### <a name="accessibility-improvements-in-windows-forms-controls"></a>Melhorias de acessibilidade em controles do Windows Forms

|   |   |
|---|---|
|Detalhes|O Windows Forms está melhorando a forma como funciona com tecnologias de acessibilidade para dar um melhor suporte a seus clientes. Isso inclui as seguintes alterações começando com o .NET Framework 4.7.1:<ul><li>Alterações para melhorar a exibição durante o modo de Alto Contraste.</li><li>Alterações para melhorar a experiência no pesquisador de propriedades. As melhorias no pesquisador de propriedades incluem:</li><li>Melhor navegação de teclado por meio das várias janelas de seleção suspensa.</li><li>Redução de paradas de tabulação desnecessárias.</li><li>Melhor relatório de tipos de controle.</li><li>Melhor comportamento do Narrador.</li><li>Alterações para implementar padrões de acessibilidade de interface do usuário ausentes em controles.</li></ul>|
|Sugestão|<strong>Como aceitar ou recusar essas alterações</strong></br>Para que o aplicativo se beneficie dessas alterações, ele deverá ser executado no .NET Framework 4.7.1 ou posterior. O aplicativo pode se beneficiar dessas alterações de uma das seguintes maneiras:<ul><li>Ele é recompilado para ser destinado ao .NET Framework 4.7.1. Essas alterações de acessibilidade são habilitadas por padrão em aplicativos do Windows Forms destinados ao .NET Framework 4.7.1 ou posterior.</li><li>Ele recusa os comportamentos de acessibilidade herdados adicionando a seguinte [Opção de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) à seção <code>&lt;runtime&gt;</code> do arquivo app.config e configurando-a como <code>false</code>, como mostra o exemplo a seguir.</li></ul><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre></br>Aplicativos destinados ao .NET Framework 4.7.1 ou posterior que desejam preservar o comportamento de acessibilidade herdado pode aceitar o uso das funcionalidades de acessibilidade herdadas definindo explicitamente essa opção de AppContext como <code>true</code>.<p/>Para obter uma visão geral de automação da interface do usuário, confira a [Visão geral de automação da interface do usuário](~/docs/framework/ui-automation/ui-automation-overview.md).&lt;/p/&gt;<p/><strong>Adicionado o suporte para padrões e propriedades de automação de interface do usuário</strong><br/>Os clientes de acessibilidade podem aproveitar as novas funcionalidades de acessibilidade do WinForms usando padrões de invocação comuns, descritos publicamente. Esses padrões não são específicos do WinForms. Por exemplo, clientes de acessibilidade podem chamar o método QueryInterface na interface IAccessible (MAAS) para obter uma interface IServiceProvider. Se essa interface estiver disponível, os clientes poderão usar seu método QueryService para solicitar uma interface IAccessibleEx. Para obter mais informações, consulte [Usar IAccessibleEx de um cliente](https://msdn.microsoft.com/library/windows/desktop/dd561924.aspx). Começando com o .NET Framework 4.7.1, IServiceProvider e [IAccessibleEx](https://msdn.microsoft.com/library/windows/desktop/dd561898.aspx) (quando aplicáveis) estão disponíveis para objetos de acessibilidade do WinForms.<p/>O .NET Framework 4.7.1 adicionou o suporte para os seguintes padrões e propriedades de automação da interface do usuário:<ul><li>Os controles <xref:System.Windows.Forms.ToolStripSplitButton> e <xref:System.Windows.Forms.ComboBox> dão suporte ao [Padrão expandir/recolher](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li>O <xref:System.Windows.Forms.ToolStripMenuItem> controle tem uma propriedade [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) com valor <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li>O controle <xref:System.Windows.Forms.ToolStripItem> é compatível com a propriedade <xref:System.Windows.Automation.AutomationElement.NameProperty> e com o [padrão expandir/recolher](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li>O controle <xref:System.Windows.Forms.ToolStripDropDownItem> dá suporte a <xref:System.Windows.Forms.AccessibleEvents> indicando StateChange e NameChange quando a lista suspensa é expandida ou recolhida.</li><li>O <xref:System.Windows.Forms.ToolStripDropDownButton> controle tem uma propriedade [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) com valor de <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li>O controle <xref:System.Windows.Forms.DataGridViewCheckBoxCell> permite o <xref:System.Windows.Automation.TogglePattern>.</li><li>Os controles <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> permitem a propriedade <xref:System.Windows.Automation.AutomationElement.NameProperty> e têm um [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) igual a <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>.</p></li></ul><strong>Melhorias no controle PropertyGrid</strong></br>O .NET Framework 4.7.1 adicionou as seguintes melhorias ao controle PropertyBrowser:<ul><li>O botão <strong>Detalhes</strong> na caixa de diálogo de erro exibida quando o usuário insere um valor incorreto no controle <xref:System.Windows.Forms.PropertyGrid> é compatível com o [padrão de expandir/recolher](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), notificações de alteração de estado e de nome e uma propriedade [ControlType]~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) com um valor igual a <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li>O painel de mensagem exibido quando o botão <strong>Detalhes</strong> da caixa de diálogo de erro é expandido agora é acessível por teclado e permite que o Narrador anuncie o conteúdo da mensagem de erro.</li><li>A <xref:System.Windows.Forms.AccessibleRole> de linhas no controle <xref:System.Windows.Forms.PropertyGrid> foi alterada de &quot;Linha&quot; para &quot;Célula&quot;. A célula é mapeada para o ControlType de UIA &quot;DataItem&quot;, o que lhe permite dar suporte aos atalhos de teclado apropriados e a anúncios do Narrador.</li><li>As linhas do controle <xref:System.Windows.Forms.PropertyGrid> que representam itens de cabeçalho quando o controle <xref:System.Windows.Forms.PropertyGrid> tem uma propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort> definida como <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> têm uma propriedade [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) com o valor <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>.</li><li>As linhas do controle <xref:System.Windows.Forms.PropertyGrid> que representam itens de cabeçalho quando o controle <xref:System.Windows.Forms.PropertyGrid> tem uma propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort> definida como <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> são compatíveis com o [padrão expandir/recolher](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li>Melhoria da navegação por teclado entre a grade e a barra de ferramentas acima dela. Pressionar &quot;Shift – Tab&quot; agora seleciona o primeiro botão de barra de ferramentas em vez de toda a ToolBar.</li><li>Controles <xref:System.Windows.Forms.PropertyGrid> exibidos no modo de Alto Contraste agora desenharão um retângulo de foco ao redor do botão da barra de ferramentas correspondente ao valor da propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort> atual.</li><li>Controles <xref:System.Windows.Forms.PropertyGrid> exibidos no modo de Alto Contraste e com uma propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort> definida como <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> agora exibirão o segundo plano dos cabeçalhos de categoria em uma cor altamente contrastante.</li><li>Controles <xref:System.Windows.Forms.PropertyGrid> diferenciam melhor itens da barra de ferramentas com foco e itens da barra de ferramentas que indicam o valor atual da propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort>. Essa correção consiste em uma alteração de Alto Contraste e em uma alteração para cenários que não são de Alto Contraste.</li><li>Os itens de ToolBar do controle <xref:System.Windows.Forms.PropertyGrid> que indicam o valor atual da propriedade <xref:System.Windows.Forms.PropertyGrid.PropertySort> são compatíveis com o <xref:System.Windows.Automation.TogglePattern>.</li><li>Suporte aprimorado do Narrador para distinguir o alinhamento selecionado no Seletor de Alinhamento.</li><li>Quando um controle <xref:System.Windows.Forms.PropertyGrid> vazio é exibido em um formulário, agora ele recebe foco onde antes não receberia.</p></li></ul><strong>Uso de cores definidas pelo sistema operacional em temas de Alto Contraste</strong></br><ul><li>Os controles <xref:System.Windows.Forms.Button> e <xref:System.Windows.Forms.CheckBox> com a propriedade <xref:System.Windows.Forms.ButtonBase.FlatStyle> definida como <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>, que é o estilo padrão, agora usam cores definidas pelo SO no tema de Alto Contraste quando selecionado. Anteriormente, as cores de texto e de tela de fundo não eram contrastantes e eram difíceis de ler.</li><li>Os controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel> e <xref:System.Windows.Forms.GroupBox> com a propriedade <xref:System.Windows.Forms.Control.Enabled> definida como <strong>false</strong> usavam uma cor sombreada para renderizar o texto nos temas de Alto Contraste, resultando em pouco um contraste em relação ao segundo plano. Agora, esses controles usam a cor de &quot;Texto Desabilitado&quot; definida pelo SO. Essa correção aplica-se a controles com a propriedade <code>FlatStyle</code> definida com um valor diferente de <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>. Os últimos controles são renderizados pelo sistema operacional.</li><li><xref:System.Windows.Forms.DataGridView> agora renderiza um retângulo visível em torno do conteúdo da célula que tem o foco atual. Anteriormente, isso não era visível em certos temas de Alto Contraste.</li><li>Os controles <xref:System.Windows.Forms.ToolStripMenuItem> com uma propriedade <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> definida como <strong>false</strong> agora usam a cor de &quot;Texto Desabilitado&quot; definida pelo SO.</li><li>Os controles <xref:System.Windows.Forms.ToolStripMenuItem> com a propriedade <xref:System.Windows.Forms.ToolStripMenuItem.Checked> definida como <strong>true</strong> agora renderizam a marca de seleção associada com uma cor do sistema contrastante.  Antes, a cor da marca de seleção não era contrastante o suficiente e não era visível em temas de Alto Contraste.</li></ul>Observação: o Windows 10 mudou os valores de algumas cores do sistema de Alto Contraste. A estrutura do Windows Forms é baseada na estrutura do Win32. Para obter a melhor experiência, execute a versão mais recente do Windows e aceite as alterações mais recentes do sistema operacional adicionando um arquivo app.manifest a um aplicativo de teste e removendo a marca de comentário do seguinte código:<pre><code class="lang-xml">&lt;!-- Windows 10 --&gt;&#13;&#10;&lt;supportedOS Id=&quot;{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}&quot; /&gt;&#13;&#10;</code></pre></br><strong>Melhoria na navegação por teclado</strong><ul><li>Quando um controle <xref:System.Windows.Forms.ComboBox> tem a propriedade<xref:System.Windows.Forms.ComboBox.DropDownStyle> definida como <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> e é o primeiro controle na ordem de tabulação no formulário, agora ele exibe um retângulo de foco quando o formulário pai é aberto usando o teclado. Antes desta alteração, o foco do teclado ficava nesse controle, mas um indicador de foco não era renderizado.</li></ul><strong>Melhor suporte ao Narrador</strong><ul><li>O controle <xref:System.Windows.Forms.MonthCalendar> tem suporte adicional para tecnologias de assistência para acessar o controle, incluindo a capacidade do Narrador ler o valor do controle, quando antes ele não podia.</li><li>O controle <xref:System.Windows.Forms.CheckedListBox> agora notifica o Narrador quando a propriedade <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType> é alterada. Antes, o Narrador não recebia uma notificação e, como resultado, os usuários não eram informados sobre a atualização da propriedade <xref:System.Windows.Forms.CheckBox.CheckState>.</li><li>O controle <xref:System.Windows.Forms.LinkLabel> alterou a maneira como notifica o Narrador do texto no controle. Antes, o Narrador anunciava esse texto duas vezes e lia símbolos &quot;&amp;&quot; como texto real, mesmo que eles não fossem visíveis para um usuário. O texto duplicado foi removido dos anúncios do Narrador, bem como símbolos &quot;&amp;&quot; desnecessários.</li><li>Os tipos de controle <xref:System.Windows.Forms.DataGridViewCell> agora relatam corretamente o status de somente leitura para o Narrador e outras tecnologias assistenciais.</li><li>O Narrator agora é capaz de ler o Menu do Sistema das janelas filhas em aplicativos [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md).</li><li>O Narrador agora é capaz de ler controles <xref:System.Windows.Forms.ToolStripMenuItem> com uma propriedade <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType> definida como <strong>false</strong>. Antes, o Narrador não conseguia focar itens de menu desabilitados para ler o conteúdo.</li></ul>|
|Escopo|Principal|
|Versão|4.7.1|
|Tipo|Redirecionando|
|APIs afetadas|<ul><li><xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType></li><li>[MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)</li></ul>|
