---
title: Ajout et suppression de pages de propriétés | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- property pages, adding
- property pages, project subtypes
- property pages, removing
ms.assetid: 34853412-ab8a-4caa-9601-7d0727b2985d
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 98838f09df3094e16d5f1a18263ffdad603ded0b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839781"
---
# <a name="adding-and-removing-property-pages"></a>Ajout et suppression de pages de propriétés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le concepteur de projet fournit un emplacement centralisé pour la gestion des propriétés, des paramètres et des ressources de projet dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] . Il apparaît sous la forme d’une fenêtre unique dans l' [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] environnement de développement intégré (IDE) et contient un certain nombre de volets à droite accessibles par le biais des onglets sur la gauche. Les volets (souvent appelés pages de propriétés) dans le concepteur de projet varient selon le type de projet et le langage. Le concepteur de projet est accessible à l’aide de la commande **Propriétés** du menu **projet** .  
  
 Un sous-type de projet doit souvent afficher des pages de propriétés supplémentaires dans le concepteur de projet. De même, certains sous-types de projet peuvent nécessiter la suppression des pages de propriétés intégrées. Pour effectuer l’une ou l’autre, votre sous-type de projet doit implémenter l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> interface et substituer la <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> méthode. En substituant cette méthode et en utilisant `propId` un paramètre contenant l’une des valeurs de l' <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> énumération, vous pouvez filtrer, ajouter ou supprimer des propriétés de projet. Par exemple, vous devrez peut-être ajouter une page aux pages de propriétés dépendantes de la configuration. Pour ce faire, vous devez filtrer les pages de propriétés dépendantes de la configuration, puis ajouter une nouvelle page à la liste existante.  
  
## <a name="adding-and-removing-property-pages-in-project-designer"></a>Ajout et suppression de pages de propriétés dans le concepteur de projets  
  
#### <a name="to-remove-a-property-page-in-project-designer"></a>Pour supprimer une page de propriétés dans le concepteur de projets  
  
1. Substituez la `GetProperty(uint itemId, int propId, out object property)` méthode pour filtrer les pages de propriétés et obtenir une `clsids` liste.  
  
    ```vb  
    Protected Overrides int GetProperty(uint itemId, int propId, out object property)  
    Protected Overrides Function GetProperty(ByVal itemId As UInteger, ByVal propId As Integer, ByRef [property] As Object) As Integer  
        'Use propId to filter configuration-independent property pages.  
        Select Case propId  
            ....   
            Case CInt(Fix(__VSHPROPID2.VSHPROPID_PropertyPagesCLSIDList))  
                'Get a semicolon-delimited list of clsids of the configuration-independent property pages  
                ErrorHandler.ThrowOnFailure(MyBase.GetProperty(itemId, propId, [property]))  
                   Dim propertyPagesList As String = ((String)[property]).ToUpper(CultureInfo.InvariantCulture)  
                'Remove the property page here  
                   ....  
            ....  
        End Select  
            ....   
        Return MyBase.GetProperty(itemId, propId, [property])  
    End Function  
  
    ```  
  
    ```csharp  
    protected override int GetProperty(uint itemId, int propId, out object property)  
    {  
        //Use propId to filter configuration-independent property pages.  
        switch (propId)  
        {  
            . . . .  
  
            case (int)__VSHPROPID2.VSHPROPID_PropertyPagesCLSIDList:  
                {  
                    //Get a semicolon-delimited list of clsids of the configuration-independent property pages  
                    ErrorHandler.ThrowOnFailure(base.GetProperty(itemId, propId, out property));  
                    string propertyPagesList = ((string)property).ToUpper(CultureInfo.InvariantCulture);  
                    //Remove the property page here  
                    . . . .  
                }  
             . . . .  
         }  
            . . . .  
        return base.GetProperty(itemId, propId, out property);  
    }  
    ```  
  
2. Supprimez la page **événements de build** de la `clsids` liste obtenu.  
  
    ```vb  
    Private buildEventsPageGuid As String = "{1E78F8DB-6C07-4D61-A18F-7514010ABD56}"  
    Private index As Integer = propertyPagesList.IndexOf(buildEventsPageGuid)  
    If index <> -1 Then  
        ' GUIDs are separated by ';' so if you remove the last GUID, also remove the last ';'  
        Dim index2 As Integer = index + buildEventsPageGuid.Length + 1  
        If index2 >= propertyPagesList.Length Then  
            propertyPagesList = propertyPagesList.Substring(0, index).TrimEnd(";"c)  
        Else  
            propertyPagesList = propertyPagesList.Substring(0, index) + propertyPagesList.Substring(index2)  
        End If  
    End If  
    'New property value  
    property = propertyPagesList  
    ```  
  
    ```csharp  
    string buildEventsPageGuid = "{1E78F8DB-6C07-4D61-A18F-7514010ABD56}";  
    int index = propertyPagesList.IndexOf(buildEventsPageGuid);  
    if (index != -1)  
    {  
        // GUIDs are separated by ';' so if you remove the last GUID, also remove the last ';'  
        int index2 = index + buildEventsPageGuid.Length + 1;  
        if (index2 >= propertyPagesList.Length)  
            propertyPagesList = propertyPagesList.Substring(0, index).TrimEnd(';');  
        else  
            propertyPagesList = propertyPagesList.Substring(0, index) + propertyPagesList.Substring(index2);  
    }  
    //New property value  
    property = propertyPagesList;  
    ```  
  
