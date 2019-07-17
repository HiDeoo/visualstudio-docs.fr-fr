---
title: Fonction SccCheckin | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccCheckin
helpviewer_keywords:
- SccCheckin function
ms.assetid: e3f26ac2-6163-42e1-a764-22cfea5a3bc6
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d8a5a91a0300f256b66970403a3431edf0fe757e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189534"
---
# <a name="scccheckin-function"></a>Fonction SccCheckin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette fonction vérifie dans les fichiers précédemment extraits vers le système de contrôle source, enregistrer les modifications et la création d’une nouvelle version. Cette fonction est appelée avec un nombre et un tableau de noms des fichiers à archiver.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccCheckin (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPSTR*    lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pvContext  
 [in] La structure de contexte de plug-in de contrôle de source.  
  
 hWnd  
 [in] Handle vers la fenêtre de l’IDE que le plug-in de SCC peut utiliser en tant que parent pour les boîtes de dialogue qu’il fournit.  
  
 nFiles  
 [in] Nombre de fichiers sélectionnés pour être archivé.  
  
 lpFileNames  
 [in] Tableau des noms de chemin d’accès local complet des fichiers à archiver.  
  
 lpComment  
 [in] Commentaire à appliquer à chacun des fichiers sélectionnés en cours d’archivage. Il s’agit de `NULL` si le plug-in de contrôle de code source doit demander un commentaire.  
  
 fOptions  
 [in] Indicateurs de commande, soit 0 ou `SCC_KEEP_CHECKEDOUT`.  
  
 pvOptions  
 [in] Options spécifiques au plug-in de contrôle de code source.  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|`Value`|Description|  
|-----------|-----------------|  
|SCC_OK|Fichiers a été extrait.|  
|SCC_E_FILENOTCONTROLLED|Le fichier sélectionné n’est pas sous contrôle de code source.|  
|SCC_E_ACCESSFAILURE|Impossible d’accéder au système de contrôle source, probablement en raison de problèmes réseau ou de contention. Une nouvelle tentative est recommandée.|  
|SCC_E_NONSPECIFICERROR|Erreur non spécifique. Fichier n’a pas été activé.|  
|SCC_E_NOTCHECKEDOUT|L’utilisateur n’a pas extrait le fichier, donc ne peut pas archiver.|  
|SCC_E_CHECKINCONFLICT|Archivage n’a pas pu être effectuée car :<br /><br /> -Un autre utilisateur a archivé à l’avance et `bAutoReconcile` a la valeur false.<br /><br /> ou<br /><br /> -La fusion automatique ne peut pas être effectuée (par exemple, lorsque les fichiers sont binaires).|  
|SCC_E_VERIFYMERGE|Fichier a été fusionnée automatique mais n’a pas été archivé en attente de vérification de l’utilisateur.|  
|SCC_E_FIXMERGE|Fichier a été fusionnée automatique mais n’a pas été archivé en raison d’un conflit de fusion qui doit être résolu manuellement.|  
|SCC_E_NOTAUTHORIZED|L’utilisateur n’est pas autorisé à effectuer cette opération.|  
|SCC_I_OPERATIONCANCELED|Opération a été annulée avant la fin.|  
|SCC_I_RELOADFILE|Un fichier ou un projet doit être rechargé.|  
|SCC_E_FILENOTEXIST|Fichier local est introuvable.|  
  
## <a name="remarks"></a>Notes  
 Le commentaire s’applique à tous les fichiers en cours d’archivage. L’argument de commentaire peut être un `null` string, auquel cas le plug-in de contrôle de code source peut inviter l’utilisateur pour une chaîne de commentaire pour chaque fichier.  
  
 Le `fOptions` argument peut recevoir une valeur de la `SCC_KEEP_CHECKEDOUT` indicateur pour indiquer l’intention de l’utilisateur à archiver le fichier et l’extraire à nouveau.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API du plug-in de contrôle de code source](../extensibility/source-control-plug-in-api-functions.md)
