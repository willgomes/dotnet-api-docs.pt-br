### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="9fdad-101">XmlSchemaException agora define as posições de linha corretamente</span><span class="sxs-lookup"><span data-stu-id="9fdad-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9fdad-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9fdad-102">Details</span></span>|<span data-ttu-id="9fdad-103">Se o <xref:System.Xml.Linq.LoadOptions.SetLineInfo> valor é passado para o método de carga e ocorre um erro de validação, o <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> propriedades agora contêm informações de linha.</span><span class="sxs-lookup"><span data-stu-id="9fdad-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="9fdad-104">Sugestão</span><span class="sxs-lookup"><span data-stu-id="9fdad-104">Suggestion</span></span>|<span data-ttu-id="9fdad-105">Código de tratamento de exceção que assume <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> não serão conjunto deve ser atualizado, pois essas propriedades serão agora definidas corretamente quando SetLineInfo é usada ao carregar o XML.</span><span class="sxs-lookup"><span data-stu-id="9fdad-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="9fdad-106">Escopo</span><span class="sxs-lookup"><span data-stu-id="9fdad-106">Scope</span></span>|<span data-ttu-id="9fdad-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9fdad-107">Edge</span></span>|
|<span data-ttu-id="9fdad-108">Versão</span><span class="sxs-lookup"><span data-stu-id="9fdad-108">Version</span></span>|<span data-ttu-id="9fdad-109">4.5</span><span class="sxs-lookup"><span data-stu-id="9fdad-109">4.5</span></span>|
|<span data-ttu-id="9fdad-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="9fdad-110">Type</span></span>|<span data-ttu-id="9fdad-111">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="9fdad-111">Runtime</span></span>|
|<span data-ttu-id="9fdad-112">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="9fdad-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
