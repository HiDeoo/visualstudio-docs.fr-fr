---
title: Débloquer le téléchargement des outils de contrôle à distance
ms.date: 07/19/2018
ms.topic: troubleshooting
helpviewer_keywords:
- remote debugging, unblock download
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a243033bf5831952d83fdf688302651e02b76b7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62903020"
---
# <a name="how-to-unblock-the-download-of-the-remote-tools-on-windows-server"></a>Comment : débloquer le téléchargement des outils de contrôle à distance sur Windows Server

Les paramètres de sécurité par défaut d’Internet Explorer sur Windows Server peuvent prendre beaucoup de temps pour télécharger des composants tels que les outils de contrôle à distance.

* La configuration de sécurité renforcée est activée sur Internet Explorer, ce qui vous empêche d’ouvrir des sites Web et d’accéder aux ressources Web, sauf si le domaine contenant la ressource est explicitement autorisé (c’est-à-dire, approuvé). Bien que vous puissiez désactiver ce paramètre, nous ne le recommandons pas, car il peut présenter un risque pour la sécurité.

* Sur Windows Server 2016, un paramètre par défaut dans **Internet options**  >  **sécurité**  >  **Internet**  >  **Personnalisation du niveau**de  >  **Téléchargement** désactive également les téléchargements de fichiers. Si vous choisissez de télécharger les outils de contrôle à distance directement sur Windows Server, vous devez activer le téléchargement de fichiers.

Pour télécharger les outils sur Windows Server, nous vous recommandons l’un des éléments suivants :

* Téléchargez les outils de contrôle à distance sur un autre ordinateur, tel que celui exécutant Visual Studio, puis copiez le fichier *. exe* sur Windows Server.

* Exécutez le débogueur distant [à partir d’un partage de fichiers](../debugger/remote-debugging.md#fileshare_msvsmon) sur votre ordinateur Visual Studio.

* Téléchargez les outils de contrôle à distance directement sur Windows Server et acceptez les invites pour ajouter des sites de confiance. Les sites Web modernes incluent souvent de nombreuses ressources tierces, ce qui peut entraîner de nombreuses invites. En outre, vous devrez peut-être ajouter manuellement des liens redirigés. Vous pouvez choisir d’ajouter certains des sites de confiance avant de commencer le téléchargement. Accédez à **Options Internet > sécurité > sites de confiance > sites** et ajoutez les sites suivants.

  * visualstudio.microsoft.com
  * download.visualstudio.microsoft.com
  * à propos de : vide

  Pour les versions antérieures du débogueur sur my.visualstudio.com, ajoutez ces sites supplémentaires pour vous assurer que la connexion a réussi :

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline-p.com
  * msft.sts.microsoft.com
  * auth.gfx.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    Si vous choisissez d’ajouter ces domaines lors du téléchargement des outils de contrôle à distance, cliquez sur **Ajouter** quand vous y êtes invité.

    ![Boîte de dialogue contenu bloqué](../debugger/media/remotedbg-blocked-content.png)

    Lorsque vous téléchargez le logiciel, vous recevez des demandes supplémentaires pour accorder l’autorisation de charger divers scripts et ressources de site Web. Sur my.visualstudio.com, nous vous recommandons d’ajouter les domaines supplémentaires pour vous assurer que la connexion a réussi.