---
title: Fonction SccOpenProject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ebb8f4250b4ef4c022c5c21d748e025ca31e35a7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353604"
---
# <a name="sccopenproject-function"></a>Fonction SccOpenProject
Cette fonction ouvre un projet de contrôle de code source existant ou crée un nouveau.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccOpenProject (
   LPVOID        pvContext,
   HWND          hWnd,
   LPSTR         lpUser,
   LPCSTR        lpProjName,
   LPCSTR        lpLocalProjPath,
   LPSTR         lpAuxProjPath,
   LPCSTR        lpComment,
   LPTEXTOUTPROC lpTextOutProc,
   LONG          dwFlags
);
```

#### <a name="parameters"></a>Paramètres
 pvContext

[in] La structure de contexte de plug-in de contrôle de source.

 hWnd

[in] Handle vers la fenêtre de l’IDE que le plug-in de contrôle de code source peut utiliser en tant que parent pour les boîtes de dialogue qu’il fournit.

 lpUser

[in, out] Le nom de l’utilisateur (ne dépassant pas SCC_USER_SIZE, y compris le terminateur NULL).

 lpProjName

[in] La chaîne qui identifie le nom du projet.

 lpLocalProjPath

[in] Le chemin d’accès au dossier de travail pour le projet.

 lpAuxProjPath

[in, out] Chaîne facultative auxiliaire identifiant le projet (ne dépassant pas SCC_AUXPATH_SIZE, y compris le terminateur NULL).

 lpComment

[in] Commentaire à un nouveau projet en cours de création.

 lpTextOutProc

[in] Fonction de rappel facultative pour afficher le texte de sortie à partir du plug-in de contrôle de code source.

 dwFlags

[in] Signale si un nouveau projet doit être créé si le projet est inconnu à la source de contrôle plug-in. Valeur peut être une combinaison de `SCC_OP_CREATEIFNEW` et `SCC_OP_SILENTOPEN.`

## <a name="return-value"></a>Valeur de retour
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :

|Value|Description|
|-----------|-----------------|
|SCC_OK|Réussite de l’ouverture du projet.|
|SCC_E_INITIALIZEFAILED|Projet n’a pas pu être initialisé.|
|SCC_E_INVALIDUSER|L’utilisateur n’a pas pu se connecter le système de contrôle source.|
|SCC_E_COULDNOTCREATEPROJECT|Le projet n’existait pas avant l’appel ;  le `SCC_OPT_CREATEIFNEW` indicateur a été défini, mais le projet n’a pas pu être créé.|
|SCC_E_PROJSYNTAXERR|Syntaxe de projet non valide.|
|SCC_E_UNKNOWNPROJECT|Le projet est inconnu pour le plug-in de contrôle de code source et le `SCC_OPT_CREATEIFNEW` indicateur n’a pas été défini.|
|SCC_E_INVALIDFILEPATH|Chemin d’accès de fichier non valide ou inutilisable.|
|SCC_E_NOTAUTHORIZED|L’utilisateur n’est pas autorisé à effectuer cette opération.|
|SCC_E_ACCESSFAILURE|Impossible d’accéder au système de contrôle source, probablement en raison de problèmes réseau ou de contention. Une nouvelle tentative est recommandée.|
|SCC_E_NONSPECFICERROR|Une défaillance non spécifique ; le système de contrôle de code source n’a pas été initialisé.|

## <a name="remarks"></a>Notes
 L’IDE peut transmettre un nom d’utilisateur (`lpUser`), ou il peut simplement passer un pointeur vers une chaîne vide. S’il existe un nom d’utilisateur, le plug-in de contrôle de code source doit l’utiliser comme valeur par défaut. Toutefois, si aucun nom n’a été passé, ou si la connexion a échoué avec le nom donné, le plug-in doit inviter l’utilisateur pour vous connecter et retourne le nom valid dans `lpUser` lorsqu’elle reçoit une connexion valide`.` , car le plug-in peut changer la chaîne de nom d’utilisateur , l’IDE sera toujours allouer une mémoire tampon de taille (`SCC_USER_LEN`+ 1 ou SCC_USER_SIZE, qui inclut l’espace pour le terminateur null).

> [!NOTE]
> La première action de l’IDE peut-être être nécessaires pour exécuter peut être un appel à la `SccOpenProject` fonction ou le [SccGetProjPath](../extensibility/sccgetprojpath-function.md). Pour cette raison, les deux d'entre eux ont un identiques `lpUser` paramètre.

 `lpAuxProjPath` et`lpProjName` sont lus à partir du fichier solution, ou ils sont retournés à partir d’un appel à la `SccGetProjPath` (fonction). Ces paramètres contiennent les chaînes qui associe les le plug-in de contrôle de code source avec le projet et sont uniquement explicites pour le plug-in. Si aucune de ces chaînes ne sont dans le fichier solution et que l’utilisateur n’a pas été invité à naviguer (qui retourne une chaîne via la `SccGetProjPath` fonction), l’IDE passe des chaînes vides pour les deux `lpAuxProjPath` et `lpProjName`et attend que ces valeurs à mettre à jour par le plug-in lorsqu’elle retourne.

 `lpTextOutProc` est un pointeur vers une fonction de rappel fournie par l’IDE pour le plug-in en vue d’afficher la sortie du résultat de contrôle de code source. Cette fonction de rappel est décrite en détail dans [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).

> [!NOTE]
> Si le plug-in de contrôle de code source envisage tirer parti de cela, il doit avoir le `SCC_CAP_TEXTOUT` indicateur dans le [SccInitialize](../extensibility/sccinitialize-function.md). Si cet indicateur n’a pas été défini, ou si l’IDE ne prend pas en charge cette fonctionnalité, `lpTextOutProc` sera `NULL`.

 Le `dwFlags` paramètre contrôle le résultat dans le cas où le projet en cours d’ouverture n’existe pas actuellement. Il se compose de deux indicateurs de bits, `SCC_OP_CREATEIFNEW` et `SCC_OP_SILENTOPEN`. Si le projet en cours d’ouverture déjà existe, la fonction ouvre le projet et le retourne `SCC_OK`. Si le projet n’existe pas et si le `SCC_OP_CREATEIFNEW` indicateur est activé, le plug-in de contrôle de code source peut créer le projet dans le système de contrôle source, ouvrez-le et retourner `SCC_OK`. Si le projet n’existe pas et si le `SCC_OP_CREATEIFNEW` indicateur est désactivé, le plug-in doit ensuite vérifier le `SCC_OP_SILENTOPEN` indicateur. Si cet indicateur est désactivée, le plug-in peut inviter l’utilisateur pour un nom de projet. Si cet indicateur est activé, le plug-in doit simplement retourner `SCC_E_UNKNOWNPROJECT`.

## <a name="calling-order"></a>Ordre d’appel
 Dans le cours normal d’événements, le [SccInitialize](../extensibility/sccinitialize-function.md) est appelée en premier pour ouvrir une session de contrôle de code source. Une session peut se composer d’un appel à `SccOpenProject`, suivie d’autres appels de fonction API de plug-in de contrôle de code Source et s’arrête avec un appel à la [SccCloseProject](../extensibility/scccloseproject-function.md). Ces sessions peuvent être répétées plusieurs fois avant la [SccUninitialize](../extensibility/sccuninitialize-function.md) est appelée.

 Si les jeux plug-in de contrôle de la source de la `SCC_CAP_REENTRANT` de transmission en `SccInitialize`, puis la séquence de session ci-dessus peut être répétée autant de fois en parallèle. Différents `pvContext` structures suivre différentes sessions, dans lequel chaque `pvContext` est associé à un projet ouvert à la fois. Selon le`pvContext` paramètre, le plug-in peut déterminer de quel projet référencé dans n’importe quel appel particulier. Si le bit de la fonction `SCC_CAP_REENTRANT` n’est pas définie, nonreentrant plug-ins de contrôle de code source sont limitées dans leur capacité à travailler avec plusieurs projets.

> [!NOTE]
> Le `SCC_CAP_REENTRANT` bits a été introduite dans la version 1.1 de l’API de plug-in de contrôle de Source. Il n’est pas définie ou est ignoré dans la version 1.0, et toutes les version 1.0 source plug-ins de contrôle sont supposés pour être nonreentrant.

## <a name="see-also"></a>Voir aussi
- [Fonctions d’API du plug-in de contrôle de code source](../extensibility/source-control-plug-in-api-functions.md)
- [SccCloseProject](../extensibility/scccloseproject-function.md)
- [SccGetProjPath](../extensibility/sccgetprojpath-function.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)
- [SccUninitialize](../extensibility/sccuninitialize-function.md)
- [Restrictions relatives aux longueurs de chaînes](../extensibility/restrictions-on-string-lengths.md)
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)