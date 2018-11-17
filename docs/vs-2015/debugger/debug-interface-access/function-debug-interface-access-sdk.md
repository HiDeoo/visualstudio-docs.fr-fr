---
title: Fonction (SDK Debug Interface Access) | Microsoft Docs
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
- Function symbol
ms.assetid: 458dc91c-b78b-4427-84f4-615d89e26760
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21b618a01cd439c1176cea65d14dcc0c270f37d7
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741570"
---
# <a name="function-debug-interface-access-sdk"></a>Fonction (Kit de développement logiciel de Debug Interface Access)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Chaque fonction est identifiée par un `SymTagFunction` symbole.  
  
## <a name="properties"></a>Properties  
 Le tableau suivant présente les propriétés qui sont valides pour ce type de symbole.  
  
|Propriété|`Data type`|Description|  
|--------------|-----------------|-----------------|  
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Une des valeurs de la [CV_access_e (énumération)](../../debugger/debug-interface-access/cv-access-e.md), si la fonction est une fonction membre.|  
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|Partie du décalage de l’emplacement ; Pour plus d’informations, consultez le [LocationType (énumération)](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|Partie de section d’emplacement ; Pour plus d’informations, consultez le [LocationType (énumération)](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbole de la classe, si la fonction est une fonction membre.|  
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID du symbole classe parent.|  
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE` Si la fonction est marquée en tant que constante.|  
|[IDiaSymbol::get_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE` Si la fonction utilise une convention d’appel personnalisée (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE` Si la fonction effectue un retour far (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasAlloca](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|`BOOL`|`TRUE` Si la fonction utilise la fonction de la mémoire allouée (uniquement uinnder DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasEH](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|`BOOL`|`TRUE` Si la fonction contient un style C++ des exceptions (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasEHa](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|`BOOL`|`TRUE` Si la fonction contient des exceptions asynchrones (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasInlAsm](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|`BOOL`|`TRUE` Si la fonction contient un assembly inline (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasLongJump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|`BOOL`|`TRUE` Si la fonction contient un [longjmp](http://msdn.microsoft.com/library/0e13670a-5130-45c1-ad69-6862505b7a2f) appeler (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE` Si la fonction contient des contrôles de sécurité (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasSEH](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|`BOOL`|`TRUE` Si la fonction contient un style Win32 structurée des exceptions (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_hasSetJump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|`BOOL`|`TRUE` Si la fonction contient un [setjmp](http://msdn.microsoft.com/library/684a8b27-e8eb-455b-b4a8-733ca1cbd7d2) appeler (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE` Si la fonction a un retour d’interruption (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|`TRUE` Si une fonction est intro virtuel.|  
|[IDiaSymbol::get_InlSpec](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|`BOOL`|`TRUE` Si la fonction a été marquée avec l’un de le [inline, __inline, \__forceinline](../../misc/inline-inline-forceinline.md) attributs.|  
|[IDiaSymbol::get_isNaked](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|`BOOL`|`TRUE` Si la fonction est marquée avec le [naked](http://msdn.microsoft.com/library/69723241-05e1-439b-868e-20a83a16ab6d) attribut (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE` Si la fonction est statique (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Nombre d’octets de code de fonction, en commençant à partir de l’emplacement.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbole de la compiland englobant.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID du symbole lexicale parente.|  
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|Les fonctions peuvent avoir des emplacements statique ou les métadonnées ; Pour plus d’informations, consultez [emplacements de symboles](../../debugger/debug-interface-access/symbol-locations.md).|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Nom de la fonction.|  
|[IDiaSymbol::get_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE` Si la fonction n’est pas une fonction inline (uniquement n DIA SDK version 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE` Si la fonction n’est pas accessible (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE` Si la fonction ne retourne pas une valeur (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_noStackOrdering](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|`BOOL`|`TRUE` Si la fonction a été compilée avec les vérifications de sécurité de mémoire tampon, mais aucun classement de la pile ne peut être effectué.|  
|[IDiaSymbol::get_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE` Si le code a des informations de débogage pour le code optimisé (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|`TRUE` Si la fonction est purement virtuel.|  
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|Position relative de cette fonction au sein de son module.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID d’index de symbole.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Retourne `SymTagFunction` (parmi les [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) valeurs).|  
|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|Jeton de métadonnées pour la fonction.|  
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbole de la signature de fonction.|  
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID de symbole du type.|  
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE` Si la fonction n’est pas alignée.|  
|[IDiaSymbol::get_undecoratedName](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|`BSTR`|La forme non décorée du nom de fonction (uniquement dans DIA SDK 8.0 ou version ultérieure)|  
|[IDiaSymbol::get_undecoratedNameEx](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|`BSTR`|Tout ou partie de la forme non décorée du nom de fonction (uniquement dans DIA SDK 8.0 ou version ultérieure).|  
|[IDiaSymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE` Si une fonction virtuelle.|  
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|Position de cette fonction au sein de l’image exécutable.|  
|[IDiaSymbol::get_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|Si une fonction virtuelle, puis le décalage dans la table de fonctions virtuelles.|  
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE` Si la fonction est marquée comme volatile.|  
  
## <a name="see-also"></a>Voir aussi  
 [CV_access_e (énumération)](../../debugger/debug-interface-access/cv-access-e.md)   
 [Hiérarchie lexicale des Types de symboles](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType (énumération)](../../debugger/debug-interface-access/locationtype.md)   
 [Emplacements des symboles](../../debugger/debug-interface-access/symbol-locations.md)



