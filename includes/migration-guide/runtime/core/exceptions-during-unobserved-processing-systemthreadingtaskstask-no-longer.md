### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="887af-101">Exceções durante o processamento observada no Threading não são propagadas no thread do finalizador</span><span class="sxs-lookup"><span data-stu-id="887af-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

|   |   |
|---|---|
|<span data-ttu-id="887af-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="887af-102">Details</span></span>|<span data-ttu-id="887af-103">Como a classe <xref:System.Threading.Tasks.Task?displayProperty=name> representa uma operação assíncrona, ela captura todas as exceções não graves que ocorrem durante o processamento assíncrono.</span><span class="sxs-lookup"><span data-stu-id="887af-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=name> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="887af-104">No .NET Framework 4.5, se uma exceção não for observada e seu código nunca aguarda a tarefa, a exceção não será mais propagada no thread do finalizador e causará a falha do processo durante a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="887af-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="887af-105">Essa alteração melhora a confiabilidade de aplicativos que usam a classe Task para executar processamento assíncrono não observado.</span><span class="sxs-lookup"><span data-stu-id="887af-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>|
|<span data-ttu-id="887af-106">Sugestão</span><span class="sxs-lookup"><span data-stu-id="887af-106">Suggestion</span></span>|<span data-ttu-id="887af-107">Se um aplicativo depender observadas exceções assíncronas propagar para o thread do finalizador, o comportamento anterior pode ser restaurado, fornecendo um manipulador adequado para o <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, ou definindo um [elemento de configuração de tempo de execução ](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span><span class="sxs-lookup"><span data-stu-id="887af-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>|
|<span data-ttu-id="887af-108">Escopo</span><span class="sxs-lookup"><span data-stu-id="887af-108">Scope</span></span>|<span data-ttu-id="887af-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="887af-109">Edge</span></span>|
|<span data-ttu-id="887af-110">Versão</span><span class="sxs-lookup"><span data-stu-id="887af-110">Version</span></span>|<span data-ttu-id="887af-111">4.5</span><span class="sxs-lookup"><span data-stu-id="887af-111">4.5</span></span>|
|<span data-ttu-id="887af-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="887af-112">Type</span></span>|<span data-ttu-id="887af-113">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="887af-113">Runtime</span></span>|
|<span data-ttu-id="887af-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="887af-114">Affected APIs</span></span>|<ul><li><xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
