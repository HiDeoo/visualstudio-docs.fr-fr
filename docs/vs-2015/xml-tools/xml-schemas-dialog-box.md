---
title: Boîte de dialogue schémas XML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: da0c73655c5c08da993fdf72bffdfeca0eb4b304
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58949084"
---
# <a name="xml-schemas-dialog-box"></a>Boîte de dialogue Schémas XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Le **schémas XML** boîte de dialogue permet de sélectionner les XML schema definition language (XSD) à associer à un document XML. Vous pouvez sélectionner un schéma dans le cache de schéma ou spécifier un schéma situé ailleurs dans le cache. Les schémas sélectionnés sont considérés comme faisant partie d'un jeu de schémas. Le jeu de schémas est utilisé pour IntelliSense et pour la validation de documents XML.  
  
 Vous pouvez accéder à la **schémas XML** boîte de dialogue en cliquant sur le **schémas** bouton dans la fenêtre de propriétés de document, ou en sélectionnant **schémas** à partir de la **XML** menu.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Utilisation**  
 Sélectionnez la manière dont le schéma XML doit être utilisé.  
  
- **Automatique**. Ce schéma n'est pas utilisé par le document en cours mais est disponible pour l'association automatique. Si le document XML déclare un espace de noms qui correspond au `targetNamespace` de ce schéma, le schéma sera automatiquement associé et inclus dans le jeu de schémas.  
  
- **Utiliser ce schéma**. Ce schéma est utilisé par le document en cours. Soit l'utilisateur a explicitement demandé que ce schéma soit utilisé en cliquant sur cette colonne, soit le schéma a été automatiquement associé en fonction d'un `targetNamespace` correspondant.  
  
- **N’utilisez pas les schémas sélectionnés**. Ce schéma n'est pas utilisé par le document actif, même si le schéma a un `targetNamespace` correspondant. Ce paramètre peut être utile dans la résolution de conflits, lorsqu'il existe plusieurs versions du même schéma dans le cache de schéma ou dans la solution.  
  
  **Cible Namespace**  
  Affiche l'espace de noms cible associé au schéma XML.  
  
  **Nom de fichier**  
  Affiche le nom de fichier du schéma XML.  
  
  **Ajouter**  
  Ouvre le **ouvrir le schéma XSD** boîte de dialogue qui vous permet de sélectionner d’autres schémas à ajouter au jeu de schémas. Lorsque vous ajoutez un schéma au schéma défini, le **utilisation** colonne a la valeur **utiliser ce schéma**.  
  
  **Supprimer**  
  Supprime le schéma actuellement sélectionné du jeu de schémas. Cela supprime le schéma du cache de schémas en mémoire, mais pas du système de fichiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Composants de l’éditeur XML](../xml-tools/xml-editor-components.md)   
 [Guide pratique pour Sélectionnez les schémas XML à utiliser](../xml-tools/how-to-select-the-xml-schemas-to-use.md)   
 [Cache de schéma](../xml-tools/schema-cache.md)
