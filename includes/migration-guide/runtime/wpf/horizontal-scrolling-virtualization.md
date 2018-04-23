### <a name="horizontal-scrolling-and-virtualization"></a><span data-ttu-id="d427e-101">Rolagem horizontal e a virtualização</span><span class="sxs-lookup"><span data-stu-id="d427e-101">Horizontal scrolling and virtualization</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d427e-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d427e-102">Details</span></span>|<span data-ttu-id="d427e-103">Essa alteração se aplica a um <xref:System.Windows.Controls.ItemsControl?displayProperty=name> que faz a sua própria virtualização na direção ortogonal para a direção da rolagem principal (o exemplo principal é <xref:System.Windows.Controls.DataGrid?displayProperty=name> com EnableColumnVirtualization =&quot;True&quot;).</span><span class="sxs-lookup"><span data-stu-id="d427e-103">This change applies to an <xref:System.Windows.Controls.ItemsControl?displayProperty=name> that does its own virtualization in the direction orthogonal to the main scrolling direction (the chief example is <xref:System.Windows.Controls.DataGrid?displayProperty=name> with EnableColumnVirtualization=&quot;True&quot;).</span></span>  <span data-ttu-id="d427e-104">O resultado de determinadas operações de rolagem horizontais foi alterado para produzir resultados mais intuitiva e mais semelhante para os resultados das operações verticais comparáveis. As operações incluem &quot;rolagem aqui&quot; e &quot;borda direita&quot;, use o nome do menu obtido clicando em uma barra de rolagem horizontal.</span><span class="sxs-lookup"><span data-stu-id="d427e-104">The outcome of certain horizontal scrolling operations has been changed to produce results that are more intuitive and more analogous to the results of comparable vertical operations.The operations include &quot;Scroll Here&quot; and &quot;Right Edge&quot;, to use the names from the menu obtained by right-clicking a horizontal scrollbar.</span></span>  <span data-ttu-id="d427e-105">Ambos computar um deslocamento de candidato e chamada <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>. Depois de rolagem para o deslocamento de novo, a noção de &quot;aqui&quot; ou &quot;direita borda&quot; pode ter sido alterado porque recentemente eliminação virtualizado conteúdo foi alterado o valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name>. Antes de .net 4.6.2, a operação de rolagem simplesmente usa o deslocamento de candidato, mesmo que ele não pode ser &quot;aqui&quot; ou o &quot;direita borda&quot; mais.</span><span class="sxs-lookup"><span data-stu-id="d427e-105">Both of these compute a candidate offset and call <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.After scrolling to the new offset, the notion of &quot;here&quot; or &quot;right edge&quot; may have changed because newly de-virtualized content has changed the value of <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name>.Prior to .Net 4.6.2, the scroll operation simply uses the candidate offset, even though it may not be &quot;here&quot; or at the &quot;right edge&quot; any more.</span></span>  <span data-ttu-id="d427e-106">Isso resulta em efeitos como &quot;saltando&quot; thumb rolagem, melhor ilustrado pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="d427e-106">This results in effects like &quot;bouncing&quot; the scroll thumb, best illustrated by example.</span></span> <span data-ttu-id="d427e-107">Suponha que um <xref:System.Windows.Controls.DataGrid?displayProperty=name> tem ExtentWidth = 1000 e largura = 200.</span><span class="sxs-lookup"><span data-stu-id="d427e-107">Suppose a <xref:System.Windows.Controls.DataGrid?displayProperty=name> has ExtentWidth=1000 and Width=200.</span></span>  <span data-ttu-id="d427e-108">Uma rolagem para &quot;borda direita&quot; candidato usa deslocamento 1000 200 = 800.</span><span class="sxs-lookup"><span data-stu-id="d427e-108">A scroll to &quot;Right Edge&quot; uses candidate offset 1000 - 200 = 800.</span></span>  <span data-ttu-id="d427e-109">Durante a rolagem para esse deslocamento, novas colunas são de-virtualizado; Vamos supor que eles são muito largos, para que o <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> altera a 2000.</span><span class="sxs-lookup"><span data-stu-id="d427e-109">While scrolling to that offset, new columns are de- virtualized; let's suppose they are very wide, so that the <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> changes to 2000.</span></span>  <span data-ttu-id="d427e-110">A rolagem termina com HorizontalOffset = 800 e elevador &quot;bounces&quot; para próximo ao meio da barra de rolagem - precisamente em 800/2000 = 40%. A alteração é recompilar um novo deslocamento de candidato quando essa situação ocorre e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="d427e-110">The scroll ends with HorizontalOffset=800, and the thumb &quot;bounces&quot; back to near the middle of the scrollbar - precisely at 800/2000 = 40%.The change is to recompute a new candidate offset when this situation occurs, and try again.</span></span> <span data-ttu-id="d427e-111">(Isso é a rolagem vertical como funciona já.) A alteração produz uma experiência mais previsível e intuitiva para o usuário final, mas ele também pode afetar qualquer aplicativo que depende do valor exato de <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> após um horizontal de rolagem, se invocado pelo usuário final ou por uma chamada explícita para <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.</span><span class="sxs-lookup"><span data-stu-id="d427e-111">(This is how vertical scrolling works already.)The change produces a more predictable and intuitive experience for the end user, but it could also affect any app that depends on the exact value of <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> after a horizontal scroll, whether invoked by the end user or by an explicit call to <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.</span></span>|
|<span data-ttu-id="d427e-112">Sugestão</span><span class="sxs-lookup"><span data-stu-id="d427e-112">Suggestion</span></span>|<span data-ttu-id="d427e-113">Um aplicativo que usa um valor previsto para <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> devem ser alteradas para buscar o valor real (e o valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name>) após qualquer rolagem horizontal que pode ser alteradas <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> devido a eliminação de virtualização.</span><span class="sxs-lookup"><span data-stu-id="d427e-113">An app that uses a predicted value for <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> should be changed to fetch the actual value (and the value of <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name>) after any horizontal scroll that could change <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> due to de-virtualization.</span></span>|
|<span data-ttu-id="d427e-114">Escopo</span><span class="sxs-lookup"><span data-stu-id="d427e-114">Scope</span></span>|<span data-ttu-id="d427e-115">Secundário</span><span class="sxs-lookup"><span data-stu-id="d427e-115">Minor</span></span>|
|<span data-ttu-id="d427e-116">Versão</span><span class="sxs-lookup"><span data-stu-id="d427e-116">Version</span></span>|<span data-ttu-id="d427e-117">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d427e-117">4.6.2</span></span>|
|<span data-ttu-id="d427e-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="d427e-118">Type</span></span>|<span data-ttu-id="d427e-119">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d427e-119">Runtime</span></span>|
|<span data-ttu-id="d427e-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d427e-120">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType></li></ul>|
