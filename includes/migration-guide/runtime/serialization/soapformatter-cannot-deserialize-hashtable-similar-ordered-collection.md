### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="9511a-101">SoapFormatter não é possível desserializar a tabela de hash e ordenados semelhante objetos de coleção</span><span class="sxs-lookup"><span data-stu-id="9511a-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9511a-102">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9511a-102">Details</span></span>|<span data-ttu-id="9511a-103">O <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> faz garante que os objetos serializados em uma versão do .NET Framework desserializará com êxito em uma versão diferente.</span><span class="sxs-lookup"><span data-stu-id="9511a-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="9511a-104">Especificamente, alguns ordenados coleções (como <xref:System.Collections.Hashtable?displayProperty=name>) adicionou membros entre 4.0 e 4.5, de forma que os objetos desses tipos não é possível desserializar com o .NET 4.0, se eles foram serializados com o .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="9511a-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=name>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET 4.0 if they were serialized with .NET 4.5.</span></span> <span data-ttu-id="9511a-105">Observe que se os dados serializados forem serializados e desserializados com a mesma versão do .NET Framework, nenhum problema ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="9511a-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>|
|<span data-ttu-id="9511a-106">Sugestão</span><span class="sxs-lookup"><span data-stu-id="9511a-106">Suggestion</span></span>|<span data-ttu-id="9511a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> serialização deve ser substituída pelo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serialização ou <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> para ser resiliente em alterações do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9511a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> to be resilient to .NET Framework changes.</span></span>|
|<span data-ttu-id="9511a-108">Escopo</span><span class="sxs-lookup"><span data-stu-id="9511a-108">Scope</span></span>|<span data-ttu-id="9511a-109">Secundário</span><span class="sxs-lookup"><span data-stu-id="9511a-109">Minor</span></span>|
|<span data-ttu-id="9511a-110">Versão</span><span class="sxs-lookup"><span data-stu-id="9511a-110">Version</span></span>|<span data-ttu-id="9511a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9511a-111">4.5</span></span>|
|<span data-ttu-id="9511a-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="9511a-112">Type</span></span>|<span data-ttu-id="9511a-113">Tempo de execução</span><span class="sxs-lookup"><span data-stu-id="9511a-113">Runtime</span></span>|
|<span data-ttu-id="9511a-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="9511a-114">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
