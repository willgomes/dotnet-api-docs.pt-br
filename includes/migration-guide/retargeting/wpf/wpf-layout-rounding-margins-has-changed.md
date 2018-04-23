### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="0f9ea-101">Arredondamento de layout do WPF foi alterado</span><span class="sxs-lookup"><span data-stu-id="0f9ea-101">WPF layout rounding of margins has changed</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0f9ea-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0f9ea-102">Details</span></span>|<span data-ttu-id="0f9ea-103">A maneira como as margens são arredondadas, bem como as bordas e a tela de fundo dentro delas, foi alterada.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="0f9ea-104">Como resultado dessa alteração:</span><span class="sxs-lookup"><span data-stu-id="0f9ea-104">As a result of this change:</span></span><ul><li><span data-ttu-id="0f9ea-105">A largura ou altura dos elementos pode aumentar ou reduzir em um pixel no máximo.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-105">The width or height of elements may grow or shrink by at most one pixel.</span></span></li><li><span data-ttu-id="0f9ea-106">O posicionamento de um objeto pode ser movido até um pixel, no máximo.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-106">The placement of an object can move by at most one pixel.</span></span></li><li><span data-ttu-id="0f9ea-107">Os elementos centralizados podem estar vertical ou horizontalmente fora do centro em, no máximo, um pixel.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span></li></ul><span data-ttu-id="0f9ea-108">Por padrão, esse novo layout é habilitado somente para aplicativos que se destinam ao .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="0f9ea-109">Sugestão</span><span class="sxs-lookup"><span data-stu-id="0f9ea-109">Suggestion</span></span>|<span data-ttu-id="0f9ea-110">Uma vez que essa modificação tende a eliminar a distorção da direita ou da parte inferior dos controles do WPF em DPIs altos, os aplicativos destinados a versões anteriores do .NET Framework, mas que estão sendo executados no .NET Framework 4.6, podem aderir a esse novo comportamento adicionando a seguinte linha à seção <code>&lt;runtime&gt;</code> do arquivo app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>Aplicativos destinados ao .NET Framework 4.6, mas que desejam que os controles do WPF renderizem usando o algoritmo de layout anterior podem fazê-lo adicionando a seguinte linha à seção <code>&lt;runtime&gt;</code> do arquivo app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="0f9ea-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;</code>Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;</code>.</span></span>|
|<span data-ttu-id="0f9ea-111">Escopo</span><span class="sxs-lookup"><span data-stu-id="0f9ea-111">Scope</span></span>|<span data-ttu-id="0f9ea-112">Secundário</span><span class="sxs-lookup"><span data-stu-id="0f9ea-112">Minor</span></span>|
|<span data-ttu-id="0f9ea-113">Versão</span><span class="sxs-lookup"><span data-stu-id="0f9ea-113">Version</span></span>|<span data-ttu-id="0f9ea-114">4.6</span><span class="sxs-lookup"><span data-stu-id="0f9ea-114">4.6</span></span>|
|<span data-ttu-id="0f9ea-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="0f9ea-115">Type</span></span>|<span data-ttu-id="0f9ea-116">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="0f9ea-116">Retargeting</span></span>|
