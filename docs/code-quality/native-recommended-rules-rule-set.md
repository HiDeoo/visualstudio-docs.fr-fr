---
title: Ensemble de règles des règles recommandées natives
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 12e9e271e0fd6881ae19581a1678f131719c4b34
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882800"
---
# <a name="native-recommended-rules-rule-set"></a>Ensemble de règles des règles recommandées natives

Les règles recommandées natives vous concentrer sur les problèmes plus fréquents et critiques dans votre code natif, notamment les failles de sécurité potentielles et les blocages d’application. Vous devez inclure cet ensemble de règles dans tout ensemble de règles personnalisé que vous créez pour vos projets natifs.

|Règle|Description|
|----------|-----------------|
|[C6001](../code-quality/c6001.md)|Utilisation d'une mémoire non initialisée|
|[C6011](../code-quality/c6011.md)|Déréférencement du pointeur Null|
|[C6029](../code-quality/c6029.md)|Utilisation d'une valeur non vérifiée|
|[C6031](../code-quality/c6031.md)|Valeur de retour ignorée|
|[C6053](../code-quality/c6053.md)|Terminaison par zéro de l'appel|
|[C6054](../code-quality/c6054.md)|Terminaison par zéro manquante|
|[C6059](../code-quality/c6059.md)|Concaténation non valide|
|[C6063](../code-quality/c6063.md)|Argument de chaîne manquant pour le formatage de la fonction|
|[C6064](../code-quality/c6064.md)|Argument d’entier manquant pour le formatage de la fonction|
|[C6066](../code-quality/c6066.md)|Argument de pointeur manquant pour le formatage de la fonction|
|[C6067](../code-quality/c6067.md)|Argument de pointeur de chaîne manquant pour le formatage de la fonction|
|[C6101](../code-quality/c6101.md)|Retour d'une mémoire non initialisée|
|[C6200](../code-quality/c6200.md)|L'index dépasse la taille maximale autorisée par la mémoire tampon|
|[C6201](../code-quality/c6201.md)|L'index dépasse la taille maximale autorisée par la mémoire tampon allouée par la pile|
|[C6214](../code-quality/c6214.md)|Cast de HRESULT vers BOOL non valide|
|[C6215](../code-quality/c6215.md)|Cast de BOOL vers HRESULT non valide|
|[C6216](../code-quality/c6216.md)|Cast inséré par le compilateur BOOL vers HRESULT non valide|
|[C6217](../code-quality/c6217.md)|Test HRESULT non valide avec NOT|
|[C6220](../code-quality/c6220.md)|Comparaison HRESULT non valide-1|
|[C6226](../code-quality/c6226.md)|Affectation de HRESULT non valide-1|
|[C6230](../code-quality/c6230.md)|Utilisation HRESULT non valide en tant que valeur booléenne|
|[C6235](../code-quality/c6235.md)|Constante non nulle avec opérateur logique- ou|
|[C6236](../code-quality/c6236.md)|Logique- ou avec une constante Non nulle|
|[C6237](../code-quality/c6237.md)|Zéro avec opérateur logique- et perd ses effets|
|[C6242](../code-quality/c6242.md)|Déroulement local provoqué|
|[C6248](../code-quality/c6248.md)|Créer des DACL Null|
|[C6250](../code-quality/c6250.md)|Descripteurs d’adresses non commercialisés|
|[C6255](../code-quality/c6255.md)|Utilisation non protégée d’Alloca|
|[C6258](../code-quality/c6258.md)|À l’aide de terminer le Thread|
|[C6259](../code-quality/c6259.md)|Code mort dans au niveau du bit- ou limités de commutateur|
|[C6260](../code-quality/c6260.md)|Utilisation des opérations arithmétiques sur les octets|
|[C6262](../code-quality/c6262.md)|Utilisation excessive de la pile|
|[C6263](../code-quality/c6263.md)|Utilisation d’Alloca dans une boucle|
|[C6268](../code-quality/c6268.md)|Parenthèses manquantes dans le Cast|
|[C6269](../code-quality/c6269.md)|Déréférencement du pointeur ignoré|
|[C6270](../code-quality/c6270.md)|Argument float manquant pour le formatage de la fonction|
|[C6271](../code-quality/c6271.md)|Argument supplémentaire pour le formatage de la fonction|
|[C6272](../code-quality/c6272.md)|Argument non float pour le formatage de la fonction|
|[C6273](../code-quality/c6273.md)|Argument non entier pour la fonction Format|
|[C6274](../code-quality/c6274.md)|Argument autre qu’un caractère pour le formatage de la fonction|
|[C6276](../code-quality/c6276.md)|Cast de chaîne non valide|
|[C6277](../code-quality/c6277.md)|Appel CreateProcess non valide|
|[C6278](../code-quality/c6278.md)|Incompatibilité de tableau New et scalaire Delete|
|[C6279](../code-quality/c6279.md)|Incompatibilité entre tableau scalaire-New-Delete|
|[C6280](../code-quality/c6280.md)|Incompatibilité d’Allocation et désallocation de mémoire|
|[C6281](../code-quality/c6281.md)|Priorité de Relation au niveau du bit|
|[C6282](../code-quality/c6282.md)|L’affectation remplace le Test|
|[C6283](../code-quality/c6283.md)|Incompatibilité primitive de tableau New et scalaire Delete|
|[C6284](../code-quality/c6284.md)|Argument d’objet non valide pour le formatage de la fonction|
|[C6285](../code-quality/c6285.md)|Logique- ou des constantes|
|[C6286](../code-quality/c6286.md)|Différent de zéro logique- ou perte des effets secondaires|
|[C6287](../code-quality/c6287.md)|Test redondant|
|[C6288](../code-quality/c6288.md)|L’Inclusion mutuelle sur logique- et a la valeur False|
|[C6289](../code-quality/c6289.md)|L’Exclusion mutuelle sur logique- ou a la valeur True|
|[C6290](../code-quality/c6290.md)|Priorité NOT logique et AND au niveau du bit|
|[C6291](../code-quality/c6291.md)|Priorité NOT logique et OR au niveau du bit|
|[C6292](../code-quality/c6292.md)|La boucle calcule à partir de la valeur maximale|
|[C6293](../code-quality/c6293.md)|Boucle calcule à partir de Minimum|
|[C6294](../code-quality/c6294.md)|Corps de la boucle jamais exécuté|
|[C6295](../code-quality/c6295.md)|Boucle infinie|
|[C6296](../code-quality/c6296.md)|Boucle exécutée une fois|
|[C6297](../code-quality/c6297.md)|Effectuer un Cast du résultat du décalage à plus grande taille|
|[C6299](../code-quality/c6299.md)|Champ de bits et comparaison booléenne|
|[C6302](../code-quality/c6302.md)|Argument de chaîne de caractères non valide pour le formatage de la fonction|
|[C6303](../code-quality/c6303.md)|Argument de chaîne de caractères larges non valide pour le formatage de la fonction|
|[C6305](../code-quality/c6305.md)|Incompatibilité entre la taille et la quantité|
|[C6306](../code-quality/c6306.md)|Appel de fonction d’argument de variable non valide|
|[C6308](../code-quality/c6308.md)|Fuite de réallocation|
|[C6310](../code-quality/c6310.md)|Constante de filtre d’Exception non conforme|
|[C6312](../code-quality/c6312.md)|L’exception Continue la boucle d’exécution|
|[C6314](../code-quality/c6314.md)|Au niveau du bit- priorité|
|[C6317](../code-quality/c6317.md)|Complément not Not|
|[C6318](../code-quality/c6318.md)|L’exception Continue la recherche|
|[C6319](../code-quality/c6319.md)|Ignoré par des virgules|
|[C6324](../code-quality/c6324.md)|Copie d’une chaîne au lieu de la comparaison de chaînes|
|[C6328](../code-quality/c6328.md)|Incompatibilité de type d’argument possible|
|[C6331](../code-quality/c6331.md)|Indicateurs VirtualFree n’est pas valide|
|[C6332](../code-quality/c6332.md)|Paramètre non valide de VirtualFree|
|[C6333](../code-quality/c6333.md)|Taille de VirtualFree n’est pas valide|
|[C6335](../code-quality/c6335.md)|Handle de processus|
|[C6381](../code-quality/c6381.md)|Informations de l’arrêt manquantes|
|[C6383](../code-quality/c6383.md)|Nombre d’éléments Byte-dépassement de mémoire tampon de nombre|
|[C6384](../code-quality/c6384.md)|Division de taille du pointeur|
|[C6385](../code-quality/c6385.md)|Dépassement en lecture|
|[C6386](../code-quality/c6386.md)|Dépassement en écriture|
|[C6387](../code-quality/c6387.md)|Valeur de paramètre non valide|
|[C6388](../code-quality/c6388.md)|Valeur de paramètre non valide|
|[C6500](../code-quality/c6500.md)|Propriété d'attribut non valide|
|[C6501](../code-quality/c6501.md)|Valeurs de propriété d'attribut en conflit|
|[C6503](../code-quality/c6503.md)|Les références ne peuvent pas être Null|
|[C6504](../code-quality/c6504.md)|Null sur élément non pointeur|
|[C6505](../code-quality/c6505.md)|MustCheck sur Void|
|[C6506](../code-quality/c6506.md)|Taille de mémoire tampon sur élément non pointeur ou tableau|
|[C6508](../code-quality/c6508.md)|Accès en écriture sur constante|
|[C6509](../code-quality/c6509.md)|Retour utilisé sur condition préalable|
|[C6510](../code-quality/c6510.md)|Terminaison par Null sur élément non pointeur|
|[C6511](../code-quality/c6511.md)|MustCheck doit avoir la valeur Yes ou No|
|[C6513](../code-quality/c6513.md)|Taille d'élément sans taille de mémoire tampon|
|[C6514](../code-quality/c6514.md)|Taille de mémoire tampon dépasse la taille du tableau|
|[C6515](../code-quality/c6515.md)|Taille de la mémoire tampon sur élément non pointeur|
|[C6516](../code-quality/c6516.md)|Attribut sans propriété|
|[C6517](../code-quality/c6517.md)|Taille valide dans mémoire tampon non lisible|
|[C6518](../code-quality/c6518.md)|Taille accessible en écriture dans mémoire tampon non accessible en écriture|
|[C6522](../code-quality/c6522.md)|Type de chaîne de taille non valide|
|[C6525](../code-quality/c6525.md)|Chaîne de taille non valide. Emplacement inaccessible|
|[C6527](../code-quality/c6527.md)|Annotation non valide : Propriété de 'NeedsRelease' ne peut pas être utilisée sur les valeurs de type void|
|[C6530](../code-quality/c6530.md)|Style de chaîne de format non reconnu|
|[C6540](../code-quality/c6540.md)|L'utilisation des annotations d'attribut sur cette fonction rendra non valides toutes ses annotations __declspec existantes|
|[C6551](../code-quality/c6551.md)|Spécification de taille non valide : expression impossible à analyser|
|[C6552](../code-quality/c6552.md)|Deref= ou Noref= non valide : expression impossible à analyser|
|[C6701](../code-quality/c6701.md)|La valeur n'est pas une valeur Yes/No/Maybe valide|
|[C6702](../code-quality/c6702.md)|La valeur n'est pas une valeur de chaîne|
|[C6703](../code-quality/c6703.md)|La valeur n'est pas un nombre|
|[C6704](../code-quality/c6704.md)|Erreur d'expression de l'annotation inattendue|
|[C6705](../code-quality/c6705.md)|Le nombre d’arguments attendu pour l’annotation ne correspond pas au nombre réel d’arguments pour l’annotation|
|[C6706](../code-quality/c6706.md)|Erreur d'annotation inattendue pour l'annotation|
|[C6995](../code-quality/c6995.md)|Impossible d’enregistrer le fichier journal XML|
|[C26100](../code-quality/c26100.md)|Condition de concurrence|
|[C26101](../code-quality/c26101.md)|Absence d’utilisation de l’opération à blocage correctement|
|[C26110](../code-quality/c26110.md)|Appelant ne parvenant pas à maintenir le verrou|
|[C26111](../code-quality/c26111.md)|Appelant ne parvenant pas à libérer le verrou|
|[C26112](../code-quality/c26112.md)|L’appelant ne peut pas maintenir aucun verrou|
|[C26115](../code-quality/c26115.md)|Échec de libération de verrou|
|[C26116](../code-quality/c26116.md)|Échec d’acquisition ou à maintenir le verrou|
|[C26117](../code-quality/c26117.md)|Libération du verrou|
|[C26140](../code-quality/c26140.md)|Erreur d’annotation SAL d’accès concurrentiel|
|[C26441](../code-quality/c26441.md)|NO_UNNAMED_GUARDS|
|[C26444](../code-quality/c26444.md)|NO_UNNAMED_RAII_OBJECTS|
|[C26498](../code-quality/c26498.md)|USE_CONSTEXPR_FOR_FUNCTIONCALL|
|[C28020](../code-quality/c28020.md)|L’expression n’est pas vraie dans cet appel|
|[C28021](../code-quality/c28021.md)|Le paramètre annoté doit être un pointeur|
|[C28022](../code-quality/c28022.md)|Les classes de fonction sur cette fonction ne correspondent pas les classes de fonction sur le typedef utilisé pour la définir.|
|[C28023](../code-quality/c28023.md)|La fonction assignée ou passée doit avoir un \_fonction\_classe\_ annotation pour au moins l’une des classes|
|[C28024](../code-quality/c28024.md)|Le pointeur de fonction assigné à est annoté avec la classe de fonction, ce qui n’est pas contenue dans la liste de classes de fonction.|
|[C28039](../code-quality/c28039.md)|Le type de paramètre réel doit correspondre exactement au type|
|[C28112](../code-quality/c28112.md)|Une variable qui est accessible via une fonction Interlocked doit toujours être accessible via une fonction Interlocked.|
|[C28113](../code-quality/c28113.md)|Accès à une variable locale via une fonction Interlocked|
|[C28125](../code-quality/c28125.md)|La fonction doit être appelée à partir de dans un bloc try / except bloc|
|[C28137](../code-quality/c28137.md)|L’argument de variable doit être à la place d’une constante (littérale)|
|[C28138](../code-quality/c28138.md)|L’argument de la constante doit plutôt être une variable|
|[C28159](../code-quality/c28159.md)|Envisagez plutôt d’utiliser une autre fonction.|
|[C28160](../code-quality/c28160.md)|annotation d'erreur|
|[C28163](../code-quality/c28163.md)|La fonction ne doit jamais être appelée à partir de dans un bloc try / except bloc|
|[C28164](../code-quality/c28164.md)|L’argument est passé à une fonction qui attend un pointeur vers un objet (pas un pointeur vers un pointeur)|
|[C28182](../code-quality/c28182.md)|Déréférencement du pointeur NULL. Le pointeur contient la même valeur NULL qu'un autre pointeur.|
|[C28183](../code-quality/c28183.md)|L’argument pouvait être une valeur, et est une copie de la valeur trouvée dans le pointeur|
|[C28193](../code-quality/c28193.md)|La variable contient une valeur qui doit être examinée.|
|[C28196](../code-quality/c28196.md)|L’exigence n’est pas satisfaite. (L’expression ne correspond pas à la valeur true).|
|[C28202](../code-quality/c28202.md)|Référence non autorisée à un membre non statique|
|[C28203](../code-quality/c28203.md)|Référence ambiguë à un membre de classe.|
|[C28205](../code-quality/c28205.md)|\_Réussite\_ ou \_sur\_échec\_ utilisé dans un contexte non autorisé|
|[C28206](../code-quality/c28206.md)|L’opérande de gauche pointe vers un struct, utiliser '->'|
|[C28207](../code-quality/c28207.md)|L’opérande de gauche est un struct, utiliser '.'|
|[C28209](../code-quality/c28209.md)|La déclaration de symbole possède une déclaration en conflit|
|[C28210](../code-quality/c28210.md)|Les annotations pour le contexte __on_failure ne doivent pas se trouver dans un contexte préalable explicite|
|[C28211](../code-quality/c28211.md)|Nom du contexte statique attendu pour SAL_context|
|[C28212](../code-quality/c28212.md)|Expression de pointeur attendue pour l'annotation|
|[C28213](../code-quality/c28213.md)|Le \_utilisation\_decl\_annotations\_ annotation doit être utilisée pour référencer, sans modification, une déclaration antérieure.|
|[C28214](../code-quality/c28214.md)|Les noms des paramètres d'attribut doivent être p1...p9|
|[C28215](../code-quality/c28215.md)|Le typefix ne peut pas être appliqué à un paramètre qui contient déjà un typefix|
|[C28216](../code-quality/c28216.md)|L'annotation checkReturn ne s'applique qu'aux post-conditions pour le paramètre de fonction spécifique.|
|[C28217](../code-quality/c28217.md)|Pour la fonction, le nombre de paramètres de l'annotation ne correspond pas au nombre trouvé dans le fichier|
|[C28218](../code-quality/c28218.md)|Pour le paramètre de fonction, paramètre de l’annotation ne correspond pas trouvé dans le fichier|
|[C28219](../code-quality/c28219.md)|Membre de l'énumération attendu pour une annotation, le paramètre dans l'annotation|
|[C28220](../code-quality/c28220.md)|Expression d'entier attendue pour une annotation, le paramètre dans l'annotation|
|[C28221](../code-quality/c28221.md)|Expression de chaîne attendue pour le paramètre dans l'annotation|
|[C28222](../code-quality/c28222.md)|__yes, \__no ou \__maybe attendus pour l’annotation|
|[C28223](../code-quality/c28223.md)|Jeton/identificateur introuvable pour l'annotation, paramètre|
|[C28224](../code-quality/c28224.md)|L'annotation requiert des paramètres|
|[C28225](../code-quality/c28225.md)|Nombre correct de paramètres requis introuvable dans l'annotation|
|[C28226](../code-quality/c28226.md)|L'annotation ne peut pas être également un PrimOp (dans la déclaration actuelle)|
|[C28227](../code-quality/c28227.md)|L'annotation ne peut pas être également un PrimOp (voir la déclaration antérieure)|
|[C28228](../code-quality/c28228.md)|Paramètre d'annotation : impossible d'utiliser ce type dans les annotations|
|[C28229](../code-quality/c28229.md)|L'annotation ne prend pas en charge les paramètres|
|[C28230](../code-quality/c28230.md)|Le type de paramètre ne contient pas de membre.|
|[C28231](../code-quality/c28231.md)|L'annotation n'est valide que sur un tableau|
|[C28232](../code-quality/c28232.md)|pre, post, ou deref ne sont appliqués à aucune annotation|
|[C28233](../code-quality/c28233.md)|pre, post ou deref sont appliqués à un bloc|
|[C28234](../code-quality/c28234.md)|l'expression __at ne s'applique pas à la fonction actuelle|
|[C28235](../code-quality/c28235.md)|La fonction ne peut pas constituer à elle seule une annotation|
|[C28236](../code-quality/c28236.md)|L'annotation ne peut pas être utilisée dans une expression|
|[C28237](../code-quality/c28237.md)|L'annotation sur le paramètre n'est plus prise en charge|
|[C28238](../code-quality/c28238.md)|Plusieurs value, stringValue et longValue sont définies dans l'annotation sur le paramètre. Utiliser paramn=xxx|
|[C28239](../code-quality/c28239.md)|value, stringValue ou longValue, et paramn=xxx sont définis en même temps dans l'annotation sur le paramètre. Utiliser uniquement paramn=xxx|
|[C28240](../code-quality/c28240.md)|L'annotation sur le paramètre possède un param2, mais pas de param1|
|[C28241](../code-quality/c28241.md)|L'annotation pour la fonction sur le paramètre n'est pas reconnue|
|[C28243](../code-quality/c28243.md)|L’annotation pour la fonction sur le paramètre nécessite plus de déréférencements que le type réel annoté ne le permet.|
|[C28244](../code-quality/c28244.md)|L’annotation pour la fonction a une annotation de paramètre/externe non analysable|
|[C28245](../code-quality/c28245.md)|L’annotation pour la fonction annote ’this’ sur une fonction non membre|
|[C28246](../code-quality/c28246.md)|L'annotation du paramètre ne correspond pas au type du paramètre|
|[C28250](../code-quality/c28250.md)|Annotation incohérente pour une fonction : l'instance précédente contient une erreur.|
|[C28251](../code-quality/c28251.md)|Annotation incohérente pour une fonction : cette instance contient une erreur.|
|[C28252](../code-quality/c28252.md)|Annotation incohérente pour une fonction : le paramètre contient d'autres annotations sur cette instance.|
|[C28253](../code-quality/c28253.md)|Annotation incohérente pour une fonction : le paramètre contient d'autres annotations sur cette instance.|
|[C28254](../code-quality/c28254.md)|dynamic_cast<>() n'est pas pris en charge dans les annotations|
|[C28262](../code-quality/c28262.md)|Une erreur de syntaxe dans l'annotation a été trouvée dans la fonction, pour l'annotation|
|[C28263](../code-quality/c28263.md)|Une erreur de syntaxe dans une annotation conditionnelle a été trouvée pour l'annotation intrinsèque|
|[C28267](../code-quality/c28267.md)|Une erreur de syntaxe dans les annotations a été trouvée pour l'annotation dans la fonction.|
|[C28272](../code-quality/c28272.md)|L'annotation pour la fonction, paramètre pendant la vérification est incohérente avec la déclaration de fonction|
|[C28273](../code-quality/c28273.md)|Pour la fonction, les indices sont incohérents avec la déclaration de fonction|
|[C28275](../code-quality/c28275.md)|Le paramètre \_Macro\_valeur\_ a la valeur null|
|[C28279](../code-quality/c28279.md)|Pour le symbole, un 'begin' a été trouvé sans le 'end' correspondant|
|[C28280](../code-quality/c28280.md)|Pour le symbole, un 'end' a été trouvé sans le 'begin' correspondant|
|[C28282](../code-quality/c28282.md)|Les chaînes de format doivent être comprises dans des conditions préalables|
|[C28285](../code-quality/c28285.md)|Pour la fonction, erreur de syntaxe dans le paramètre|
|[C28286](../code-quality/c28286.md)|Pour la fonction, erreur de syntaxe près de la fin|
|[C28287](../code-quality/c28287.md)|Pour la fonction, erreur de syntaxe dans l’annotation \_At\_() (nom de paramètre non reconnu)|
|[C28288](../code-quality/c28288.md)|Pour la fonction, erreur de syntaxe dans l’annotation \_At\_() (nom de paramètre non valide)|
|[C28289](../code-quality/c28289.md)|Pour la fonction : ReadableTo ou WritableTo n’avait pas une spécification de limite en tant que paramètre|
|[C28290](../code-quality/c28290.md)|l'annotation pour la fonction contient plus d'Externals que le nombre réel de paramètres|
|[C28291](../code-quality/c28291.md)|post null/notnull au niveau 0 deref n'a pas de sens pour la fonction.|
|[C28300](../code-quality/c28300.md)|Opérandes d’expression de types incompatibles pour l’opérateur|
|[C28301](../code-quality/c28301.md)|Aucune annotation pour la première déclaration de la fonction.|
|[C28302](../code-quality/c28302.md)|Un opérateur \_Deref\_ en trop a été trouvé dans une annotation.|
|[C28303](../code-quality/c28303.md)|Un opérateur ambigu \_Deref\_ a été trouvé dans une annotation.|
|[C28304](../code-quality/c28304.md)|Un opérateur \_Notref\_ placé de manière incorrecte et appliqué à un jeton a été trouvé.|
|[C28305](../code-quality/c28305.md)|Une erreur a été détectée pendant l'analyse d'un jeton.|
|[C28306](../code-quality/c28306.md)|L’annotation sur paramètre est obsolète|
|[C28307](../code-quality/c28307.md)|L’annotation sur paramètre est obsolète|
|[C28350](../code-quality/c28350.md)|L'annotation décrit une situation qui n'est pas applicable de manière conditionnelle.|
|[C28351](../code-quality/c28351.md)|L'annotation décrit l'emplacement auquel une valeur dynamique (une variable) ne peut pas être utilisée dans la condition.|