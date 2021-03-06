---
title: Fonctions des extraits de code | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets [Visual Studio], functions
- snippets [Visual Studio], functions
- IntelliSense code snippets, functions
ms.assetid: c0a2bf21-8fa5-4457-9281-f599beb53e7d
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 92533b90e6a2da9f29a67d13c6e0eee2c31dbcfe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72620239"
---
# <a name="code-snippet-functions"></a>Fonctions des extraits de code
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Trois fonctions peuvent être utilisées avec les extraits de code [!INCLUDE[csprcs](../includes/csprcs-md.md)]. Les fonctions sont spécifiées dans l’élément [Function](https://msdn.microsoft.com/572c5549-5821-4e15-8ecd-0fa86c1c65df) de l’extrait de code. Pour plus d’informations sur la création d’extraits de code, consultez [extraits de code](../ide/code-snippets.md).

## <a name="functions"></a>Fonctions
 Le tableau suivant décrit les fonctions qui peuvent être utilisées avec l’élément `Function` dans les extraits de code.

|Fonction|Description|Langage|
|--------------|-----------------|--------------|
|`GenerateSwitchCases(` `EnumerationLiteral` `)`|Génère une instruction switch et un ensemble d’instructions case pour les membres de l’énumération spécifiée par le paramètre `EnumerationLiteral`. Le paramètre `EnumerationLiteral` doit être une référence à un littéral d’énumération ou un type d’énumération.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|
|`ClassName()`|Retourne le nom de la classe qui contient l’extrait de code inséré.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|
|`SimpleTypeName(` `TypeName` `)`|Réduit le paramètre *TypeName* à sa forme la plus simple dans le contexte dans lequel l’extrait de code a été appelé.|[!INCLUDE[csprcs](../includes/csprcs-md.md)]|

## <a name="example"></a>Exemple
 L’exemple suivant explique comment utiliser la fonction `GenerateSwitchCases`. Quand cet extrait de code est inséré et qu’une énumération est entrée dans le littéral `$switch_on$`, le littéral `$cases$` génère une instruction `case` pour chaque valeur contenue dans l’énumération.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>switch</Title>
            <Shortcut>switch</Shortcut>
            <Description>Code snippet for switch statement</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>expression</ID>
                    <ToolTip>Expression to switch on</ToolTip>
                    <Default>switch_on</Default>
                </Literal>
                <Literal Editable="false">
                    <ID>cases</ID>
                    <Function>GenerateSwitchCases($expression$)</Function>
                    <Default>default:</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    switch ($expression$)
                    {
                        $cases$
                    }
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Exemple
 L’exemple suivant explique comment utiliser la fonction `ClassName`. Quand cet extrait de code est inséré, le littéral `$classname$` est remplacé par le nom de la classe englobante à cet emplacement dans le fichier de code.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Common constructor pattern</Title>
            <Shortcut>ctor</Shortcut>
            <Description>Code Snippet for a constructor</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>type</ID>
                    <Default>int</Default>
                </Literal>
                <Literal>
                    <ID>name</ID>
                    <Default>field</Default>
                </Literal>
                <Literal default="true" Editable="false">
                    <ID>classname</ID>
                    <ToolTip>Class name</ToolTip>
                    <Function>ClassName()</Function>
                    <Default>ClassNamePlaceholder</Default>
                </Literal>
            </Declarations>
            <Code Language="vjsharp" Format="CData">
                <![CDATA[
                    public $classname$ ($type$ $name$)
                    {
                        this._$name$ = $name$;
                    }
                    private $type$ _$name$;
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Exemple
 Cet exemple montre comment utiliser la fonction `SimpleTypeName`. Quand cet extrait de code est inséré dans un fichier de code, le littéral `$SystemConsole$` est remplacé par la forme la plus simple du type <xref:System.Console> dans le contexte dans lequel l’extrait de code a été appelé.

```
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Console_WriteLine</Title>
            <Shortcut>cw</Shortcut>
            <Description>Code snippet for Console.WriteLine</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal Editable="false">
                    <ID>SystemConsole</ID>
                    <Function>SimpleTypeName(global::System.Console)</Function>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    $SystemConsole$.WriteLine();
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="see-also"></a>Voir aussi
 [Function, élément (extraits de code IntelliSense) référence de](https://msdn.microsoft.com/572c5549-5821-4e15-8ecd-0fa86c1c65df) [schéma des extraits de code](../ide/code-snippets-schema-reference.md)