#### <a name="to-add-a-property-page-in-project-designer"></a>Pour ajouter une page de propriétés dans le concepteur de projets  
  
1. Créez une page de propriétés que vous souhaitez ajouter.  
  
    ```vb  
    Class DeployPropertyPage  
            Inherits Form  
            Implements Microsoft.VisualStudio.OLE.Interop.IPropertyPage  
        'Summary: Return a stucture describing your property page.  
        ....   
        Public Sub GetPageInfo(ByVal pPageInfo As Microsoft.VisualStudio.OLE.Interop.PROPPAGEINFO())  
            Dim info As PROPPAGEINFO = New PROPPAGEINFO()  
            info.cb = CUInt(Marshal.SizeOf(GetType(PROPPAGEINFO)))  
            info.dwHelpContext = 0  
            info.pszDocString = Nothing  
            info.pszHelpFile = Nothing  
            info.pszTitle = "Deployment" 'Assign tab name  
            info.SIZE.cx = Me.Size.Width  
            info.SIZE.cy = Me.Size.Height  
            If Not pPageInfo Is Nothing AndAlso pPageInfo.Length > 0 Then  
                pPageInfo(0) = info  
            End If  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    class DeployPropertyPage : Form, Microsoft.VisualStudio.OLE.Interop.IPropertyPage  
    {  
        . . . .   
        //Summary: Return a stucture describing your property page.  
        public void GetPageInfo(Microsoft.VisualStudio.OLE.Interop.PROPPAGEINFO[] pPageInfo)  
        {  
            PROPPAGEINFO info = new PROPPAGEINFO();  
            info.cb = (uint)Marshal.SizeOf(typeof(PROPPAGEINFO));  
            info.dwHelpContext = 0;  
            info.pszDocString = null;  
            info.pszHelpFile = null;  
            info.pszTitle = "Deployment";  //Assign tab name  
            info.SIZE.cx = this.Size.Width;  
            info.SIZE.cy = this.Size.Height;  
            if (pPageInfo != null && pPageInfo.Length > 0)  
                pPageInfo[0] = info;  
        }  
    }  
    ```  
  
2. Inscrivez votre nouvelle page de propriétés.  
  
    ```vb  
    <MSVSIP.ProvideObject(GetType(DeployPropertyPage), RegisterUsing = RegistrationMethod.CodeBase)>  
    ```  
  
    ```csharp  
    [MSVSIP.ProvideObject(typeof(DeployPropertyPage), RegisterUsing = RegistrationMethod.CodeBase)]  
    ```  
  
3. Substituez la `GetProperty(uint itemId, int propId, out object property)` méthode pour filtrer les pages de propriétés, obtenez une `clsids` liste et ajoutez une nouvelle page de propriétés.  
  
    ```vb  
    Protected Overrides Function GetProperty(ByVal itemId As UInteger, ByVal propId As Integer, ByRef [property] As Object) As Integer  
        'Use propId to filter configuration-dependent property pages.  
        Select Case propId  
            ....   
            case CInt(Fix(__VSHPROPID2.VSHPROPID_CfgPropertyPagesCLSIDList)):  
                'Get a semicolon-delimited list of clsids of the configuration-dependent property pages.  
                ErrorHandler.ThrowOnFailure(MyBase.GetProperty(itemId, propId, [property]))  
                'Add the Deployment property page.  
                [property] &= ";"c + GetType(DeployPropertyPage).GUID.ToString("B")  
        End Select  
            ....   
            Return MyBase.GetProperty(itemId, propId, [property])  
    End Function  
    ```  
  
    ```csharp  
    protected override int GetProperty(uint itemId, int propId, out object property)  
    {  
        //Use propId to filter configuration-dependent property pages.  
        switch (propId)  
        {  
            . . . .  
            case (int)__VSHPROPID2.VSHPROPID_CfgPropertyPagesCLSIDList:  
                {  
                    //Get a semicolon-delimited list of clsids of the configuration-dependent property pages.  
                    ErrorHandler.ThrowOnFailure(base.GetProperty(itemId, propId, out property));  
                    //Add the Deployment property page.  
                    property += ';' + typeof(DeployPropertyPage).GUID.ToString("B");  
                }  
         }  
            . . . .  
        return base.GetProperty(itemId, propId, out property);  
    }  
    ```  
  
> [!NOTE]
> Tous les exemples de code fournis dans cette rubrique font partie d’un exemple plus complet, [VSSDK Samples](../misc/vssdk-samples.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Sous-types de projets](../extensibility/internals/project-subtypes.md)
