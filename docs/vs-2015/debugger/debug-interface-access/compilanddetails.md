---
title: CompilandDetails | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CompilandDetails symbol
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37468ba708ded9d1fd0b976fd3771d1a18291d71
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266628"
---
# <a name="compilanddetails"></a>CompilandDetails
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Informations de compiland sont réparties entre les symboles avec un `SymTagCompiland` balise (détail faible) et un `SymTagCompilandDetails` balise (beaucoup de détails). `SymTagCompilandDetails` nécessite le chargement de symboles supplémentaires. Toutefois, il fournit une mine d’informations sur le module qui n’est pas disponible avec un `SymTagCompiland` symbole.  
  
## <a name="properties"></a>Properties  
 Le tableau suivant présente les propriétés qui sont valides pour ce type de symbole.  
  
|Propriété|Type de données|Description|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_backEndBuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|Numéro de build de back-end du compilateur.|  
|[IDiaSymbol::get_backEndMajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|Numéro de version principale de back-end du compilateur.|  
|[IDiaSymbol::get_backEndMinor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|Numéro de version secondaire de back-end du compilateur.|  
|[IDiaSymbol::get_compilerName](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|Nom du compilateur qui a généré cette compiland (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE` Si Modifier & Continuer a été activé à la compilation.|  
|[IDiaSymbol::get_frontEndBuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|Numéro de build frontal du compilateur.|  
|[IDiaSymbol::get_frontEndMajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|Numéro de version principale frontal du compilateur.|  
|[IDiaSymbol::get_frontEndMinor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|Numéro de version mineure frontal du compilateur.|  
|[IDiaSymbol::get_hasDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|`TRUE` Si cette compiland a des informations de débogage (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasManagedCode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|`TRUE` Si cette compiland contient du code managé (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE` Si le module a été compilé avec le [/GS (vérification de la sécurité de la mémoire tampon)](http://msdn.microsoft.com/library/8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e) commutateur de compilateur (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_isCVTCIL](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|`TRUE` Si compiland a été converti à partir du code de langage CIL (Common Intermediate) en code natif.|  
|[IDiaSymbol::get_isDataAligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|`TRUE` Si les types définis par l’utilisateur (UDT) ont été alignées sur certaines spécifiées des limites de mémoire (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_isHotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|`TRUE` Si compiland a été compilé avec le [/hotpatch (créer une Image corrigeable en mémoire)](http://msdn.microsoft.com/library/aad539b6-c053-4c78-8682-853d98327798) commutateur de compilateur (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_isLTCG](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|`TRUE` Si compiland a été compilé avec le [/LTCG (Link-time Code Generation)](http://msdn.microsoft.com/library/788c6f52-fdb8-40c2-90af-4026ea2cf2e2) commutateur de compilateur (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_isMSILNetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|TRUE si compiland est un module de langage MSIL (Microsoft Intermediate Language) (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|Langage de code source.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbole du module.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID du symbole lexicale parente.|  
|[IDiaSymbol::get_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|Plateforme sur laquelle le module a été compilé (parmi les [CV_CPU_TYPE_e (énumération)](../../debugger/debug-interface-access/cv-cpu-type-e.md) valeurs).|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID d’index de symbole.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Retourne `SymTagCompilandDetails` (parmi les [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) valeurs).|  
  
## <a name="remarks"></a>Notes  
 Les compilateurs utilisent souvent dans un formulaire appelé un compilateur deux passes ; dans certaines versions du compilateur, chaque passage est gérée par un programme distinct. Ceux-ci sont connus comme les compilateurs frontaux et principaux, respectivement, par conséquent, les symboles de propriété pour les numéros de version principal et frontal.  
  
## <a name="see-also"></a>Voir aussi  
 [Compiland](../../debugger/debug-interface-access/compiland.md)   
 [Hiérarchie lexicale des types de symboles](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)



