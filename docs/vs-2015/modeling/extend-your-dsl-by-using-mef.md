---
title: Étendre votre DSL à l’aide de MEF | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e7be79a-53ab-4d79-863a-bef8d27839bd
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: fd5e4727c4352ca27d905bad608c4a1c17284f9b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49930636"
---
# <a name="extend-your-dsl-by-using-mef"></a>Extension de votre DSL à l'aide de MEF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez étendre votre langage spécifique à un domaine (DSL) à l’aide de Managed Extensibility Framework (MEF). Vous ou autres développeurs seront en mesure d’écrire des extensions pour le DSL sans modifier la définition DSL et le code de programme. Ces extensions incluent des commandes de menu, les gestionnaires de glisser-déplacer et la validation. Les utilisateurs pourront installer votre DSL et puis éventuellement installer les extensions pour elle.  
  
 En outre, lorsque vous activez MEF dans votre DSL, il peut être plus facile d’écrire certaines des fonctionnalités de votre DSL, même si elles sont construites avec la solution DSL.  
  
 Pour plus d’informations sur MEF, consultez [Managed Extensibility Framework (MEF)](http://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde).  
  
### <a name="to-enable-your-dsl-to-be-extended-by-mef"></a>Pour activer votre DSL d’être étendue par MEF  
  
1. Créez un dossier nommé **MefExtension** à l’intérieur de la **DslPackage** projet. Ajoutez les fichiers suivants à celui-ci :  
  
    Nom de fichier : `CommandExtensionVSCT.tt`  
  
   > [!IMPORTANT]
   >  Le GUID du jeu de ce fichier pour être le même que le CommandSetId GUID qui est défini dans DslPackage\GeneratedCode\Constants.tt  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#  
   // CmdSet Guid must be defined before master template is included  
   // This Guid must be kept synchronized with the CommandSetId Guid in Constants.tt  
   Guid guidCmdSet = new Guid ("00000000-0000-0000-0000-000000000000");  
   string menuidCommandsExtensionBaseId="0x4000";  
   #>  
   <#@ include file="DslPackage\CommandExtensionVSCT.tt" #>  
   ```  
  
    Nom de fichier : `CommandExtensionRegistrar.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="DslPackage\CommandExtensionRegistrar.tt" #>  
   ```  
  
    Nom de fichier : `ValidationExtensionEnablement.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="DslPackage\ValidationExtensionEnablement.tt" #>  
   ```  
  
    Nom de fichier : `ValidationExtensionRegistrar.tt`  
  
    Si vous ajoutez ce fichier, vous devez activer la validation dans votre DSL à l’aide d’au moins un des commutateurs **EditorValidation** dans l’Explorateur DSL.  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="DslPackage\ValidationExtensionRegistrar.tt" #>  
   ```  
  
    Nom de fichier : `PackageExtensionEnablement.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="DslPackage\PackageExtensionEnablement.tt" #>  
   ```  
  
2. Créez un dossier nommé **MefExtension** à l’intérieur de la **Dsl** projet. Ajoutez les fichiers suivants à celui-ci :  
  
    Nom de fichier : `DesignerExtensionMetaDataAttribute.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="Dsl\DesignerExtensionMetadataAttribute.tt" #>  
   ```  
  
    Nom de fichier : `GestureExtensionEnablement.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="Dsl\GestureExtensionEnablement.tt" #>  
   ```  
  
    Nom de fichier : `GestureExtensionController.tt`  
  
   ```  
   <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
   <#@ include file="Dsl\GestureExtensionController.tt" #>  
   ```  
  
3. Ajoutez la ligne suivante au fichier existant nommé **dslpackage\commands.VSCT**:  
  
   ```  
   <Include href="MefExtension\CommandExtensionVSCT.vsct"/>  
   ```  
  
    Insérez la ligne après existant `<Include>` directive.  
  
4. `Open DslDefinition.dsl.`  
  
5. Dans l’Explorateur DSL, sélectionnez **éditeur\validation**.  
  
6. Dans la fenêtre Propriétés, assurez-vous qu’au moins une des propriétés nommé **utilise...**  est `true`.  
  
7. Dans la barre d’outils Explorateur de solutions, cliquez sur **transformer tous les modèles**.  
  
    Fichiers auxiliaires apparaissent sous chacun des fichiers que vous avez ajouté.  
  
8. Générez et exécutez la solution pour vérifier qu’il est toujours activé.  
  
   Votre solution DSL est maintenant activé pour MEF. Vous pouvez écrire des commandes de menu, les gestionnaires de mouvements et les contraintes de validation en tant qu’extensions MEF. Vous pouvez écrire ces extensions dans votre solution DSL, ainsi que d’autres codes personnalisés. En outre, vous ou autres développeurs peuvent écrire distinct [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Extensions qui étendent votre DSL.  
  
## <a name="creating-an-extension-for-a-mef-enabled-dsl"></a>Création d’une extension d’un DSL prenant en charge de MEF  
 Si vous avez accès à un DSL prenant en charge de MEF créé par vous-même ou quelqu'un d’autre, vous pouvez écrire des extensions pour celui-ci. Les extensions peuvent être utilisées pour ajouter des commandes de menu, des gestionnaires de mouvements ou des contraintes de validation. Pour créer ces extensions, vous utilisez un [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] solution d’Extension (VSIX). La solution comporte deux parties : un projet de bibliothèque de classes qui génère l’assembly de code et un projet VSIX utilisées par les packages de l’assembly.  
  
#### <a name="to-create-a-dsl-extension-vsix"></a>Pour créer une extension DSL VSIX  
  
1. Créez un projet de bibliothèque de classes. Pour ce faire, dans le **nouveau projet** boîte de dialogue, sélectionnez **Visual Basic** ou **Visual C#** , puis sélectionnez **bibliothèque de classes**.  
  
2. Dans le nouveau projet de bibliothèque de classes, ajoutez une référence à l’assembly du DSL.  
  
   - Cet assembly a généralement un nom qui se termine par ». DSL.dll ».  
  
   - Si vous avez accès au projet DSL, vous pouvez trouver le fichier d’assembly sous le répertoire **Dsl\bin\\\\***  
  
   - Si vous avez accès au fichier DSL VSIX, vous pouvez trouver l’assembly en modifiant l’extension de nom de fichier du fichier VSIX par « .zip ». Décompresser le fichier .zip.  
  
3. Ajouter des références aux assemblys .NET suivants :  
  
   -   Microsoft.VisualStudio.Modeling.Sdk.11.0.dll  
  
   -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0.dll  
  
   -   Microsoft.VisualStudio.Modeling.Sdk.Shell.11.0.dll  
  
   -   System.ComponentModel.Composition.dll  
  
   -   System.Windows.Forms.dll  
  
4. Créez un projet VSIX dans la même solution. Pour ce faire, dans le **nouveau projet** boîte de dialogue, développez **Visual Basic** ou **Visual C#**, cliquez sur **extensibilité**, puis sélectionnez  **Projet VSIX**.  
  
5. Dans l’Explorateur de solutions, cliquez sur le projet VSIX, puis sélectionnez **définir comme projet de démarrage**.  
  
6. Dans le nouveau projet, ouvrez **source.extension.vsixmanifest**.  
  
7. Cliquez sur **ajouter du contenu**. Dans la boîte de dialogue, définissez **Type de contenu** à **composant MEF**, et **projet Source** à votre projet de bibliothèque de classes.  
  
8. Ajouter une référence VSIX sur la ligne DSL.  
  
   1. Dans **source.extension.vsixmanifest**, cliquez sur **ajouter une référence**  
  
   2. Dans la boîte de dialogue, cliquez sur **ajouter la charge utile** et recherchez le fichier VSIX du DSL. Le fichier VSIX est intégré dans la solution DSL, ** DslPackage\bin\\\\***.  
  
       Cela permet aux utilisateurs à installer la solution DSL et votre extension en même temps. Si l’utilisateur a déjà installé la solution DSL, seulement votre extension est installée.  
  
9. Passez en revue et mettre à jour les autres champs de **source.extension.vsixmanifest**. Cliquez sur **sélectionner des éditions** et vérifiez que le bon [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] éditions sont définies.  
  
10. Ajoutez le code au projet de bibliothèque de classes. Utilisez les exemples dans la section suivante comme guide.  
  
     Vous pouvez ajouter n’importe quel nombre de commandes, mouvement et les classes de validation.  
  
11. Pour tester l’extension, appuyez sur **F5**. Dans l’instance expérimentale de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], créez ou ouvrez un exemple de fichier de la solution DSL.  
  
## <a name="writing-mef-extensions-for-dsls"></a>Écriture d’extensions MEF pour DSL  
 Vous pouvez écrire des extensions dans le projet de code d’assembly d’une solution d’extension DSL distinct. Vous pouvez également utiliser MEF dans votre projet DslPackage, comme un moyen pratique d’écrire des commandes, des mouvements et code de validation dans le cadre de la solution DSL.  
  
### <a name="menu-commands"></a>Commandes de menu  
 Pour écrire une commande de menu, définissez une classe qui implémente <xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement.ICommandExtension> , le préfixe de la classe avec l’attribut est défini dans votre solution DSL, nommé *Votre_solution_dsl*`CommandExtension`. Vous pouvez écrire plusieurs classes de commande de menu.  
  
 `QueryStatus()` est appelée chaque fois que l’utilisateur clique sur le diagramme. Il doit inspecter la sélection actuelle et affecter `command.Enabled` pour indiquer quand la commande s’applique.  
  
```  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl; // My DSL  
using Company.MyDsl.ExtensionEnablement; // My DSL  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement; // IVsSelectionContext  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement; // ICommandExtension  
  
namespace MyMefExtension  
{  
  // Defined in Dsl\MefExtension\DesignerExtensionMetaDataAttribute.cs:  
  [MyDslCommandExtension]   
  public class MyCommandClass : ICommandExtension  
  {   
    /// <summary>  
    /// Provides access to current document and selection.  
    /// </summary>  
    [Import]  
    IVsSelectionContext SelectionContext { get; set; }  
  
    /// <summary>  
    /// Called when the user selects this command.  
    /// </summary>  
    /// <param name="command"></param>  
    public void Execute(IMenuCommand command)  
    {  
      // Transaction is required if you want to update elements.  
      using (Transaction t = SelectionContext.CurrentStore  
              .TransactionManager.BeginTransaction("fix names"))  
      {  
        foreach (ExampleShape shape in SelectionContext.CurrentSelection)  
        {  
          ExampleElement element = shape.ModelElement as ExampleElement;  
          element.Name = element.Name + " !";  
        }  
        t.Commit();  
      }  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines whether the command should appear.  
    /// This method should set command.Enabled and command.Visible.  
    /// </summary>  
    /// <param name="command"></param>  
    public void QueryStatus(IMenuCommand command)  
    {  
      command.Enabled =  
        command.Visible = (SelectionContext.CurrentSelection.OfType<ExampleShape>().Count() > 0);  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines the text of the command in the menu.  
    /// </summary>  
    public string Text  
    {  
      get { return "My menu command"; }  
    }  
  }  
}  
  
```  
  
### <a name="gesture-handlers"></a>Gestionnaires de mouvements  
 Un gestionnaire de mouvements peut traiter des objets de faire glissés le diagramme à partir de n’importe où, à l’intérieur ou à l’extérieur [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. L’exemple suivant permet à l’utilisateur de faire glisser des fichiers à partir de l’Explorateur Windows sur le diagramme. Il crée des éléments qui contiennent les noms de fichiers.  
  
 Vous pouvez écrire des gestionnaires d’occuper fait glisser à partir d’autres modèles DSL et les modèles UML. Pour plus d’informations, consultez [Comment : ajouter un gestionnaire glisser-déplacer](../modeling/how-to-add-a-drag-and-drop-handler.md).  
  
```  
  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;   
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;   
  
namespace MefExtension  
{  
  [MyDslGestureExtension]  
  class MyGestureExtension : IGestureExtension  
  {  
    public void OnDoubleClick(ShapeElement targetElement, DiagramPointEventArgs diagramPointEventArgs)  
    {  
      System.Windows.Forms.MessageBox.Show("double click!");  
    }  
  
    /// <summary>  
    /// Called when the user drags anything over the diagram.  
    /// Return true if the dragged object can be dropped on the current target.  
    /// </summary>  
    /// <param name="targetMergeElement">The shape or diagram that the mouse is currently over</param>  
    /// <param name="diagramDragEventArgs">Data about the dragged element.</param>  
    /// <returns></returns>  
    public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      // This handler only allows items to be dropped onto the diagram:  
      return targetMergeElement is MefDsl2Diagram &&  
      // And only accepts files dragged from Windows Explorer:  
        diagramDragEventArgs.Data.GetFormats().Contains("FileNameW");  
    }  
  
    /// <summary>  
    /// Called when the user drops an item onto the diagram.  
    /// </summary>  
    /// <param name="targetDropElement"></param>  
    /// <param name="diagramDragEventArgs"></param>  
    public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      MefDsl2Diagram diagram = targetDropElement as MefDsl2Diagram;  
      if (diagram == null) return;  
  
      // This handler only accepts files dragged from Windows Explorer:  
      string[] draggedFileNames = diagramDragEventArgs.Data.GetData("FileNameW") as string[];  
      if (draggedFileNames == null || draggedFileNames.Length == 0) return;   
  
      using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("file names"))  
      {  
        // Create an element to represent each file:  
        foreach (string fileName in draggedFileNames)  
        {  
          ExampleElement element = new ExampleElement(diagram.ModelElement.Partition);  
          element.Name = fileName;  
  
          // This method of adding the new element allows the position  
          // of the shape to be specified:            
          ElementGroup group = new ElementGroup(element);  
          diagram.ElementOperations.MergeElementGroupPrototype(  
            diagram, group.CreatePrototype(), PointD.ToPointF(diagramDragEventArgs.MousePosition));  
        }  
        t.Commit();  
      }  
    }  
  }  
}  
  
```  
  
### <a name="validation-constraints"></a>Contraintes de validation  
 Méthodes de validation sont marquées par le `ValidationExtension` attribut qui est généré par la solution DSL et également par <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute>. La méthode peut apparaître dans n’importe quelle classe qui n’est pas marqué par un attribut.  
  
 Pour plus d’informations, consultez [Validation dans un langage spécifique à un domaine](../modeling/validation-in-a-domain-specific-language.md).  
  
```  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.Validation;  
  
namespace MefExtension  
{  
  class MyValidationExtension // Can be any class.  
  {  
    // SAMPLE VALIDATION METHOD.  
    // All validation methods have the following attributes.  
  
    // Specific to the extended DSL:  
    [MyDslValidationExtension]   
  
    // Determines when validation is applied:  
    [ValidationMethod(  
       ValidationCategories.Save  
     | ValidationCategories.Open  
     | ValidationCategories.Menu)]  
  
    /// <summary>  
    /// When validation is executed, this method is invoked  
    /// for every element in the model that is an instance  
    /// of the second parameter type.  
    /// </summary>  
    /// <param name="context">For reporting errors</param>  
    /// <param name="elementToValidate"></param>  
    private void ValidateClassNames  
      (ValidationContext context,  
       // Type determines to what elements this will be applied:  
       ExampleElement elementToValidate)  
    {   
      // Write code here to test values and links.  
      if (elementToValidate.Name.IndexOf(' ') >= 0)  
      {  
        // Log any unacceptable values:  
        context.LogError(  
          // Description:  
          "Name must not contain spaces"   
          // Error code unique to this type of error:  
          , "MyDsl001"   
          // Element to highlight when user double-clicks error:  
          , elementToValidate);   
} } } }  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Proposent des Extensions de Visual Studio](../extensibility/shipping-visual-studio-extensions.md)   
 [Managed Extensibility Framework (MEF)](http://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)   
 [Comment : ajouter un gestionnaire glisser-déplacer](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Validation dans un langage spécifique à un domaine](../modeling/validation-in-a-domain-specific-language.md)



