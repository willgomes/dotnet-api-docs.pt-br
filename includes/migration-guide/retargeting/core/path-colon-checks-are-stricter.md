### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="47305-101">Verificações de dois-pontos em caminhos estão mais rigorosas</span><span class="sxs-lookup"><span data-stu-id="47305-101">Path colon checks are stricter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="47305-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="47305-102">Details</span></span>|<span data-ttu-id="47305-103">No .NET Framework 4.6.2, uma série de alterações foram feitas para dar suporte aos caminhos incompatíveis anteriormente (em termos de comprimento e formato).</span><span class="sxs-lookup"><span data-stu-id="47305-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="47305-104">As verificações de sintaxe do separador de unidades (dois-pontos) correto foram aperfeiçoadas, o que teve como efeito colateral o bloqueio de alguns caminhos de URI em algumas APIs de Caminho selecionadas em que eles costumavam ser aceitos.</span><span class="sxs-lookup"><span data-stu-id="47305-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>|
|<span data-ttu-id="47305-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="47305-105">Suggestion</span></span>|<span data-ttu-id="47305-106">Ao passar um URI para as APIs afetadas, modifique a cadeia de caracteres para um caminho correto antes.</span><span class="sxs-lookup"><span data-stu-id="47305-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="47305-107">Remova o esquema das URLs manualmente (por exemplo, remova <code>file://</code> das URLs).</span><span class="sxs-lookup"><span data-stu-id="47305-107">Remove the scheme from URLs manually (e.g. remove <code>file://</code> from URLs)</span></span></li><li><span data-ttu-id="47305-108">Passe o URI para a classe <xref:System.Uri> e use <xref:System.Uri.LocalPath>.</span><span class="sxs-lookup"><span data-stu-id="47305-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span></li></ul><span data-ttu-id="47305-109">Como alternativa, é possível recusar a normalização do novo caminho definindo a opção AppContext <code>Switch.System.IO.UseLegacyPathHandling</code> como true.</span><span class="sxs-lookup"><span data-stu-id="47305-109">Alternatively, you can opt out of the new path normalization by setting the <code>Switch.System.IO.UseLegacyPathHandling</code> AppContext switch to true.</span></span>|
|<span data-ttu-id="47305-110">Escopo</span><span class="sxs-lookup"><span data-stu-id="47305-110">Scope</span></span>|<span data-ttu-id="47305-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47305-111">Edge</span></span>|
|<span data-ttu-id="47305-112">Versão</span><span class="sxs-lookup"><span data-stu-id="47305-112">Version</span></span>|<span data-ttu-id="47305-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="47305-113">4.6.2</span></span>|
|<span data-ttu-id="47305-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="47305-114">Type</span></span>|<span data-ttu-id="47305-115">Redirecionando</span><span class="sxs-lookup"><span data-stu-id="47305-115">Retargeting</span></span>|
|<span data-ttu-id="47305-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="47305-116">Affected APIs</span></span>|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|
