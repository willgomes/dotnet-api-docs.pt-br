### <a name="systemuri-escaping-now-supports-rfc-3986"></a><span data-ttu-id="fbeb4-101">URI de escape agora dá suporte ao RFC 3986</span><span class="sxs-lookup"><span data-stu-id="fbeb4-101">System.Uri escaping now supports RFC 3986</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fbeb4-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fbeb4-102">Details</span></span>|<span data-ttu-id="fbeb4-103">O escape do URI mudou no .NET 4.5 para dar suporte à [RFC 3986](http://tools.ietf.org/html/rfc3986).</span><span class="sxs-lookup"><span data-stu-id="fbeb4-103">URI escaping has changed in .NET 4.5 to support [RFC 3986](http://tools.ietf.org/html/rfc3986).</span></span> <span data-ttu-id="fbeb4-104">As alterações específicas incluem:</span><span class="sxs-lookup"><span data-stu-id="fbeb4-104">Specific changes include:</span></span><ul><li><span data-ttu-id="fbeb4-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> escapa caracteres reservados com base na RFC 3986.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-105"><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> escapes reserved characters based on RFC 3986.</span></span></li><li><span data-ttu-id="fbeb4-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> não escapa caracteres reservados.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-106"><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> does not escape reserved characters.</span></span></li><li><span data-ttu-id="fbeb4-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> não gerará uma exceção se encontrar uma sequência de escape inválida.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-107"><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> does not throw an exception if it encounters an invalid escape sequence.</span></span></li><li><span data-ttu-id="fbeb4-108">Os caracteres escapados não reservados não são escapados.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-108">Unreserved escaped characters are un-escaped.</span></span></li></ul>|
|<span data-ttu-id="fbeb4-109">Sugestão</span><span class="sxs-lookup"><span data-stu-id="fbeb4-109">Suggestion</span></span>|<ul><li><span data-ttu-id="fbeb4-110">Atualizar aplicativos para não confiar no <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> para lançar no caso de uma sequência de escape inválido.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-110">Update applications to not rely on <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> to throw in the case of an invalid escape sequence.</span></span> <span data-ttu-id="fbeb4-111">Essas sequências devem ser detectadas diretamente agora.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-111">Such sequences must be detected directly now.</span></span></li><li><span data-ttu-id="fbeb4-112">Da mesma forma, espere que o URI com escape e sem escape, bem como cadeias de caracteres de dados, possam variar do .NET 4.0 e .NET 4.5, não devendo ser comparados entre as versões do .NET diretamente.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-112">Similarly, expect that Escaped and Unescaped URI and Data strings may vary from .NET 4.0 and .NET 4.5 and should not be compared across .NET versions directly.</span></span> <span data-ttu-id="fbeb4-113">Em vez disso, eles devem ser analisados e normalizados em uma única versão do .NET antes que qualquer comparação seja feita.</span><span class="sxs-lookup"><span data-stu-id="fbeb4-113">Instead, they should be parsed and normalized in a single .NET version before any comparisons are made.</span></span></li></ul>|
|<span data-ttu-id="fbeb4-114">Escopo</span><span class="sxs-lookup"><span data-stu-id="fbeb4-114">Scope</span></span>|<span data-ttu-id="fbeb4-115">Secundário</span><span class="sxs-lookup"><span data-stu-id="fbeb4-115">Minor</span></span>|
|<span data-ttu-id="fbeb4-116">Versão</span><span class="sxs-lookup"><span data-stu-id="fbeb4-116">Version</span></span>|<span data-ttu-id="fbeb4-117">4.5</span><span class="sxs-lookup"><span data-stu-id="fbeb4-117">4.5</span></span>|
|<span data-ttu-id="fbeb4-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="fbeb4-118">Type</span></span>|<span data-ttu-id="fbeb4-119">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="fbeb4-119">Runtime</span></span>|
|<span data-ttu-id="fbeb4-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="fbeb4-120">Affected APIs</span></span>|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
