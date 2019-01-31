---
title: Utilisation des nuanceurs | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3e0f962440d722a881d7a8de4ed2e7c9a9c7755f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54795908"
---
# <a name="working-with-shaders"></a>Utilisation des nuanceurs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser le concepteur Shader graphique dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour concevoir des effets de nuanceur personnalisés. Vous pouvez utiliser ces nuanceurs dans votre jeu ou votre application DirectX.  
  
## <a name="shaders"></a>Nuanceurs  
 Un *nuanceur* est un logiciel qui effectue des calculs graphiques, par exemple des transformations de sommets ou une coloration de pixels, et qui s’exécute généralement sur un processeur graphique (GPU) plutôt que sur l’UC. Comme la plupart des phases du pipeline graphique traditionnel à fonction fixe sont maintenant effectuées par des programmes de nuanceur, vous pouvez les utiliser pour créer un pipeline spécifique aux besoins de votre application.  
  
 Les types les plus courants de nuanceurs sont les *nuanceurs de sommets*, qui effectuent des calculs par sommet et remplacent la transformation de fonction fixe et le circuit d’éclairage dans le matériel graphique non programmable, et les *nuanceurs de pixels*, qui effectuent des calculs par pixel qui déterminent la couleur d’un pixel et remplacent le circuit de combinaison de couleurs à fonction fixe dans le matériel graphique non programmable. Grâce au matériel graphique moderne, d’autres types de nuanceurs sont possibles : les *nuanceurs de coque*, les *nuanceurs de domaine* et les *nuanceurs de géométrie* pour les calculs graphiques, ainsi que les *nuanceurs de calcul* pour les calculs non graphiques. Aucune de ces phases n’est disponible dans le matériel graphique non programmable. Les nuanceurs ont été créés initialement à l’aide d’un langage semblable à un langage d’assembly qui fournissait des instructions parallèles aux données (SIMD) et centrées sur les graphiques (produit scalaire). Aujourd’hui, les nuanceurs sont généralement créés à l’aide de langages de haut niveau, semblables au langage C, comme HLSL (High Level Shader Language).  
  
 Vous pouvez utiliser le concepteur Shader pour créer des nuanceurs de pixels de manière interactive plutôt qu’en entrant et en compilant du code. Dans le concepteur Shader, un nuanceur est défini par un nombre de nœuds qui représentent des données et des opérations, et par des connexions entre les nœuds qui représentent le flux de valeurs de données et les résultats intermédiaires dans le nuanceur. En utilisant cette approche et l’aperçu en temps réel dans le concepteur Shader, vous pouvez visualiser plus facilement l’exécution du nuanceur et « découvrir » des variations de nuanceur intéressantes en expérimentant.  
  
## <a name="dgsl-documents"></a>Documents DGSL  
 Le concepteur Shader enregistre les nuanceurs au format DGSL (Directed Graph Shader Language), format XML basé sur le langage DGML (Directed Graph Markup Language). Vous pouvez appliquer des nuanceurs DGSL directement à des modèles 3D dans l’éditeur de modèle. Toutefois, avant de pouvoir utiliser un nuanceur DGSL dans votre application, vous devez l’exporter dans un format pris en charge par DirectX, par exemple HLSL.  
  
 Le langage DGSL étant compatible avec le langage DGML, vous pouvez utiliser des outils conçus pour analyser des documents DGML pour analyser vos nuanceurs DGSL. Pour plus d’informations sur le langage DGML, consultez [Fonctionnement du langage DGML (Directed Graph Markup Language)](http://msdn.microsoft.com/library/ee842619.aspx).  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Concepteur Shader](../designers/shader-designer.md)|Explique comment utiliser le concepteur Shader de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour travailler avec des nuanceurs.|  
|[Nœuds du concepteur Shader](../designers/shader-designer-nodes.md)|Décrit les types de nœuds du concepteur Shader que vous pouvez utiliser pour obtenir des effets graphiques.|  
|[Exemples du concepteur Shader](../designers/shader-designer-examples.md)|Fournit des liens vers des rubriques qui montrent comment utiliser le concepteur Shader pour obtenir des effets graphiques courants.|
