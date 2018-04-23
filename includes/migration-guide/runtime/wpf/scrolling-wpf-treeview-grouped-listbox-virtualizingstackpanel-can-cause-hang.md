### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="1d270-101">Rolar um TreeView WPF ou ListBox agrupado em um VirtualizingStackPanel pode causar um travamento</span><span class="sxs-lookup"><span data-stu-id="1d270-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1d270-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1d270-102">Details</span></span>|<span data-ttu-id="1d270-103">Em que a versão do .NET Framework 4.5, rolando um WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> em uma pilha virtualizada painel pode causar a trava se houver margens no visor (entre os itens a <xref:System.Windows.Controls.TreeView?displayProperty=name>, por exemplo, ou em um elemento ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="1d270-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=name> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=name>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="1d270-104">Além disso, em alguns casos, itens de tamanhos diferentes no modo de exibição podem causar instabilidade, mesmo se não houver margens.</span><span class="sxs-lookup"><span data-stu-id="1d270-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>|
|<span data-ttu-id="1d270-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="1d270-105">Suggestion</span></span>|<span data-ttu-id="1d270-106">Esse bug pode ser evitado com a o upgrade para o .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="1d270-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="1d270-107">Como alternativa, as margens podem ser removidas de coleções de exibição (como <xref:System.Windows.Controls.TreeView?displayProperty=name>s) na pilha virtualizada painéis se todos os itens contidos são do mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="1d270-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=name>s) within virtualized stack panels if all contained items are the same size.</span></span>|
|<span data-ttu-id="1d270-108">Escopo</span><span class="sxs-lookup"><span data-stu-id="1d270-108">Scope</span></span>|<span data-ttu-id="1d270-109">Principal</span><span class="sxs-lookup"><span data-stu-id="1d270-109">Major</span></span>|
|<span data-ttu-id="1d270-110">Versão</span><span class="sxs-lookup"><span data-stu-id="1d270-110">Version</span></span>|<span data-ttu-id="1d270-111">4.5</span><span class="sxs-lookup"><span data-stu-id="1d270-111">4.5</span></span>|
|<span data-ttu-id="1d270-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d270-112">Type</span></span>|<span data-ttu-id="1d270-113">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="1d270-113">Runtime</span></span>|
|<span data-ttu-id="1d270-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="1d270-114">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
