### <a name="wpf-pointer-based-touch-stack"></a><span data-ttu-id="5501e-101">Pilha de toque baseada em ponteiro WPF</span><span class="sxs-lookup"><span data-stu-id="5501e-101">WPF Pointer-Based Touch Stack</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5501e-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5501e-102">Details</span></span>|<span data-ttu-id="5501e-103">Essa alteração adiciona a capacidade de habilitar um WM_POINTER opcional com base em pilha de toque/caneta do WPF.</span><span class="sxs-lookup"><span data-stu-id="5501e-103">This change adds the ability to enable an optional WM_POINTER based WPF touch/stylus stack.</span></span>  <span data-ttu-id="5501e-104">Os desenvolvedores que não permitem explicitamente isso deverá ver nenhuma alteração no comportamento de toque/caneta do WPF. Atual problemas conhecidos com opcional WM_POINTER com base em pilha toque/caneta:</span><span class="sxs-lookup"><span data-stu-id="5501e-104">Developers that do not explicitly enable this should see no change in WPF touch/stylus behavior.Current Known Issues With optional WM_POINTER based touch/stylus stack:</span></span><ul><li><span data-ttu-id="5501e-105">Não há suporte para escrita à tinta em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5501e-105">No support for real-time inking.</span></span></li><li><span data-ttu-id="5501e-106">Ao escrever à tinta e StylusPlugins ainda funcionarão, eles serão processados no Thread da interface do usuário que pode resultar em baixo desempenho.</span><span class="sxs-lookup"><span data-stu-id="5501e-106">While inking and StylusPlugins will still work, they will be processed on the UI Thread which can lead to poor performance.</span></span></li><li><span data-ttu-id="5501e-107">Alterações de comportamento devido a alterações na promoção de eventos de caneta/toque para eventos de mouse</span><span class="sxs-lookup"><span data-stu-id="5501e-107">Behavioral changes due to changes in promotion from touch/stylus events to mouse events</span></span></li><li><span data-ttu-id="5501e-108">Manipulação pode se comportar de maneira diferente</span><span class="sxs-lookup"><span data-stu-id="5501e-108">Manipulation may behave differently</span></span></li><li><span data-ttu-id="5501e-109">Arrastar/soltar não mostrará comentários apropriado para a entrada de toque</span><span class="sxs-lookup"><span data-stu-id="5501e-109">Drag/Drop will not show appropriate feedback for touch input</span></span></li><li><span data-ttu-id="5501e-110">Isso não afeta a entrada de caneta</span><span class="sxs-lookup"><span data-stu-id="5501e-110">This does not affect stylus input</span></span></li><li><span data-ttu-id="5501e-111">Arrastar/soltar não pode ser iniciado em eventos de toque/caneta</span><span class="sxs-lookup"><span data-stu-id="5501e-111">Drag/Drop can no longer be initiated on touch/stylus events</span></span></li><li><span data-ttu-id="5501e-112">Isso pode travar o aplicativo até que a entrada do mouse seja detectada.</span><span class="sxs-lookup"><span data-stu-id="5501e-112">This can potentially hang the application until mouse input is detected.</span></span></li><li><span data-ttu-id="5501e-113">Em vez disso, os desenvolvedores devem iniciar a ação de arrastar e soltar usando eventos de mouse.</span><span class="sxs-lookup"><span data-stu-id="5501e-113">Instead, developers should initiate drag and drop from mouse events.</span></span></li></ul>|
|<span data-ttu-id="5501e-114">Sugestão</span><span class="sxs-lookup"><span data-stu-id="5501e-114">Suggestion</span></span>|<span data-ttu-id="5501e-115">Os desenvolvedores que desejam habilitar esta pilha podem adicionar/mesclagem a seguir ao arquivo App. config de seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="5501e-115">Developers who wish to enable this stack can add/merge the following to their application's App.config file:</span></span><pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="5501e-116">Removendo isso ou definindo o valor como false desativa essa pilha opcional. Observe que esta pilha está disponível somente em criadores de atualização do Windows 10 e acima.</span><span class="sxs-lookup"><span data-stu-id="5501e-116">Removing this or setting the value to false will turn this optional stack off.Please note that this stack is available only on Windows 10 Creators Update and above.</span></span>|
|<span data-ttu-id="5501e-117">Escopo</span><span class="sxs-lookup"><span data-stu-id="5501e-117">Scope</span></span>|<span data-ttu-id="5501e-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5501e-118">Edge</span></span>|
|<span data-ttu-id="5501e-119">Versão</span><span class="sxs-lookup"><span data-stu-id="5501e-119">Version</span></span>|<span data-ttu-id="5501e-120">4.7</span><span class="sxs-lookup"><span data-stu-id="5501e-120">4.7</span></span>|
|<span data-ttu-id="5501e-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="5501e-121">Type</span></span>|<span data-ttu-id="5501e-122">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="5501e-122">Retargeting</span></span>|
