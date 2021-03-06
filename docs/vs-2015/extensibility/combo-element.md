---
title: Élément combo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- Combos element (VSCT XML schema)
- VSCT XML schema elements, Combos
ms.assetid: 392e3063-f0a0-4130-9583-23bd2aa3fa36
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: daa89266d653743a743f42e5f0b8e11c954adc1a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184412"
---
# <a name="combo-element"></a>Élément Combo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Définit les commandes qui s’affichent dans une zone de liste déroulante. Il existe quatre types de zones de liste déroulante, comme suit : DropDownCombo, DynamicCombo, IndexCombo et MRUCombo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<combo guid="guidMyCommandSet" id="MyCommand" defaultWidth="20" idCommandList="MyCommandListID" priority="0x102" type="DropDownCombo">  
  <Parent>... </Parent  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</combo>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|guid|Obligatoire. GUID de l’identificateur de la commande GUID/ID.|  
|id|Obligatoire. ID de l’identificateur de la commande GUID/ID.|  
|defaultWidth|Obligatoire. Entier qui spécifie une largeur en pixels pour la zone de liste déroulante.|  
|idCommandList|Obligatoire. ID qui est envoyé à la cible de commande active pour récupérer la liste des éléments à afficher dans la zone de liste déroulante. L’ID sera dans la même portée GUID que le contrôle.|  
|priority|facultatif. Valeur numérique qui spécifie la priorité.|  
|type|facultatif. Valeur énumérée qui spécifie le type de bouton.<br /><br /> S’il n’est pas spécifié, utilise le bouton.<br /><br /> DropDownCombo<br /> Le VSPackage est chargé de remplir le contenu de cette zone de liste déroulante. L’utilisateur ne peut pas taper quoi que ce soit dans la zone de texte de cette liste déroulante.<br /><br /> DynamicCombo<br /> Le VSPackage est chargé de remplir le contenu de cette zone de liste déroulante. L’utilisateur peut modifier cette liste déroulante et également sélectionner des éléments.<br /><br /> IndexCombo<br /> Identique à DynamicCombo, sauf qu’il déclenche l’index de l’élément plutôt que son texte.<br /><br /> MRUCombo<br /> Rempli par l’environnement de développement intégré (IDE) pour le compte du VSPackage.  L’utilisateur peut modifier cette zone de liste déroulante. L’IDE se souvient des 16 dernières entrées par zone de liste déroulante.<br /><br /> Lorsque l’utilisateur sélectionne un nom dans la zone de liste déroulante ou entre un nouveau, l’IDE notifie le VSPackage approprié.|  
|Condition|facultatif. Consultez [attributs conditionnels](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Éléments enfants  
  
|Élément|Description|  
|-------------|-----------------|  
|Parent|facultatif. Élément parent du bouton.|  
|CommandFlag|Obligatoire. Consultez [élément indicateur de commande](../extensibility/command-flag-element.md). Les valeurs CommandFlag valides pour un bouton sont les suivantes.<br /><br /> -CaseSensitive<br /><br /> - CommandWellOnly<br /><br /> - DefaultDisabled<br /><br /> - DefaultInvisible<br /><br /> - DynamicVisibility<br /><br /> -Touches filtres<br /><br /> - IconAndText<br /><br /> - NoAutoComplete<br /><br /> - NoButtonCustomize<br /><br /> -Nocustom<br /><br /> - NoKeyCustomize<br /><br /> - StretchHorizontally|  
|Chaînes|Obligatoire. Consultez l' [élément Strings](../extensibility/strings-element.md). L’élément ButtonText enfant doit être défini.|  
|Annotation|Commentaire facultatif.|  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[Élément Commands](../extensibility/commands-element.md)|Représente la collection de commandes dans la barre d’outils VSPackage.|  
  
## <a name="example"></a> Exemple  
  
```  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  defaultWidth="100" idCommandList="cmdidGetInsertOptionsList">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  priority="0x0500" type="DropDownCombo" defaultWidth="100"  
  idCommandList="cmdidGetInsertOptionsList">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers Visual Studio Command Table (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
