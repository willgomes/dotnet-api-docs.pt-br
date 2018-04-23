### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="a8676-101">Chamando Attribute.GetCustomAttributes em uma propriedade do indexador não lança AmbiguousMatchException a ambiguidade pode ser resolvida pelo tipo do índice</span><span class="sxs-lookup"><span data-stu-id="a8676-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a8676-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a8676-102">Details</span></span>|<span data-ttu-id="a8676-103">Antes do .NET Framework 4.6, chamar <code>GetCustomAttribute(s)</code> na propriedade de um indexador que diferia de outra propriedade apenas pelo tipo do índice resultaria em um <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="a8676-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>.</span></span> <span data-ttu-id="a8676-104">A partir do .NET Framework 4.6, os atributos da propriedade serão corretamente retornados.</span><span class="sxs-lookup"><span data-stu-id="a8676-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>|
|<span data-ttu-id="a8676-105">Sugestão</span><span class="sxs-lookup"><span data-stu-id="a8676-105">Suggestion</span></span>|<span data-ttu-id="a8676-106">Lembre-se de que GetCustomAttribute(s) funcionará com mais frequência agora.</span><span class="sxs-lookup"><span data-stu-id="a8676-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="a8676-107">Se um aplicativo anteriormente contava com o <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>, a reflexão agora deverá ser usada para procurar explicitamente vários indexadores.</span><span class="sxs-lookup"><span data-stu-id="a8676-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>|
|<span data-ttu-id="a8676-108">Escopo</span><span class="sxs-lookup"><span data-stu-id="a8676-108">Scope</span></span>|<span data-ttu-id="a8676-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a8676-109">Edge</span></span>|
|<span data-ttu-id="a8676-110">Versão</span><span class="sxs-lookup"><span data-stu-id="a8676-110">Version</span></span>|<span data-ttu-id="a8676-111">4.6</span><span class="sxs-lookup"><span data-stu-id="a8676-111">4.6</span></span>|
|<span data-ttu-id="a8676-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a8676-112">Type</span></span>|<span data-ttu-id="a8676-113">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="a8676-113">Runtime</span></span>|
|<span data-ttu-id="a8676-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="a8676-114">Affected APIs</span></span>|<ul><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li></ul>|
