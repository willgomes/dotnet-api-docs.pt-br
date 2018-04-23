### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="cb706-101">WorkflowDesigner.Load não remove a propriedade de símbolo</span><span class="sxs-lookup"><span data-stu-id="cb706-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cb706-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cb706-102">Details</span></span>|<span data-ttu-id="cb706-103">Durante o direcionamento do .NET Framework 4.5 no designer de fluxo de trabalho e carregar um fluxo de trabalho 3.5 re-hospedado com o <xref:System.Activities.Presentation.WorkflowDesigner.Load> método, uma <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> é gerada ao salvar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cb706-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="cb706-104">Sugestão</span><span class="sxs-lookup"><span data-stu-id="cb706-104">Suggestion</span></span>|<span data-ttu-id="cb706-105">Esse bug manifestos somente durante o direcionamento do .NET Framework 4.5 no designer de fluxo de trabalho, portanto ele pode ser contornado definindo o <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> para Framework.Alternatively o .NET 4.0, o problema pode ser evitado usando o <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> método ao carregar o fluxo de trabalho em vez de <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="cb706-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="cb706-106">Escopo</span><span class="sxs-lookup"><span data-stu-id="cb706-106">Scope</span></span>|<span data-ttu-id="cb706-107">Principal</span><span class="sxs-lookup"><span data-stu-id="cb706-107">Major</span></span>|
|<span data-ttu-id="cb706-108">Versão</span><span class="sxs-lookup"><span data-stu-id="cb706-108">Version</span></span>|<span data-ttu-id="cb706-109">4.5</span><span class="sxs-lookup"><span data-stu-id="cb706-109">4.5</span></span>|
|<span data-ttu-id="cb706-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb706-110">Type</span></span>|<span data-ttu-id="cb706-111">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="cb706-111">Retargeting</span></span>|
|<span data-ttu-id="cb706-112">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="cb706-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|
