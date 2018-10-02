---
title: 'Comment : créer un Document XML basé sur un schéma XSD | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7ce870506097c820d5a6a8e981ffd63d64257780
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47494312"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Procédure : créer un document XML basé sur un schéma XSD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : créer un Document XML basé sur un schéma XSD](https://docs.microsoft.com/visualstudio/xml-tools/how-to-create-an-xml-document-based-on-an-xsd-schema).  
  
  
Le **générer un exemple de code XML** fonctionnalité génère un exemple de fichier XML en fonction de votre fichier de schéma XSD (XML).  
  
 Vous pouvez utiliser cette option dans les scénarios suivants :  
  
-   Comprendre l'utilisation des diverses constructions dans votre schéma.  
  
-   confirmer la finalité du schéma.  
  
 Le **générer un exemple de code XML** fonctionnalité est disponible uniquement sur les éléments globaux et nécessite un jeu de schémas XML valid.  
  
 En règle générale, cette fonctionnalité permet de générer des documents XML valides. Toutefois, si le schéma contient un ou plusieurs des éléments suivants, l'exemple risque de ne pas être valide :  
  
-   Contraintes d'identité `xs:key`, `xs:keyref` et `xs:unique`.  
  
-   Facettes `xs:pattern`.  
  
-   Énumérations du type `xs:QName`.  
  
-   Types `xs:ENTITY`, `xs:ENTITIES` et `xs:NOTATION`.  
  
 Notez également que le contenu `xs:base64Binary` n'est généré que si des énumérations figurent dans le schéma du type correspondant.  
  
### <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Pour générer un document d'instance XML basé sur le fichier XSD  
  
1.  Suivez les étapes de [Comment : créer et modifier un fichier de schéma XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  Dans le [Explorateur de schémas XML](../xml-tools/xml-schema-explorer.md), avec le bouton droit le `PurchaseOrder` élément global. Sélectionnez **générer l’exemple de code XML**.  
  
     Lorsque vous sélectionnez cette option, le fichier PurchaseOrder.xml avec l'exemple de contenu XML suivant est généré et ouvert dans l'Éditeur XML :  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">  
      <ShipTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </ShipTo>  
      <ShipTo country="US">  
        <name>name2</name>  
        <street>street2</street>  
        <city>city2</city>  
        <state>state2</state>  
        <zip>-79228162514264337593543950335</zip>  
      </ShipTo>  
      <BillTo country="US">  
        <name>name1</name>  
        <street>street1</street>  
        <city>city1</city>  
        <state>state1</state>  
        <zip>1</zip>  
      </BillTo>  
    </PurchaseOrder>  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de données XML](../xml-tools/working-with-xml-data.md)



