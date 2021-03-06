---
title: '&lt;field&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <field> JavaScript XML tag
- field JavaScript XML tag
ms.assetid: c494bae0-3095-42a3-aa0a-4c415188c65c
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a3fc786e4d99d1eaff4a8b152ea9496ce8400ff1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72663859"
---
# <a name="ltfieldgt-javascript"></a>&lt;field&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie des informations de documentation, y compris une description, pour un champ ou un membre défini sur un objet.

## <a name="syntax"></a>Syntaxe

```
<field name="fieldName" static="true|false"
    type="FieldType" integer="true|false"
    domElement="true|false" mayBeNull="true|false"
    elementType="ArrayElementType" elementInteger="true|false"
    elementDomElement="true|false" elementMayBeNull="true|false"
    helpKeyword="keyword" locid="descriptionID"
    value="code">description
</field>
```

#### <a name="parameters"></a>Paramètres
 `name` Nom du champ ou du membre. Lorsque l' `<field>` élément est utilisé dans une fonction constructeur, `name` est obligatoire et définit le membre auquel s’applique la balise. Lorsque l' `<field>` élément annote directement un champ, cet attribut est ignoré et le nom utilisé par Visual Studio est le nom du champ réel dans le code source.

 `static` Facultatif. Spécifie si le champ est membre de la fonction constructeur ou d’un membre de l’objet retourné par la fonction constructeur. Affectez `true` la valeur pour traiter le champ comme un membre de la fonction constructeur. Affectez `false` la valeur pour traiter le champ comme un membre de l’objet retourné par la fonction constructeur.

 `type` Facultatif. Type de données du champ. Le type peut être l’un des suivants :

- Type de langage ECMAScript dans la spécification ECMAScript 5, tel que `Number` et `Object` .

- Objet DOM, comme `HTMLElement`, `Window` et `Document`.

- Fonction constructeur JavaScript.

  `integer` Facultatif. Si `type` est `Number` , spécifie si le champ est un entier. Affectez `true` la valeur pour indiquer que le champ est un entier ; sinon, affectez à la valeur `false` . Cet attribut n’est pas utilisé par Visual Studio pour fournir des informations IntelliSense.

  `domElement` Facultatif. Cet attribut est déprécié ; l’attribut `type` a la priorité sur cet attribut. Cet attribut spécifie si le champ documenté est un élément DOM. Affectez `true` la valeur à pour spécifier que le champ est un élément DOM ; sinon, affectez à la valeur `false` . Si l' `type` attribut n’est pas défini et que `domElement` a la valeur `true` , IntelliSense traite le champ documenté comme un lors de l’exécution de la `HTMLElement` saisie semi-automatique des instructions.

  `mayBeNull` Facultatif. Spécifie si le champ documenté peut avoir la valeur null. Affectez `true` la valeur pour indiquer que le champ peut avoir la valeur NULL ; sinon, affectez à la valeur `false` . La valeur par défaut est `false`. Cet attribut n’est pas utilisé par Visual Studio pour fournir des informations IntelliSense.

  `elementType` Facultatif. Si `type` est `Array`, cet attribut spécifie le type des éléments contenus dans le tableau.

  `elementInteger` Facultatif. Si `type` est `Array` et que `elementType` est `Number`, cet attribut indique si les éléments contenus dans le tableau sont des entiers. Définissez `true` pour indiquer que les éléments du tableau sont des entiers ; sinon, définissez `false`. Cet attribut n’est pas utilisé par Visual Studio pour fournir des informations IntelliSense.

  `elementDomElement` Facultatif. Cet attribut est déprécié ; l’attribut `elementType` a la priorité sur cet attribut. Si `type` est `Array`, cet attribut indique si les éléments contenus dans le tableau sont des éléments DOM. Définissez `true` pour indiquer que les éléments sont des éléments DOM ; sinon, définissez `false`. Si l’attribut `elementType` n’est pas défini et que `elementDomElement` est défini sur `true`, IntelliSense considère chaque élément du tableau en tant que `HTMLElement` au moment de procéder à la complétion des instructions.

  `elementMayBeNull` Facultatif. Si `type` est `Array`, indique si les éléments contenus dans le tableau peuvent être définis sur null. Définissez `true` pour indiquer que les éléments contenus dans le tableau peuvent être définis sur null ; sinon, définissez `false`. La valeur par défaut est `false`. Cet attribut n’est pas utilisé par Visual Studio pour fournir des informations IntelliSense.

  `helpKeyword` Facultatif. Mot clé pour l’aide F1.

  `locid` Facultatif. Identificateur des informations de localisation relatives au champ. L’identificateur est soit un ID de membre soit il correspond à la valeur d’attribut `name` dans un lot de messages défini par des métadonnées OpenAjax. Le type d’identificateur dépend du format spécifié dans la [\<loc>](../ide/loc-javascript.md) balise.

  `value` Facultatif. Spécifie le code qui doit être évalué pour être utilisé par IntelliSense au lieu du code de fonction lui-même. Pour `<field>` , cet attribut est pris en charge pour les fonctions de constructeur, mais n’est pas pris en charge pour les littéraux d’objet. Vous pouvez utiliser cet attribut pour fournir des informations de type lorsque le type de champ n’est pas défini. Par exemple, vous pouvez utiliser `value=’1’` pour traiter le type de champ en tant que nombre.

  `description` Facultatif. Description du champ.

