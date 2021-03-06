---
title: 'Procédure pas à pas : analyse du code C-C++ pour les erreurs | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.assetid: eaee55b8-85fe-47c7-a489-9be0c46ae8af
caps.latest.revision: 37
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: c822dbcc6a1ece2040da22a3442dd584c3926d97
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "77272435"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>Procédure pas à pas : analyse du code C/C++ pour rechercher les erreurs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette procédure pas à pas montre comment analyser du code C/C++ pour les erreurs de code potentielles à l’aide de l’outil d’analyse du code pour le code C/C++.  
  
 Dans cette procédure pas à pas, vous parcourez le processus d’utilisation de l’analyse du code pour analyser votre code C/C++ pour identifier les erreurs de code potentielles.  
  
 Vous allez accomplir les étapes ci-dessous :  
  
- Exécutez l’analyse du code sur du code natif.  
  
- Analyser les avertissements de défaut de code.  
  
- Traiter l’avertissement comme une erreur.  
  
- Annoter le code source pour améliorer l’analyse des erreurs de code.  
  
## <a name="prerequisites"></a>Prérequis  
  
- [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)] ou [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)].  
  
- Copie de l' [exemple de démonstration](../code-quality/demo-sample.md).  
  
- Connaissances de base de C/C++.  
  
### <a name="to-run-code-defect-analysis-on-native-code"></a>Pour exécuter l’analyse des erreurs de code sur du code natif  
  
1. Ouvrez la solution de démonstration dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .  
  
     La solution de démonstration remplit maintenant **Explorateur de solutions**.  
  
2. Dans le menu **Générer**, cliquez sur **Régénérer la solution**.  
  
     La solution est générée sans erreurs ou avertissements.  
  
3. Dans **Explorateur de solutions**, sélectionnez le projet CodeDefects.  
  
4. Dans le menu **Projet** , cliquez sur **Propriétés**.  
  
     La boîte de dialogue **pages de propriétés de CodeDefects** s’affiche.  
  
5. Cliquez sur **Analyse du code**.  
  
6. Activez la case à cocher **activer l’analyse du code pour C/C++ sur la build** .  
  
7. Régénérez le projet CodeDefects.  
  
     Les avertissements de l’analyse du code s’affichent dans la **liste d’erreurs**.  
  
### <a name="to-analyze-code-defect-warnings"></a>Pour analyser les avertissements de défauts de code  
  
1. Dans le menu **Affichage** , cliquez sur **Liste d'erreurs**.  
  
     Selon le profil de développeur que vous avez choisi dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , vous devrez peut-être pointer sur **autres fenêtres** dans le menu **affichage** , puis cliquez sur **liste d’erreurs**.  
  
2. Dans la **liste d’erreurs**, double-cliquez sur l’avertissement suivant :  
  
     avertissement C6230 : cast implicite entre les types sémantiquement différents : utilisation de HRESULT dans un contexte booléen.  
  
     L’éditeur de code affiche la ligne qui a provoqué l’avertissement dans la fonction `bool``ProcessDomain()` . Cet avertissement indique qu’un HRESULT est utilisé dans une instruction’If’où un résultat booléen est attendu.  
  
3. Corrigez cet avertissement à l’aide de la macro SUCCEEDED. Votre code doit ressembler au code suivant :  
  
    ```  
    if (SUCCEEDED (ReadUserAccount()) )  
    ```  
  
4. Dans la **liste d’erreurs**, double-cliquez sur l’avertissement suivant :  
  
     AVERTISSEMENT C6282 : opérateur incorrect : assignation à une constante dans le contexte de test. Était = = prévu ?  
  
5. Corrigez cet avertissement en vérifiant l’égalité. Votre code doit ressembler au code suivant :  
  
    ```  
    if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))  
    ```  
  
### <a name="to-treat-warning-as-an-error"></a>Pour traiter l’avertissement comme une erreur  
  
1. Dans le fichier bug. cpp, ajoutez l' `#pragma` instruction suivante au début du fichier pour traiter l’avertissement C6001 comme une erreur :  
  
    ```  
    #pragma warning (error: 6001)  
    ```  
  
2. Régénérez le projet CodeDefects.  
  
     Dans le **liste d’erreurs**, C6001 s’affiche à présent comme une erreur.  
  
3. Corrigez les deux erreurs C6001 restantes dans le **liste d’erreurs** en initialisant `i` et `j` en 0.  
  
4. Régénérez le projet CodeDefects.  
  
     Le projet est généré sans avertissements ou erreurs.  
  
### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>Pour corriger les avertissements d’annotation de code source dans annotation. c  
  
1. Dans Explorateur de solutions, sélectionnez le projet annotations.  
  
2. Dans le menu **Projet** , cliquez sur **Propriétés**.  
  
     La boîte de dialogue **pages de propriétés des annotations** s’affiche.  
  
3. Cliquez sur **Analyse du code**.  
  
4. Activez la case à cocher **activer l’analyse du code pour C/C++ sur la build** .  
  
5. Régénérez le projet annotations.  
  
6. Dans la **liste d’erreurs**, double-cliquez sur l’avertissement suivant :  
  
     AVERTISSEMENT C6011 : suppression de la référence du pointeur NULL’newNode'.  
  
     Cet avertissement indique un échec de la vérification par l’appelant de la valeur de retour. Dans ce cas, un appel à **AllocateNode** peut retourner une valeur null (consultez le fichier d’en-tête annotations. h pour la déclaration de fonction pour AllocateNode).  
  
7. Ouvrez le fichier annotations. cpp.  
  
8. Pour corriger cet avertissement, utilisez une instruction’If’pour tester la valeur de retour. Votre code doit ressembler au code suivant :  
  
     `if (NULL != newNode)`  
  
     `{`  
  
     `newNode->data = value;`  
  
     `newNode->next = 0;`  
  
     `node->next = newNode;`  
  
     `}`  
  
9. Régénérez le projet annotations.  
  
     Le projet est généré sans avertissements ou erreurs.  
  
### <a name="to-use-source-code-annotation"></a>Pour utiliser l’annotation de code source  
  
1. Annotez les paramètres formels et la valeur de retour de la fonction `AddTail` en utilisant les conditions de pré et de publication comme indiqué dans cet exemple :  
  
     `[returnvalue:SA_Post (Null=SA_Maybe)] LinkedList* AddTail`  
  
     `(`  
  
     `[SA_Pre(Null=SA_Maybe)] LinkedList* node,`  
  
     `int value`  
  
     `)`  
  
2. Régénérez le projet annotations.  
  
3. Dans la **liste d’erreurs**, double-cliquez sur l’avertissement suivant :  
  
     AVERTISSEMENT C6011 : suppression de la référence du pointeur NULL’node'.  
  
     Cet avertissement indique que le nœud passé dans la fonction peut avoir la valeur null, et indique le numéro de ligne où l’avertissement a été déclenché.  
  
4. Pour corriger cet avertissement, utilisez une instruction’If’pour tester la valeur de retour. Votre code doit ressembler au code suivant :  
  
    ```  
    . . .  
    LinkedList *newNode = NULL;   
    if (NULL == node)  
    {  
         return NULL;  
        . . .  
    }  
    ```  
  
5. Régénérez le projet annotations.  
  
     Le projet est généré sans avertissements ou erreurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Procédure pas à pas : analyse du code managé pour les erreurs de code](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)
