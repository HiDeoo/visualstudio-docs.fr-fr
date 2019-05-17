---
title: Page Options, Éditeur de texte, propriétés de nœud | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d127aaa85cdd8da9e5daebe5c7841e0f6e85238d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674877"
---
# <a name="options-page-text-editor-node-properties"></a>Page Options, Éditeur de texte, propriétés de nœud
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ce document décrit certaines pages (ou collections de propriétés) associées à la catégorie **Éditeur de texte**, `DTE.Properties("TextEditor", <Property Page>)`, de la boîte de dialogue **Options**. Le titre de chaque sous-section correspond à l'appel utilisé pour accéder à la collection `Properties`, et le tableau figurant dans chaque sous-section répertorie les propriétés présentes dans la collection.  
  
 Les macros Visual Basic dans [Contrôle des paramètres de la boîte de dialogue Options](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d) montrent comment afficher des options actuelles et leurs valeurs pour chaque page de la boîte de dialogue **Options**.  
  
## <a name="general"></a>Général  
 `DTE.Properties("TextEditor", "General")`  
  
|Nom de l'élément de propriété|Value|Description|  
|------------------------|-----------|-----------------|  
|GoToAnchorAfterEscape|Get/Set (booléen)|Si la valeur est `True`, le fait d'appuyer sur Échap durant une sélection déplace le point d'insertion là où l'action qui a créé la sélection a été initiée. Si la valeur est `False`, le point d'insertion est déplacé à l'autre bout de la sélection.|  
|DragNDropTextEditing|Get/Set (booléen)|Détermine si vous pouvez faire glisser, dans le document, d'un emplacement à un autre, une zone de texte sélectionnée dans le cadre d'une opération Copier ou Couper/coller.|  
|HorizontalScrollBar|Get/Set (booléen)|Détermine si une barre de défilement horizontale apparaît dans les fenêtres de l'éditeur.|  
|VerticalScrollBar|Get/Set (booléen)|Détermine si une barre de défilement verticale apparaît dans les fenêtres de l'éditeur.|  
|SelectionMargin|Get/Set (booléen)|Détermine si un espace existe à gauche du volet de texte pour les opérations de sélection spéciales, le dessin d'icônes de point d'arrêt, etc.|  
|MarginIndicatorBar|Get/Set (booléen)|Détermine si une ligne verticale sépare la marge de gauche du volet de texte du corps principal du volet de texte.|  
|UndoCaretActions|Get/Set (booléen)|Si `True`. les opérations d’annulation comprennent le mouvement du point d’insertion, les commandes de sélection, et ainsi de suite, en plus des actions de modification qui s’appliquent à la mémoire tampon.|  
|AutoDelimiterHighlighting|Get/Set (booléen)|Détermine si la saisie d'un délimiteur fermant provoque la mise en surbrillance du délimiteur ouvrant par l'éditeur. L'éditeur affiche toujours en gras le délimiteur ouvrant quelle que soit la valeur de cette propriété.|  
|EditorEmulation|Get/Set (Enum)||  
|DetectUTF8WithoutSignature|Get/Set (booléen)|Détecte si un fichier utilise l'encodage UTF-8 lorsqu'il n'a pas de signature d'encodage.|  
|TrackChanges|Get/Set (booléen)||  
  
## <a name="plain-text"></a>Texte brut  
 `DTE.Properties("TextEditor", "PlainText")`  
  
 Les options d'éditeur `PlainText` affectent les paramètres d'éditeur lorsque les fichiers texte sont modifiés. Chaque langage de programmation et package [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] dispose de ses propres paramètres **Éditeur de texte**. Par exemple, pour afficher ou modifier les paramètres d'éditeur [!INCLUDE[csprcs](../../includes/csprcs-md.md)], utilisez `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")`. Pour les paramètres de l’éditeur de **SQL Script**, utilisez `DTE.Properties("TextEditor", "SQL ")`.  
  
|Nom de l'élément de propriété|Value|Description|  
|------------------------|-----------|-----------------|  
|AutoListMembers|Get/Set (booléen)|Détermine si une liste des membres disponibles s'affiche automatiquement lorsqu'un utilisateur tape un point à la suite d'une référence variable.|  
|AutoListParams|Get/Set (booléen)|Détermine si la description d'une liste d'arguments s'affiche automatiquement lorsque l'utilisateur tape une parenthèse ouvrante, ( , à la suite d'un nom de fonction.|  
|HideAdvancedMembers|Get/Set (booléen)|Détermine si la saisie semi-automatique des instructions affiche la liste de tous les membres ou uniquement des membres les plus utilisés.|  
|VirtualSpace|Get/Set (booléen)|Détermine si des espaces blancs sont affichés en tant que graphiques. Une valeur `true` provoque l'affectation à l'élément de propriété `WordWrap` (dans cette liste) d'une valeur `false`.|  
|WordWrap|Get/Set (booléen)|Détermine si l'affichage insère un retour de ligne pour les lignes longues à la limite des mots. Une valeur `true` provoque l'affectation à l'élément de propriété `VirtualSpace` (dans cette liste) d'une valeur `false`.|  
|WordWrapGlyphs|Get/Set (booléen)|Affiche un glyphe à la fin d'une ligne ; cela indique qu'elle se poursuit à la ligne suivante.|  
|EnableLeftClickForURLs|Get/Set (booléen)|Détermine si l'éditeur souligne les URL et permet d'accéder à l'URL en cliquant une fois sur le bouton gauche dans le navigateur Web inscrit du système.|  
|IndentStyle|Get/Set (<xref:EnvDTE.vsIndentStyle>)|Détermine le style de mise en retrait : Par défaut, Smart ou aucun.|  
|TabSize|Get/Set (Long)|Représente le nombre d'espaces auquel équivaut une tabulation. Échec s'il ne s'agit pas d'un entier compris entre 1 et 60.|  
|InsertTabs|Get/Set (booléen)|En cas de valeur `True`, des caractères de tabulation sont utilisés pour le retrait.|  
|IndentSize|Get/Set (Long)|Représente le nombre d'espaces qui équivaut à un niveau de retrait. Échec s'il ne s'agit pas d'une valeur entière comprise entre 1 et 60.|  
|ShowLineNumbers|Get/Set (booléen)|Détermine si l'affichage d'un document de l'éditeur principal affiche des numéros de ligne dans la marge de gauche.|  
|ShowNavigationBar|Get/Set (booléen)|Détermine si les listes déroulantes et les boutons s'affichent en haut des fenêtres de l'éditeur.|  
|CutCopyBlankLines|Get/Set (booléen)|Coupe ou copie des lignes vides lorsqu'elles sont sélectionnées.|  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle des paramètres de la boîte de dialogue Options](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Détermination des noms d’éléments de propriété dans les pages Options](https://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Page Options, Propriétés du nœud Environnement](../../ide/reference/options-page-environment-node-properties.md)   
 [Page Options, Propriétés du nœud Polices et couleurs](../../ide/reference/options-page-fonts-and-colors-node-properties.md)
