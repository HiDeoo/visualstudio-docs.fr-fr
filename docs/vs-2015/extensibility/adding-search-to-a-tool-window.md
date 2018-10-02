---
title: Ajout de la recherche à une fenêtre outil | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tool windows, adding search
ms.assetid: f78c4892-8060-49c4-8ecd-4360f1b4d133
caps.latest.revision: 39
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8bdee40e2af2e09844314cd1727f480b3cd33462
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508518"
---
# <a name="adding-search-to-a-tool-window"></a>Ajout de la recherche dans une fenêtre d’outil
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Ajout d’une recherche à une fenêtre outil](https://docs.microsoft.com/visualstudio/extensibility/adding-search-to-a-tool-window).  
  
Lorsque vous créez ou mettez à jour d’une fenêtre outil dans votre extension, vous pouvez ajouter les mêmes fonctionnalités de recherche apparaît ailleurs dans Visual Studio. Cette fonctionnalité inclut les fonctionnalités suivantes :  
  
-   Une zone de recherche qui se trouve toujours dans une zone personnalisée de la barre d’outils.  
  
-   Un indicateur de progression se superpose à la zone de recherche lui-même.  
  
-   La possibilité d’afficher les résultats dès que vous entrez chaque caractère (recherche instantanée) ou uniquement une fois que vous appuyez sur entrée (recherche à la demande).  
  
-   Une liste qui affiche les termes du contrat pour lequel vous avez recherchées le plus récemment.  
  
-   La possibilité de filtrer les recherches par des champs ou des aspects des cibles de recherche.  
  
 En suivant cette procédure pas à pas, vous allez apprendre à effectuer les tâches suivantes :  
  
1.  Créez un projet VSPackage.  
  
2.  Créer une fenêtre outil qui contient un contrôle utilisateur avec une zone de texte en lecture seule.  
  
3.  Ajoutez une zone de recherche à la fenêtre outil.  
  
4.  Ajoutez l’implémentation de la recherche.  
  
5.  Activer la recherche instantanée et l’affichage d’une barre de progression.  
  
6.  Ajouter un **respecter la casse** option.  
  
7.  Ajouter un **recherche uniquement des lignes mêmes** filtre.  
  
## <a name="to-create-a-vsix-project"></a>Pour créer un projet VSIX  
  
1.  Créez un projet VSIX nommé `TestToolWindowSearch` avec une fenêtre Outil nommée **TestSearch**. Si vous avez besoin d’aide pour cette opération, consultez [création d’une Extension avec une fenêtre outil](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="to-create-a-tool-window"></a>Pour créer une fenêtre outil  
  
1.  Dans le `TestToolWindowSearch` de projet, ouvrez le fichier TestSearchControl.xaml.  
  
2.  Remplacer la `<StackPanel>` bloc avec le bloc suivant, qui ajoute en lecture seule <xref:System.Windows.Controls.TextBox> à la <xref:System.Windows.Controls.UserControl> dans la fenêtre outil.  
  
    ```xaml  
    <StackPanel Orientation="Vertical">  
        <TextBox Name="resultsTextBox" Height="800.0"  
            Width="800.0"  
            IsReadOnly="True">  
        </TextBox>  
    </StackPanel>  
    ```  
  
3.  Dans le fichier TestSearchControl.xaml.cs, ajoutez le code suivant à l’aide d’instruction :  
  
    ```csharp  
    using System.Text;  
    ```  
  
4.  Supprimer le `button1_Click()` (méthode).  
  
     Dans le **TestSearchControl** de classe, ajoutez le code suivant.  
  
     Ce code ajoute un public <xref:System.Windows.Controls.TextBox> propriété nommée **SearchResultsTextBox** et une propriété de chaîne publique nommée **SearchContent**. Dans le constructeur, SearchResultsTextBox est définie sur la zone de texte et SearchContent est initialisé à un ensemble délimité de saut de ligne de chaînes. Le contenu de la zone de texte est également initialisé à l’ensemble de chaînes.  
  
    ```csharp  
    public partial class TestSearchControl : UserControl  
    {  
        public TextBox SearchResultsTextBox { get; set; }  
        public string SearchContent { get; set; }  
  
        public TestSearchControl()  
        {  
            InitializeComponent();  
  
            this.SearchResultsTextBox = resultsTextBox;  
            this.SearchContent = BuildContent();  
  
            this.SearchResultsTextBox.Text = this.SearchContent;  
        }  
  
        private string BuildContent()  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendLine("1 go");  
            sb.AppendLine("2 good");  
            sb.AppendLine("3 Go");  
            sb.AppendLine("4 Good");  
            sb.AppendLine("5 goodbye");  
            sb.AppendLine("6 Goodbye");  
  
            return sb.ToString();  
        }  
    }  
    ```  
  
     [!code-csharp[ToolWindowSearch#1](../snippets/csharp/VS_Snippets_VBCSharp/toolwindowsearch/cs/mycontrol.xaml.cs#1)]
     [!code-vb[ToolWindowSearch#1](../snippets/visualbasic/VS_Snippets_VBCSharp/toolwindowsearch/vb/mycontrol.xaml.vb#1)]  
  
5.  Générez le projet et commencez le débogage. L’instance expérimentale de Visual Studio s’affiche.  
  
6.  Dans la barre de menus, choisissez **vue**, **Windows autres**, **TestSearch**.  
  
     Cette fenêtre outil apparaît, mais le contrôle de recherche n’apparaît pas encore.  
  
## <a name="to-add-a-search-box-to-the-tool-window"></a>Pour ajouter une zone de recherche à la fenêtre outil  
  
1.  Dans le fichier TestSearch.cs, ajoutez le code suivant à la `TestSearch` classe. Le code substitue la <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> propriété afin que l’accesseur get retourne `true`.  
  
     Pour activer la recherche, vous devez substituer la <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> propriété. Le <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> la classe implémente <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch> et fournit une implémentation par défaut qui n’active la recherche.  
  
    ```csharp  
    public override bool SearchEnabled  
    {  
        get { return true; }  
    }  
    ```  
  
2.  Générez le projet et commencez le débogage. L’instance expérimentale s’affiche.  
  
3.  Dans l’instance expérimentale de Visual Studio, ouvrez **TestSearch**.  
  
     En haut de la fenêtre outil, un contrôle de recherche s’affiche avec un **recherche** filigrane et une icône de loupe agrandissement. Toutefois, recherche ne fonctionne pas encore, car le processus de recherche n’a pas été implémenté.  
  
## <a name="to-add-the-search-implementation"></a>Pour ajouter l’implémentation de la recherche  
 Lorsque vous activez la recherche sur un <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>, comme dans la procédure précédente, la fenêtre outil crée un hôte de recherche. Cet hôte configure et gère les processus de recherche, qui sont toujours effectuées sur un thread d’arrière-plan. Étant donné que la <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> classe gère la création de l’hôte de recherche et le paramètre de configuration de la recherche, vous devez uniquement créer une tâche de recherche et fournir la méthode de recherche. Le processus de recherche se produit sur un thread d’arrière-plan, et les appels au contrôle de fenêtre outil se produisent sur le thread d’interface utilisateur. Par conséquent, vous devez utiliser le <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> méthode pour gérer tous les appels que vous apportez dans le traitement avec le contrôle.  
  
1.  Dans le fichier TestSearch.cs, ajoutez le code suivant `using` instructions :  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Runtime.InteropServices;  
    using System.Text;  
    using System.Windows.Controls;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
2.  Dans le `TestSearch` de classe, ajoutez le code suivant, qui effectue les actions suivantes :  
  
    -   Remplace le <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> méthode pour créer une tâche de recherche.  
  
    -   Remplace le <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> méthode pour restaurer l’état de la zone de texte. Cette méthode est appelée lorsqu’un utilisateur annule une tâche de recherche et lorsqu’un utilisateur définit ou unsets options ou filtres. Les deux <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> sont appelées sur le thread d’interface utilisateur. Par conséquent, vous n’avez pas besoin accéder à la zone de texte par le biais de la <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> (méthode).  
  
    -   Crée une classe qui est nommée `TestSearchTask` qui hérite de <xref:Microsoft.VisualStudio.Shell.VsSearchTask>, qui fournit une implémentation par défaut de <xref:Microsoft.VisualStudio.Shell.Interop.IVsSearchTask>.  
  
         Dans `TestSearchTask`, le constructeur définit un champ privé qui fait référence à la fenêtre outil. Pour fournir la méthode de recherche, vous substituez le <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> et <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStopSearch%2A> méthodes. Le <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> méthode est de vous mettre en place le processus de recherche. Ce processus inclut la recherche, affichage des résultats de recherche dans la zone de texte et appeler l’implémentation de classe de base de cette méthode pour signaler que la recherche est terminée.  
  
    ```csharp  
    public override IVsSearchTask CreateSearch(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback)  
    {  
        if (pSearchQuery == null || pSearchCallback == null)  
            return null;  
         return new TestSearchTask(dwCookie, pSearchQuery, pSearchCallback, this);  
    }  
  
    public override void ClearSearch()  
    {  
        TestSearchControl control = (TestSearchControl)this.Content;  
        control.SearchResultsTextBox.Text = control.SearchContent;  
    }  
  
    internal class TestSearchTask : VsSearchTask  
    {  
        private TestSearch m_toolWindow;  
  
        public TestSearchTask(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback, TestSearch toolwindow)  
            : base(dwCookie, pSearchQuery, pSearchCallback)  
        {  
            m_toolWindow = toolwindow;  
        }  
  
        protected override void OnStartSearch()  
        {  
            // Use the original content of the text box as the target of the search.   
            var separator = new string[] { Environment.NewLine };  
            TestSearchControl control = (TestSearchControl)m_toolWindow.Content;  
            string[] contentArr = control.SearchContent.Split(separator, StringSplitOptions.None);  
  
            // Get the search option.   
            bool matchCase = false;  
            // matchCase = m_toolWindow.MatchCaseOption.Value;   
  
                // Set variables that are used in the finally block.  
                StringBuilder sb = new StringBuilder("");  
                uint resultCount = 0;  
                this.ErrorCode = VSConstants.S_OK;  
  
                try  
                {  
                    string searchString = this.SearchQuery.SearchString;  
  
                    // Determine the results.   
                    uint progress = 0;  
                    foreach (string line in contentArr)  
                    {  
                        if (matchCase == true)  
                        {  
                            if (line.Contains(searchString))  
                            {  
                                sb.AppendLine(line);  
                                resultCount++;  
                            }  
                        }  
                        else  
                            {  
                                if (line.ToLower().Contains(searchString.ToLower()))  
                                {  
                                    sb.AppendLine(line);  
                                    resultCount++;  
                                }  
                            }  
  
                            // SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));   
  
                            // Uncomment the following line to demonstrate the progress bar.   
                            // System.Threading.Thread.Sleep(100);  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        this.ErrorCode = VSConstants.E_FAIL;  
                    }  
                    finally  
                    {  
                        ThreadHelper.Generic.Invoke(() =>  
                        { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
                        this.SearchResults = resultCount;  
                    }  
  
            // Call the implementation of this method in the base class.   
            // This sets the task status to complete and reports task completion.   
            base.OnStartSearch();  
        }  
  
        protected override void OnStopSearch()  
        {  
            this.SearchResults = 0;  
        }  
    }  
    ```  
  
3.  Tester votre implémentation de la recherche en effectuant les étapes suivantes :  
  
    1.  Régénérez le projet et démarrer le débogage.  
  
    2.  Dans l’instance expérimentale de Visual Studio, ouvrez la fenêtre outil à nouveau, entrez du texte de recherche dans la fenêtre de recherche, cliquez sur ENTRÉE.  
  
         Les résultats corrects doivent apparaître.  
  
## <a name="to-customize-the-search-behavior"></a>Pour personnaliser le comportement de recherche  
 En modifiant les paramètres de recherche, vous pouvez apporter différentes des modifications dans la façon dont le contrôle de recherche s’affiche et la façon dont la recherche est effectuée. Par exemple, vous pouvez modifier le filigrane (le texte par défaut qui s’affiche dans la zone de recherche), la valeur minimale et la largeur maximale du contrôle de recherche et s’il faut afficher une barre de progression. Vous pouvez également modifier le point sur les résultats de recherche démarrent (à la demande ou sur la recherche instantanée) et s’il faut afficher une liste de termes pour lesquels vous avez recherchées récemment. Vous trouverez la liste complète des paramètres dans le <xref:Microsoft.VisualStudio.PlatformUI.SearchSettingsDataSource> classe.  
  
1.  Dans le fichier TestSearch.cs, ajoutez le code suivant à la `TestSearch` classe. Ce code permet la recherche instantanée au lieu de la recherche à la demande (ce qui signifie que l’utilisateur n’a pas de cliquer sur entrée). Le code substitue la `ProvideSearchSettings` méthode dans le `TestSearch` (classe), qui est nécessaire pour modifier les paramètres par défaut.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
            (uint)VSSEARCHSTARTTYPE.SST_INSTANT);}  
    ```  
  
2.  Tester la nouvelle définition de la régénération de la solution et redémarrer le débogueur.  
  
     Affichage des résultats chaque fois que vous entrez un caractère dans la zone de recherche.  
  
3.  Dans le `ProvideSearchSettings` (méthode), ajoutez la ligne suivante, qui permet d’afficher une barre de progression.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
             (uint)VSSEARCHSTARTTYPE.SST_INSTANT);  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchProgressTypeProperty.Name,   
             (uint)VSSEARCHPROGRESSTYPE.SPT_DETERMINATE);  
    }  
    ```  
  
     Pour la barre de progression s’affichent, la progression doit être signalée. Pour signaler la progression, supprimez le code suivant dans le `OnStartSearch` méthode de la `TestSearchTask` classe :  
  
    ```csharp  
    SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
    ```  
  
4.  Ralentissement de la progression du traitement suffisamment qui barre est visible, supprimez les commentaires de la ligne suivante dans le `OnStartSearch` méthode de la `TestSearchTask` classe :  
  
    ```csharp  
    System.Threading.Thread.Sleep(100);  
    ```  
  
5.  Les nouveaux paramètres de test par la régénération de la solution et commencer à debugb.  
  
     La barre de progression apparaît dans la fenêtre de recherche (comme une ligne bleue sous la zone de texte de recherche) chaque fois que vous effectuez une recherche.  
  
## <a name="to-enable-users-to-refine-their-searches"></a>Pour permettre aux utilisateurs d’affiner leurs recherches  
 Vous pouvez autoriser les utilisateurs à affiner leurs recherches au moyen des options telles que **respecter la casse** ou **mot entier**. Options peuvent être booléennes, qui apparaissent comme des cases à cocher, ou des commandes qui s’affichent sous forme de boutons. Pour cette procédure pas à pas, vous allez créer une option booléenne.  
  
1.  Dans le fichier TestSearch.cs, ajoutez le code suivant à la `TestSearch` classe. Le code substitue la `SearchOptionsEnum` (méthode), ce qui permet l’implémentation de la recherche détecter si une option donnée est activé ou désactivé. Le code dans `SearchOptionsEnum` ajoute une option pour respecter la casse pour un <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumWindowSearchOptions> énumérateur. L’option pour respecter la casse est également mises à disposition en tant que le `MatchCaseOption` propriété.  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
        {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
2.  Dans le `TestSearchTask` (classe), supprimez les commentaires de ligne matchCase dans le `OnStartSearch` méthode :  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
         {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
3.  L’option de test :  
  
    1.  Générez le projet et commencez le débogage. L’instance expérimentale s’affiche.  
  
    2.  Dans la fenêtre outil, cliquez sur la flèche bas sur le côté droit de la zone de texte.  
  
         Le **respecter la casse** case à cocher s’affiche.  
  
    3.  Sélectionnez le **respecter la casse** case à cocher, puis effectuer des recherches.  
  
## <a name="to-add-a-search-filter"></a>Pour ajouter un filtre de recherche  
 Vous pouvez ajouter des filtres de recherche qui permettent aux utilisateurs affiner l’ensemble des cibles de recherche. Par exemple, vous pouvez filtrer les fichiers dans l’Explorateur de fichiers par les dates sur lequel ils ont été modifiés plus récemment et leurs extensions de nom de fichier. Dans cette procédure pas à pas, vous allez ajouter un filtre de lignes paires uniquement. Lorsque l’utilisateur choisit ce filtre, l’hôte de recherche ajoute les chaînes que vous spécifiez à la requête de recherche. Vous pouvez identifier ces chaînes à l’intérieur de votre méthode de recherche, puis filtrer les cibles de recherche en conséquence.  
  
1.  Dans le fichier TestSearch.cs, ajoutez le code suivant à la `TestSearch` classe. Le code implémente `SearchFiltersEnum` en ajoutant un <xref:Microsoft.VisualStudio.PlatformUI.WindowSearchSimpleFilter> qui spécifie pour filtrer les résultats de recherche de façon à afficher uniquement les lignes de mêmes.  
  
    ```csharp  
    public override IVsEnumWindowSearchFilters SearchFiltersEnum  
    {  
        get  
        {  
            List<IVsWindowSearchFilter> list = new List<IVsWindowSearchFilter>();  
            list.Add(new WindowSearchSimpleFilter("Search even lines only", "Search even lines only", "lines", "even"));  
            return new WindowSearchFilterEnumerator(list) as IVsEnumWindowSearchFilters;  
        }  
    }  
  
    ```  
  
     Maintenant le contrôle de recherche affiche le filtre de recherche `Search even lines only`. Quand l’utilisateur choisit le filtre, la chaîne `lines:"even"` s’affiche dans la zone de recherche. Autres critères de recherche peuvent apparaître en même temps que le filtre. Chaînes de recherche peuvent apparaître avant le filtre, après le filtre, ou les deux.  
  
2.  Dans le fichier TestSearch.cs, ajoutez les méthodes suivantes pour le `TestSearchTask` (classe), qui se trouve dans le `TestSearch` classe. Ces méthodes prennent en charge le `OnStartSearch` (méthode), que vous modifierez à l’étape suivante.  
  
    ```csharp  
    private string RemoveFromString(string origString, string stringToRemove)  
    {  
        int index = origString.IndexOf(stringToRemove);  
        if (index == -1)  
            return origString;  
        else   
             return (origString.Substring(0, index) + origString.Substring(index + stringToRemove.Length)).Trim();  
    }  
  
    private string[] GetEvenItems(string[] contentArr)  
    {  
        int length = contentArr.Length / 2;  
        string[] evenContentArr = new string[length];  
  
        int indexB = 0;  
        for (int index = 1; index < contentArr.Length; index += 2)  
        {  
            evenContentArr[indexB] = contentArr[index];  
            indexB++;  
        }  
  
        return evenContentArr;  
    }  
    ```  
  
3.  Dans le `TestSearchTask` class, mettre à jour le `OnStartSearch` méthode avec le code suivant. Ce changement met à jour le code pour prendre en charge le filtre.  
  
    ```csharp  
    protected override void OnStartSearch()  
    {  
        // Use the original content of the text box as the target of the search.   
        var separator = new string[] { Environment.NewLine };  
        string[] contentArr = ((TestSearchControl)m_toolWindow.Content).SearchContent.Split(separator, StringSplitOptions.None);  
  
        // Get the search option.   
        bool matchCase = false;  
        matchCase = m_toolWindow.MatchCaseOption.Value;  
  
        // Set variables that are used in the finally block.  
        StringBuilder sb = new StringBuilder("");  
        uint resultCount = 0;  
        this.ErrorCode = VSConstants.S_OK;  
  
        try  
        {  
            string searchString = this.SearchQuery.SearchString;  
  
            // If the search string contains the filter string, filter the content array.   
            string filterString = "lines:\"even\"";  
  
            if (this.SearchQuery.SearchString.Contains(filterString))  
            {  
                // Retain only the even items in the array.  
                contentArr = GetEvenItems(contentArr);  
  
                // Remove 'lines:"even"' from the search string.  
                searchString = RemoveFromString(searchString, filterString);  
            }  
  
            // Determine the results.   
            uint progress = 0;  
            foreach (string line in contentArr)  
            {  
                if (matchCase == true)  
                {  
                    if (line.Contains(searchString))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
                else  
                {  
                    if (line.ToLower().Contains(searchString.ToLower()))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
  
                SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
  
                // Uncomment the following line to demonstrate the progress bar.   
                // System.Threading.Thread.Sleep(100);  
            }  
        }  
        catch (Exception e)  
        {  
            this.ErrorCode = VSConstants.E_FAIL;  
        }  
        finally  
        {  
            ThreadHelper.Generic.Invoke(() =>  
            { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
            this.SearchResults = resultCount;  
        }  
  
        // Call the implementation of this method in the base class.   
        // This sets the task status to complete and reports task completion.   
        base.OnStartSearch();  
    }  
    ```  
  
4.  Testez votre code.  
  
5.  Générez le projet et commencez le débogage. Dans l’instance expérimentale de Visual Studio, ouvrez la fenêtre outil, puis choisissez la flèche vers le bas sur le contrôle de recherche.  
  
     Le **respecter la casse** case à cocher et le **recherche uniquement des lignes mêmes** filtre s’affichent.  
  
6.  Choisissez le filtre.  
  
     La zone de recherche contient **lignes : « même »**, et les résultats suivants s’affichent :  
  
     2 bon  
  
     4 bonne  
  
     Adieu 6  
  
7.  Supprimer `lines:"even"` dans la zone de recherche, sélectionnez le **respecter la casse** case à cocher, puis entrez `g` dans la zone de recherche.  
  
     Les résultats suivants s’affichent :  
  
     1 go  
  
     2 bon  
  
     Adieu 5  
  
8.  Cliquez sur le X situé à droite de la zone de recherche.  
  
     La recherche est désactivée, et le contenu d’origine s’affiche. Toutefois, le **respecter la casse** est toujours activée.

