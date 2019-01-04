---
title: 'Procédure : Créer un document XML basé sur un schéma XSD'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d675695b3d3e054d14e481c8c41ae06de5af5600
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53820197"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Procédure : Créer un document XML basé sur un schéma XSD

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

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Pour générer un document d'instance XML basé sur le fichier XSD

1.  Suivez les étapes de [Comment : Créer et modifier un fichier de schéma XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2.  Dans le [Explorateur de schémas XML](../xml-tools/xml-schema-explorer.md), avec le bouton droit le `PurchaseOrder` élément global. Sélectionnez **générer l’exemple de code XML**.

     Lorsque vous sélectionnez cette option, PurchaseOrder. *xml* fichier avec l’exemple de contenu XML suivant est généré et ouvert dans l’éditeur XML :

    ```xml
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

- [Utilisation des données XML](../xml-tools/working-with-xml-data.md)