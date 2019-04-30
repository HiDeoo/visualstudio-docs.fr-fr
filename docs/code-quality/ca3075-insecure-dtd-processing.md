---
title: 'CA3075 : Traitement DTD non sécurisé'
ms.date: 03/18/2019
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6de817e3aaecbdd1c89cc2174e91126ea39d99d7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541115"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075 : Traitement DTD non sécurisé

|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|Category|Microsoft.Security|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause

Si vous utilisez des instances de <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> non sécurisées ou référencez des sources d’entités externes, l’analyseur peut accepter une entrée non fiable et divulguer des informations sensibles à des personnes malveillantes.

## <a name="rule-description"></a>Description de la règle

Une *définition de type de document (DTD)* est l’une des deux façons pour un analyseur XML de déterminer la validité d’un document, comme défini par la recommandation du  [World Wide Web Consortium (W3C) sur le langage XML (Extensible Markup Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Cette règle recherche les propriétés et instances où les données non fiables sont acceptées pour informer les développeurs potentiel [la divulgation d’informations](/dotnet/framework/wcf/feature-details/information-disclosure) les menaces ou [par déni de Service (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) les attaques. Cette règle se déclenche quand :

- DtdProcessing est activé sur l’instance de <xref:System.Xml.XmlReader> , ce qui résout les entités XML externes à l’aide de <xref:System.Xml.XmlUrlResolver>.

- La propriété <xref:System.Xml.XmlNode.InnerXml%2A> dans le code XML est définie.

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> propriété est définie pour l’analyse.

- Non fiables entrée est traitée à l’aide de <xref:System.Xml.XmlResolver> au lieu de <xref:System.Xml.XmlSecureResolver>.

- Le <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> méthode est appelée avec un non sécurisé <xref:System.Xml.XmlReaderSettings> instance ou aucune instance du tout.

- <xref:System.Xml.XmlReader> est créé avec les paramètres par défaut non sécurisées ou des valeurs.

Dans chacun de ces cas, le résultat est le même : le contenu soit les partages de fichiers système ou réseau à partir de l’ordinateur où le code XML est traité sera exposé à l’attaquant, ou le traitement DTD peut être utilisé comme un vecteur de déni de service.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

- Intercepter et traiter toutes les exceptions XmlTextReader correctement pour éviter la divulgation d’informations de chemin d’accès.

- Utilisez le <xref:System.Xml.XmlSecureResolver> pour limiter les ressources auxquelles XmlTextReader peut accéder.

- Empêchez <xref:System.Xml.XmlReader> d’ouvrir des ressources externes en affectant à la propriété <xref:System.Xml.XmlResolver> la valeur **null**.

- Vérifiez que le <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A?displayProperty=nameWithType> propriété est affectée à partir d’une source approuvée.

**.NET 3.5 et versions antérieures**

- Désactivez le traitement DTD si vous utilisez des sources non approuvées en définissant le <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> propriété **true**.

- La classe XmlTextReader a une demande d’héritage de confiance totale.

**.NET 4 et versions ultérieures**

- Évitez d’activer DtdProcessing si vous utilisez des sources non fiables en définissant le <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> propriété **Prohibit** ou **ignorer**.

- Vérifiez que la méthode Load() accepte une instance de XmlReader dans tous les cas InnerXml.

> [!NOTE]
> Cette règle peut signaler des faux positifs sur certaines instances de XmlSecureResolver valides.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Sauf si vous êtes sûr que l’entrée provient d’une source fiable, ne supprimez aucune règle de cet avertissement.

## <a name="pseudo-code-examples"></a>Exemples de pseudo-code

### <a name="violation"></a>Violation

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>Violation

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>Violations

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlReader reader = XmlReader.Create(sreader, new XmlReaderSettings() { XmlResolver = null });
    doc.Load(reader);
}
```

### <a name="violation"></a>Violation

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlReader reader = XmlReader.Create(stream, new XmlReaderSettings() { XmlResolver = null });
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>Violation

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlReader reader = XmlReader.Create(path, new XmlReaderSettings() { XmlResolver = null });
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>Violation

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>Violations

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>Solution

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings() { XmlResolver = null };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```
