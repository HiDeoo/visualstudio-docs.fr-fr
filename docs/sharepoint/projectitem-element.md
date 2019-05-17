---
title: ProjectItem, élément | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItem element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2768a2e55b3e38158f2ef6b856a653a1a2c12dfa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562401"
---
# <a name="projectitem-element"></a>ProjectItem (élément)
  Représente un élément de projet SharePoint. Cet élément de l’élément racine requis de la *.spdata* fichier.

## <a name="syntax"></a>Syntaxe

```xml
<ProjectItem DefaultFile = "File that opens in the editor when you open the project item"
    FeatureReceiverClass = "Class that implements a feature receiver for the project item"
    FeatureReceiverAssembly = "Assembly that defines a feature receiver for the project item"
    SupportedTrustLevels = "Trust levels that the project item supports"
    SupportedDeploymentScopes = "Deployment scopes that the project item supports"
    Type="Identifier for the project item">
  <Files>...</Files>
  <ProjectItemFolder>...</ProjectItemFolder>
  <SafeControls>...</SafeControls>
  <FeatureProperties>...</FeatureProperties>
  <ExtensionData>...</ExtensionData>
</ProjectItem>
```

## <a name="attributes-and-elements"></a>Attributs et éléments
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.

### <a name="attributes"></a>Attributs

|Attribut|Description|
|---------------|-----------------|
|**DefaultFile**|Facultatif **xs : string** attribut.<br /><br /> Le chemin d’accès relatif, y compris le nom de fichier du fichier qui s’ouvre dans l’éditeur Visual Studio lorsque vous ouvrez l’élément de projet SharePoint dans **l’Explorateur de solutions**. Le chemin d’accès est relatif à partir du dossier qui contient le *.spdata* fichier.|
|**FeatureReceiverClass**|Facultatif **xs : String** attribut.<br /><br /> Le nom qualifié complet d’une classe de récepteur de fonctionnalité pour cet élément de projet SharePoint. Pour plus d’informations sur les récepteurs, consultez [fournissent des informations d’empaquetage et de déploiement dans les éléments de projet](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|
|**FeatureReceiverAssembly**|Facultatif **xs : String** attribut.<br /><br /> Spécifie le nom qualifié complet d’un assembly qui définit un récepteur de fonctionnalité pour cet élément de projet SharePoint. Pour plus d’informations sur les récepteurs, consultez [fournissent des informations d’empaquetage et de déploiement dans les éléments de projet](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md). Pour plus d’informations sur les noms d’assembly qualifiés complets, consultez [noms d’assemblys](/dotnet/framework/app-domains/assembly-names).|
|**SupportedTrustLevels**|Facultatif **xs : String** attribut.<br /><br /> Spécifie les niveaux de confiance prenant en charge cet élément de projet SharePoint. Cette valeur peut être une des chaînes suivantes : Sandbox, FullTrust, ou la totalité. La valeur All spécifie Sandboxed et FullTrust.<br /><br /> Dans un type d’élément de projet SharePoint personnalisé, la valeur de cet attribut correspond à la valeur que vous attribuez à la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> propriété dans votre implémentation de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> (méthode). Si vous spécifiez une valeur différente pour cet attribut, Visual Studio remplace la valeur afin qu’elle spécifie le même niveau de confiance que vous spécifiez dans le <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> propriété.|
|**SupportedDeploymentScopes**|Facultatif **xs : String** attribut.<br /><br /> Spécifie les portées de déploiement qui prend en charge par cet élément de projet SharePoint. Cette valeur est une chaîne délimitée par des virgules qui se compose d’une ou plusieurs des chaînes suivantes : Batterie de serveurs, Site, Web, WebApplication ou Package. Par exemple :`Web, Site`<br /><br /> Dans un type d’élément de projet SharePoint personnalisé, la valeur de cet attribut correspond à la valeur que vous attribuez à la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> propriété dans votre implémentation de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> (méthode). Si vous spécifiez une valeur différente pour cet attribut, Visual Studio remplace la valeur afin qu’elle spécifie le même niveau de confiance que vous spécifiez dans le <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> propriété.|
|**Type**|Requis **xs : String** attribut.<br /><br /> L’identificateur pour l’élément de projet SharePoint. Dans un type d’élément de projet SharePoint personnalisé, l’identificateur est la chaîne que vous passez à la <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Pour plus d'informations, voir [Procédure : Définir un type d’élément de projet SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).<br /><br /> Pour obtenir la liste des identificateurs pour les éléments de projet SharePoint intégrés inclus avec Visual Studio, consultez [éléments de projet SharePoint étendre](../sharepoint/extending-sharepoint-project-items.md).|

### <a name="child-elements"></a>Éléments enfants

|Élément|Description|
|-------------|-----------------|
|[ExtensionData](../sharepoint/extensiondata-element.md)|Élément facultatif.<br /><br /> Représente une collection d’éléments de données personnalisés qui sont associés à l’élément de projet SharePoint.<br /><br /> Vous pouvez inclure qu’un seul **ExtensionData** élément.|
|[FeatureProperties](../sharepoint/featureproperties-element.md)|Élément facultatif.<br /><br /> Représente une collection de valeurs de propriété qui sont incluses avec une fonctionnalité lorsqu’elle est déployée vers SharePoint.<br /><br /> Vous pouvez inclure qu’un seul **FeatureProperties** élément.|
|[Fichiers](../sharepoint/files-element.md)|Facultatif **FileCollectionType** élément.<br /><br /> Spécifie les fichiers à déployer avec l’élément de projet SharePoint, tels que les fichiers d’élément de fonctionnalité et la sortie des projets non-SharePoint dépendants.<br /><br /> Inclure un **fichiers** ou un **ProjectItemFolder** élément, mais pas les deux.|
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|Facultatif **ProjectItemFolderType** élément.<br /><br /> Représente un dossier mappé.<br /><br /> Inclure un **fichiers** ou un **ProjectItemFolder** élément, mais pas les deux.|
|[SafeControls](../sharepoint/safecontrols-element.md)|Élément facultatif.<br /><br /> Représente une collection de contrôles ASPX et les composants WebPart qui sont désignés comme sécurisés pour tous les utilisateurs à accéder sur n’importe quelle page ASPX du site SharePoint.<br /><br /> Vous pouvez inclure qu’un seul **SafeControls** élément.|

### <a name="parent-elements"></a>Éléments parents
 Aucun.

## <a name="element-information"></a>Informations sur les éléments

|||
|-|-|
|**Espace de noms**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Nom de schéma**|Schéma d’élément de projet SharePoint|
|**Fichier de validation**|ProjectItemModelSchema.xsd|
|**Peut être vide**|Non|

## <a name="see-also"></a>Voir aussi
[Rseference de schéma d’élément de projet SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
