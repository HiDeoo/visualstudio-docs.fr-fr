---
title: Personnalisation de l’Explorateur de modèles | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.explorerbehavior
helpviewer_keywords:
- Domain-Specific Language Tools, Domain-Specific Language Explorer
ms.assetid: d2926444-9408-41d8-a27e-3fd0c416f9ac
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ce96f2a3df901c1fea0aa4caa97d29c07db5e681
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72654954"
---
# <a name="customizing-the-model-explorer"></a>Personnalisation de l'Explorateur de modèles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez modifier l’apparence et le comportement de l’Explorateur pour votre concepteur de langage spécifique à un domaine comme suit :

- Modifiez le titre de la fenêtre.

- Modifiez l’icône de tabulation.

- Modifiez les icônes des nœuds.

- Masquer les nœuds.

## <a name="changing-the-window-title"></a>Modification du titre de la fenêtre
 Pour modifier le titre de la fenêtre de l’Explorateur généré, sélectionnez comportement de l' **Explorateur** dans l' **Explorateur DSL**, puis, dans la fenêtre **Propriétés** , définissez la propriété **titre** sur le titre de votre choix.

## <a name="changing-the-tab-icon"></a>Modification de l’icône d’onglet
 Pour modifier l’icône d’onglet de l’Explorateur, utilisez une icône de 16x16 pixels dans un fichier. bmp. Placez le fichier d’icône dans le dossier \DslPackage\Resources\, puis remplacez le nom de fichier par **ModelExplorerToolWindowBitmaps.bmp**. Par exemple, vous pouvez modifier le [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] fichier icône Setup. ico au format. bmp et le renommer en **DSLLanguageName\DslPackage\Resources\ModelExplorerToolWindowBitmaps.bmp**. Le concepteur généré affiche cette icône sous l’onglet de votre explorateur lorsqu’il est ancré avec **Explorateur de solutions**.

## <a name="setting-custom-icons-on-explorer-nodes"></a>Définition des icônes personnalisées sur les nœuds de l’Explorateur
 Vous pouvez personnaliser des nœuds dans votre explorateur à l’aide des paramètres de nœud de l’Explorateur. La procédure suivante montre comment ajouter une icône à un nœud.

#### <a name="to-add-an-icon-to-an-explorer-node"></a>Pour ajouter une icône à un nœud Explorer

1. Créez une [!INCLUDE[dsl](../includes/dsl-md.md)] solution à l’aide du modèle de solution de déroulement des tâches.

2. Placez un fichier. bmp contenant une icône de 16 x 16 pixels dans le dossier **Dsl\Resources** de la solution.

3. Dans l' **Explorateur DSL**, cliquez avec le bouton droit sur **comportement** de l’Explorateur, puis cliquez sur **ajouter de nouveaux paramètres de nœud de l’Explorateur**.

     Un nœud **ExplorerNodeSettings** apparaît sous le nœud **paramètres de nœuds personnalisés** .

4. Sélectionnez **ExplorerNodeSettings**, puis, dans la fenêtre **Propriétés** , affectez à **classe** la valeur **acteur**.

5. Définissez l' **icône à afficher** dans le chemin d’accès du fichier icône.

6. Transformez tous les modèles, puis générez et exécutez la solution.

7. Dans le concepteur généré, ouvrez l’exemple de diagramme.

     L’Explorateur doit afficher trois nœuds **acteur** qui ont votre icône.

> [!NOTE]
> Si vous avez défini une icône de nœud pour un élément affiché dans l’Explorateur généré, tous les nœuds de l’Explorateur affichent l’icône. Si aucune icône n’a été définie, les nœuds affichent l’icône par défaut.

## <a name="changing-the-name-displayed-on-an-explorer-node"></a>Modification du nom affiché sur un nœud de l’Explorateur
 Vous pouvez modifier la façon dont les noms des éléments de modèle sont affichés dans votre explorateur. La procédure suivante montre comment afficher le nom de la **tâche** qui est référencée par un **Commentaire** dans le nœud commentaire.

#### <a name="to-display-a-property"></a>Pour afficher une propriété

1. Ouvrez la solution que vous avez créée dans la procédure précédente.

2. Assurez-vous que le **Commentaire** ne fait référence qu’à une classe de domaine unique en affectant à la multiplicité du rôle les **objets** de nom de propriété la valeur 0.. 1. Le nom de la propriété doit devenir **Subject**et le nom de la relation doit devenir **CommentReferencesSubject**.

3. Dans l' **Explorateur DSL**, cliquez avec le bouton droit sur **comportement** de l’Explorateur, puis cliquez sur **ajouter de nouveaux paramètres de nœud de l’Explorateur**.

     Un nœud **ExplorerNodeSettings** apparaît sous le nœud **paramètres de nœuds personnalisés** .

4. Sélectionnez **ExplorerNodeSettings**, puis dans la fenêtre **Propriétés** , affectez à **classe** la valeur **Comment**.

5. Cliquez avec le bouton droit sur le nœud **Commentaire** , puis cliquez sur **Ajouter un nouveau chemin d’accès**à la propriété.

     Un nouveau nœud s’affiche, nommé **propriété affiché**.

6. Sélectionnez la **propriété affichée**, puis dans la fenêtre **Propriétés** , cliquez sur le champ valeur de **chemin d’accès à la propriété**. Sélectionnez **Comment**, puis **CommentReferencesSubject**, puis **FlowElement**. Le chemin d’accès obtenu doit ressembler à **CommentReferencesSubject. Subject/ ! Objet**.

7. Dans le champ valeur de la **propriété**, sélectionnez **nom**.

8. Transformez tous les modèles, puis générez et exécutez votre solution.

9. Dans le concepteur généré, ouvrez l’exemple de diagramme.

10. Dessinez un **connecteur de commentaires** entre l’élément de commentaire et l’élément **Task1** sur le diagramme.

     Le nœud de l’Explorateur doit afficher le commentaire en tant que **Task1**.

## <a name="hiding-nodes"></a>Masquage des nœuds
 Vous pouvez masquer un nœud dans votre explorateur en ajoutant son chemin d’accès au nœud **nœuds masqués** de l' **Explorateur DSL**. La procédure suivante montre comment masquer des nœuds de **Commentaire** .

#### <a name="to-hide-an-explorer-node"></a>Pour masquer un nœud de l’Explorateur

1. Ouvrez la solution que vous avez créée dans la procédure précédente.

2. Dans l' **Explorateur DSL**, cliquez avec le bouton droit sur comportement de l' **Explorateur** , puis cliquez sur **Ajouter un nouveau chemin d’accès au domaine**.

     Un nœud de **chemin d’accès de domaine** apparaît sous **nœuds masqués**.

3. Sélectionnez **chemin d’accès au domaine**, puis dans la fenêtre **Propriétés** , cliquez sur le champ valeur de la définition du **chemin d’accès**. Sélectionnez **FlowGraph**, puis **FlowGraphHasComments**. Le chemin d’accès obtenu doit ressembler à **FlowGraphHasComments. Comments**

4. Transformez tous les modèles, puis générez et exécutez votre solution.

5. Dans le concepteur généré, ouvrez l’exemple de diagramme.

     L’Explorateur doit afficher uniquement un nœud **acteurs** et ne doit pas afficher le nœud **Commentaires** .

## <a name="see-also"></a>Voir aussi
 [Glossaire des Outils Domain-Specific Language](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