## <a name="remarks"></a>Notes
 L' `name` attribut est obligatoire lorsque vous documentez un champ dans une fonction constructeur. Pour tous les autres scénarios, tous les attributs de l' `<field>` élément sont facultatifs.

 Lorsque vous documentez une fonction constructeur, l' `<field>` élément doit apparaître immédiatement avant la déclaration du champ. L' `name` attribut doit correspondre au nom de champ utilisé dans le code source. Pour les membres d’objet, l' `name` attribut peut être omis si l' `<field>` élément apparaît immédiatement avant la déclaration de membre d’objet.

## <a name="example"></a>Exemple
 L’exemple de code suivant montre comment utiliser l'élément `<field>`.

```javascript
// Use of <field> in an object definition.
var Rectangle = {
    /// <field type='Number'>The width of the rectangle.</field>
    wid: 5,
    /// <field type='Number'>The length of the rectangle.</field>
    len: 0,
    /// <field type='Number'>Returns the area of the rectangle.</field>
    getArea: function (wid, len) {
        return len * wid;
    }
}

// Use of <field> in a constructor function.
// The name attribute is required.
function Engine() {
    /// <field name='HorsePower' type='Number'>The engine's horsepower.</field>
    this.HorsePower = 150;
}
```

## <a name="example"></a>Exemple
 L’exemple suivant montre comment utiliser l' `<field>` élément avec l' `static` attribut défini sur `true` .

```javascript
function Engine() {
    /// <field name='HorsePower' static='true' type='Number'>static field desc.</field>
}

Engine.HorsePower = 140;
// IntelliSense on the field is available here.
Engine.

```

## <a name="example"></a>Exemple
 L’exemple suivant montre comment utiliser l' `<field>` élément avec l' `static` attribut défini sur `false` .

```javascript
function Engine() {
    /// <field name='HorsePower' static='false' type='Number'>Non-static field desc.</field>
}

Engine.HorsePower = 140;
var eng = new Engine();
// IntelliSense on the field is available here.
eng.

```

## <a name="example"></a>Exemple
 L’exemple suivant montre comment utiliser l' `<field>` élément avec l' `value` attribut.

```javascript
function calculator(a) {
    /// <field name='f' value='1'/>
}
new calculator().f.   // Completion list for a Number.

```

## <a name="see-also"></a>Voir aussi
 [Commentaires de documentation XML](../ide/xml-documentation-comments-javascript.md)
