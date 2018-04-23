### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="caa07-101">ServiceBase não propaga OnStart exceções</span><span class="sxs-lookup"><span data-stu-id="caa07-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

|   |   |
|---|---|
|<span data-ttu-id="caa07-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="caa07-102">Details</span></span>|<span data-ttu-id="caa07-103">No .NET Framework 4.7 e versões anteriores, exceções geradas durante a inicialização do serviço não são propagadas para o chamador de <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>. Começando com aplicativos voltados para o .NET Framework 4.7.1, o tempo de execução propaga exceções <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> para serviços que falham ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="caa07-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>|
|<span data-ttu-id="caa07-104">Sugestão</span><span class="sxs-lookup"><span data-stu-id="caa07-104">Suggestion</span></span>|<span data-ttu-id="caa07-105">Na inicialização do serviço, se houver uma exceção, essa exceção será propagada.</span><span class="sxs-lookup"><span data-stu-id="caa07-105">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="caa07-106">Isso deve ajudar a diagnosticar os casos em que os serviços não serão iniciados. Se esse comportamento é desejável, você pode optar por fora dele, adicionando o seguinte <AppContextSwitchOverrides> elemento para o <runtime> seção do arquivo de configuração de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="caa07-106">This should help diagnose cases where services fail to start.If this behavior is undesirable, you can opt out of it by adding the following <AppContextSwitchOverrides> element to the <runtime> section of your application configuration file:</span></span><pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre><span data-ttu-id="caa07-107">Se seu aplicativo tem como alvo uma versão anterior ao 4.7.1, mas você deseja ter esse comportamento, adicione o seguinte <AppContextSwitchOverrides> elemento para o <runtime> seção do arquivo de configuração de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="caa07-107">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following <AppContextSwitchOverrides> element to the <runtime> section of your application configuration file:</span></span><pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="caa07-108">Escopo</span><span class="sxs-lookup"><span data-stu-id="caa07-108">Scope</span></span>|<span data-ttu-id="caa07-109">Secundário</span><span class="sxs-lookup"><span data-stu-id="caa07-109">Minor</span></span>|
|<span data-ttu-id="caa07-110">Versão</span><span class="sxs-lookup"><span data-stu-id="caa07-110">Version</span></span>|<span data-ttu-id="caa07-111">4.7.1</span><span class="sxs-lookup"><span data-stu-id="caa07-111">4.7.1</span></span>|
|<span data-ttu-id="caa07-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="caa07-112">Type</span></span>|<span data-ttu-id="caa07-113">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="caa07-113">Retargeting</span></span>|
|<span data-ttu-id="caa07-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="caa07-114">Affected APIs</span></span>|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|
