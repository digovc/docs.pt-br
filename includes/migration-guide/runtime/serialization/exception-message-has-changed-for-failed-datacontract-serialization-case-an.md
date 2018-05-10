### <a name="exception-message-has-changed-for-failed-datacontract-serialization-in-case-of-an-unknown-type"></a>A mensagem de exceção foi alterada para a falha na serialização DataContract no caso de um tipo desconhecido

|   |   |
|---|---|
|Detalhes|A partir do .NET Framework 4.6, a mensagem de exceção gerada se a serialização ou desserialização de <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> ou <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> falhar por causa de "tipos conhecidos" ausentes foi esclarecida.|
|Sugestão|Os aplicativos não devem depender de mensagens de exceção específicas. Se um aplicativo depender dessa mensagem, atualize-o para que ele espere a nova mensagem ou, preferencialmente, altere-o para depender somente do tipo de exceção.|
|Escopo|Microsoft Edge|
|Versão|4.6|
|Tipo|Tempo de execução|
|APIs afetadas|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Runtime.Serialization.Json.DataContractJsonSerializerSettings)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Runtime.Serialization.DataContractSerializerSettings)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li></ul>|
