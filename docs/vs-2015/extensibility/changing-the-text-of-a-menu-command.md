---
title: Modification du texte d’une commande de menu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, changing text
- text, menus
- commands, changing text
ms.assetid: 5cb676a0-c6e2-47e5-bd2b-133dc8842e46
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d8fd3fc01a5dd3e10e633b876b719695d6b26c18
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184494"
---
# <a name="changing-the-text-of-a-menu-command"></a>Modification du texte d’une commande de menu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les étapes suivantes montrent comment modifier l’étiquette de texte d’une commande de menu à l’aide du <xref:System.ComponentModel.Design.IMenuCommandService> service.  
  
## <a name="changing-a-menu-command-label-with-the-imenucommandservice"></a>Modification d’une étiquette de commande de menu avec IMenuCommandService  
  
1. Créez un projet VSIX nommé `MenuText` à l’aide d’une commande de menu nommée **ChangeMenuText**. Pour plus d’informations, consultez [création d’une extension à l’aide d’une commande de menu](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2. Dans le fichier. vstc, ajoutez l' `TextChanges` indicateur à votre commande de menu, comme indiqué dans l’exemple suivant.  
  
    ```xml  
    <Button guid="guidChangeMenuTextPackageCmdSet" id="ChangeMenuTextId" priority="0x0100" type="Button">  
        <Parent guid="guidChangeMenuTextPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <CommandFlag>TextChanges</CommandFlag>  
        <Strings>  
            <ButtonText>Invoke ChangeMenuText</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
3. Dans le fichier ChangeMenuText.cs, créez un gestionnaire d’événements qui sera appelé avant l’affichage de la commande de menu.  
  
    ```csharp  
    private void OnBeforeQueryStatus(object sender, EventArgs e)  
    {  
        var myCommand = sender as OleMenuCommand;  
        if (null != myCommand)  
        {  
            myCommand.Text = "New Text";  
                    }  
    }  
    ```  
  
     Vous pouvez également mettre à jour l’état de la commande de menu dans cette méthode en modifiant les <xref:System.ComponentModel.Design.MenuCommand.Visible%2A> <xref:System.ComponentModel.Design.MenuCommand.Checked%2A> Propriétés, et <xref:System.ComponentModel.Design.MenuCommand.Enabled%2A> sur l' <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> objet.  
  
4. Dans le constructeur ChangeMenuText, remplacez l’initialisation de la commande d’origine et le code de placement par du code qui crée un <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> (au lieu d’un `MenuCommand` ) qui représente la commande de menu, ajoute le <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> Gestionnaire d’événements et donne la commande de menu au service de commande de menu.  
  
     Voici à quoi elle doit ressembler :  
  
    ```csharp  
    private ChangeMenuText(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
        OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
            EventHandler eventHandler = this.ShowMessageBox;  
            OleMenuCommand menuItem = new OleMenuCommand(ShowMessageBox, menuCommandID);  
            menuItem.BeforeQueryStatus +=  
                new EventHandler(OnBeforeQueryStatus);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
5. Générez le projet et commencez le débogage. L’instance expérimentale de Visual Studio s’affiche.  
  
6. Dans le menu **Outils** , vous devez voir une commande appelée **appeler ChangeMenuText**.  
  
7. Cliquez sur la commande. La boîte de message s’affiche pour annoncer que MenuItemCallback a été appelé. Lorsque vous fermez la boîte de message, vous devez voir que le nom de la commande dans le menu outils est désormais **nouveau texte**.
