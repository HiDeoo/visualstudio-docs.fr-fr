---
title: 'CA1058 : Les Types ne doivent pas étendre certains types de base | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e3cb06e77962bfd5e6bf377afc9f1e81f1efb520
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49206308"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058 : Les types ne doivent pas étendre certains types de base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type visible de l'extérieur étend certains types de base. Actuellement, cette règle signale les types qui dérivent des types suivants :

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.Xml.XmlDocument?displayProperty=fullName>

-   <xref:System.Collections.CollectionBase?displayProperty=fullName>

-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>

-   <xref:System.Collections.Queue?displayProperty=fullName>

-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

-   <xref:System.Collections.SortedList?displayProperty=fullName>

-   <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>Description de la règle
 Pour [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] version 1, il était recommandé de dériver les nouvelles exceptions de <xref:System.ApplicationException>. La recommandation a changé et de nouvelles exceptions doivent dériver de <xref:System.Exception?displayProperty=fullName> ou une de ses sous-classes dans le <xref:System> espace de noms.

 Ne créez pas une sous-classe de <xref:System.Xml.XmlDocument> si vous souhaitez créer une vue XML d’une source de données ou le modèle objet sous-jacent.

### <a name="non-generic-collections"></a>Collections non génériques
 Utiliser et/ou étendre des collections génériques chaque fois que possible. N’étendez pas de collections non génériques dans votre code, à moins que vous ayez expédiées précédemment.

 **Exemples d’utilisations incorrectes**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **Exemples d’utilisation correcte**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, dérivez le type d’un autre type de base ou une collection générique.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas un avertissement de cette règle pour les violations sur <xref:System.ApplicationException>. Il est possible de supprimer un avertissement de cette règle pour les violations sur <xref:System.Xml.XmlDocument>. Il est possible de supprimer un avertissement à propos d’une collection non générique si le code a été publié précédemment.



