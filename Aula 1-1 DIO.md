---


---

<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>
<h3 id="serviços-web">Serviços Web</h3>
<p>São soluções para aplicações se comunicarem independente de linguagem, softwares e hardwares utilizados. Foram criados para troca de mensagens utilizando XML sobre o protocolo HTTP.</p>
<p>Basicamente Serviços Web são APIs que se comunicam por meio de redes sobre o protocolo HTTP, utilizando JSON ou XML.</p>
<p>O Web Service faz a ponte entre dois bancos de dados que não poderiam se comunicar entre dois aplicativos distintos.</p>
<p>Exemplo XML</p>
<pre><code>&lt;endereco&gt;
	&lt;cep&gt;9999-99&lt;/cep&gt;
	&lt;bairro&gt;Jardim Paulista&lt;/bairro&gt;
	&lt;cidade&gt;São Paulo&lt;/cidade&gt;
&lt;/endereco&gt;
</code></pre>
<p>Exemplo JSON</p>
<pre><code>{
	"endereco": {
		"cep": "9999-99",
		"logradouro": "Av. Paulista",
		"bairro": "Jardim Paulista",
		"cidade": "São Paulo"
	}
}
</code></pre>
<p>As vantagens do XML consistem em ser uma linguagem comum, com alta integração, reutilização de implentação, segurança e baixos custos.</p>
<h3 id="estrutura-soap">Estrutura SOAP</h3>
<p>SOAP é um acrônimo para Simple Object Access Protocol.</p>
<p>É um protocolo baseado em XML para acessar serviços web principalmente por HTTP. Podemos dizer que SOAP é uma definição de como serviços web se comunicam. Também é um meio de transporte genérico podendo ser utilizado por outros protocolos além do HTTP, como Java e PHP.<br>
É independente de hardware, software e sistema operacional e permite integrações entre aplicações independente de linguagem pois usa a linguagem de marcação comum XML.</p>
<h4 id="xml">Xml</h4>
<p>XML é uma sigla para eXtensible Markup Language.</p>
<p>Foi criado na década de 90 pela W3C, um órgão criado por diversas empresas e órgãos governamentais para a padronização da web. Através das <em>tags</em>(etiquetas) podemos separar o conteúdo para fácill leitura, além das <em>tags</em> não terem limite para sua criação. Também é uma linguagem comum para a integração de aplicativos.</p>
<h4 id="soap-message">Soap Message</h4>
<p>Uma mensagem SOAP deve seguir a seguinte estrutura:</p>
<ol>
<li><em>Soap Envelope</em> (a <em>tag</em> pai que envolve toda a mensagem)<br>
1.1 <em>Soap Header</em> (Dados de atributos e metadados da mensagem)<br>
1.1.1 <em>Soap Body</em> (Conteúdo e detalhes da mensagem)</li>
</ol>
<p>Exemplo XML de SOAP</p>
<pre><code>&lt;soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope"&gt;
	&lt;soap:Header&gt;
	&lt;/soap:Header&gt;
	&lt;soap:Body&gt;
	 &lt;m: MetodoEndereco xmlns:m="http://example.org/endereco"&gt;
	 ...
	 &lt;/m:endereco&gt;
	 &lt;/soap:Body&gt;
&lt;\soap:Envelope&gt;
</code></pre>
<h3 id="wsdl">WSDL</h3>
<p>WSDL significa Web Services Description Language.<br>
Usado para descrever Web Services, como um contrato de serviço escrito em XML descrevendo o serviço, especificações de acesso, operações e métodos.</p>
<p>Aqui temos um <strong><a href="www.soapclient.com/xml/soapresponder.wsdl">Exemplo de WSDL</a></strong> com um XSD.</p>
<h3 id="xsd">XSD</h3>
<p>Significa XML Schema Definition.<br>
É um esquema no formato XML usado para definir a estrutura de dados que será validada no XML.  Funciona como uma documentação de como deve ser montado o SOAP Message que será enviado através do Web Service. XSD define a estrutura e WSDL descreve o Web Service.</p>
<p><a href="soapui.org">SoapUI</a> é um visualizador de SOAPs com uma alternativa open source.</p>
<h3 id="rest">REST</h3>
<p>REST é um acrônimo de Representional State Transfer.<br>
É um estilo de arquitetura de software que define a implementação de um serviço web. Podem trabalhar com os formatos XML, JSON ou outros. Difere do SOAP por não ser um protocolo mas sim um estilo ou design de arquitetura de serviços web que roda sob HTTP e outros formatos.</p>
<p>Permite integração entre aplicações, além entre cliente e servidor em páginas web e aplicações. Utiliza de métodos HTTP para definir a operação que está sendo efetuada, além de possuir uma arquitetura de fácil compreensão.</p>
<h4 id="estrutura-do-rest">Estrutura do REST</h4>
<div class="mermaid"><svg xmlns="http://www.w3.org/2000/svg" id="mermaid-svg-zRHiVGWV7eiZOTkM" width="100%" style="max-width: 427.8666534423828px;" viewBox="0 0 427.8666534423828 89.43331909179688"><g transform="translate(-12, -12)"><g class="output"><g class="clusters"></g><g class="edgePaths"><g class="edgePath" style="opacity: 1;"><path class="path" d="M89.71665954589844,51.8268644378969L221.37499237060547,33.35832977294922L353.0333251953125,51.33476589941972" marker-end="url(#arrowhead4847)" style="fill:none"></path><defs><marker id="arrowhead4847" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1px; stroke-dasharray: 1px, 0px;"></path></marker></defs></g><g class="edgePath" style="opacity: 1;"><path class="path" d="M353.0333251953125,62.09855319237715L221.37499237060547,80.07498931884766L89.71665954589844,61.60645465389997" marker-end="url(#arrowhead4848)" style="fill:none"></path><defs><marker id="arrowhead4848" viewBox="0 0 10 10" refX="9" refY="5" markerUnits="strokeWidth" markerWidth="8" markerHeight="6" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" class="arrowheadPath" style="stroke-width: 1px; stroke-dasharray: 1px, 0px;"></path></marker></defs></g></g><g class="edgeLabels"><g class="edgeLabel" style="opacity: 1;" transform="translate(221.37499237060547,33.35832977294922)"><g transform="translate(-59.958335876464844,-13.358329772949219)" class="label"><foreignObject width="119.91667175292969" height="26.716659545898438"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">Requisição HTTP</span></div></foreignObject></g></g><g class="edgeLabel" style="opacity: 1;" transform="translate(221.37499237060547,80.07498931884766)"><g transform="translate(-106.65833282470703,-13.358329772949219)" class="label"><foreignObject width="213.31666564941406" height="26.716659545898438"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;"><span class="edgeLabel">Retorno em XML, JSON, Texto</span></div></foreignObject></g></g></g><g class="nodes"><g class="node" style="opacity: 1;" id="A" transform="translate(54.85832977294922,56.71665954589844)"><rect rx="0" ry="0" x="-34.85832977294922" y="-23.35832977294922" width="69.71665954589844" height="46.71665954589844"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-24.85832977294922,-13.358329772949219)"><foreignObject width="49.71665954589844" height="26.716659545898438"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">Cliente</div></foreignObject></g></g></g><g class="node" style="opacity: 1;" id="B" transform="translate(392.44998931884766,56.71665954589844)"><rect rx="5" ry="5" x="-39.416664123535156" y="-23.35832977294922" width="78.83332824707031" height="46.71665954589844"></rect><g class="label" transform="translate(0,0)"><g transform="translate(-29.416664123535156,-13.358329772949219)"><foreignObject width="58.83332824707031" height="26.716659545898438"><div xmlns="http://www.w3.org/1999/xhtml" style="display: inline-block; white-space: nowrap;">Servidor</div></foreignObject></g></g></g></g></g></g></svg></div>
<h3 id="apis">APIs</h3>
<p>Quando uma aplicação web disponibiliza um conjunto de rotinas e padrões através de serviços web podemos chamar esse conjunto de APIs.</p>
<p>Significa Application Programming Interface. São conjuntos de rotinas documentados e disponibilizados por uma aplicação para que outras aplicações possam consumir suas funcionalidades. Ficou popular com o aumento do uso de serviços web. Os maiores plataformas de tecnologia disponibilizam APIs para acesso de suas funcionalidades.</p>
<h4 id="principais-métodos-http">Principais métodos HTTP:</h4>
<ul>
<li>
<p>GET: Solicita a representação de um recurso, como por exemplo a consulta de um logradouro.</p>
</li>
<li>
<p>POST: Solicita a criação de um recurso, como a inserção de uma informação em uma base de dados.</p>
</li>
<li>
<p>DELETE: Solicita a exclusão de um recurso, um paralelo sendo a exclusão de um tweet postado.</p>
</li>
<li>
<p>PUT: Atualiza um recurso.</p>
</li>
</ul>
<p>Para um serviço web seguir a arquitetura REST as requisições tem de seguir este formato. Um GET deve realizar um GET e não por exemplo deletar um recurso.</p>
<h3 id="json">JSON</h3>
<p>JavaScript Object Notation. É uma linguagem de marcação com linguagem leve, estrutura de chaves e valores além de listas ordenadas e é altamente popular juntamente com o XML para troca de mensagens entre sistemas.</p>
<p>Exemplo da estrutura JSON:</p>
<pre><code>{
	"nome":"os vingadores",
	"ano_lancamento":"2019",
	"personagens":[
		{
			"nome":"Thanos"
		},
		{
			"nome":"Homem de Ferro"
		},
		{
			"nome:"Thor"
		}
	]
}
</code></pre>
<h3 id="integração-com-rest-e-http">Integração com REST e HTTP</h3>
<h4 id="códigos-de-estado">Códigos de Estado</h4>
<p>Utilizado pelo servidor para avisar o cliente sobre o estado da operação solicitada.</p>
<ul>
<li>1** - Informativo</li>
<li>2** - Sucesso</li>
<li>3** - Redirecionamento (Utilizado quando ocorre uma troca de URI, ou a URI é movida permanentemente)</li>
<li>4** - Erro do Cliente (Quando o cliente envia uma informação indevida, como uma URI inválida (404))</li>
<li>5** - Erro do Servidor (Erro interno de processamento do servidor)</li>
</ul>
<p>O <a href="https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status">Site</a> da Mozilla contém informações de todos os códigos de estado HTTP.</p>
<p>O <a href="www.postman.com">Postman</a> é um bom software para trabalhar com o padrão REST.</p>
<p>A API do <a href="https://developer.twitter.com/en/docs/twitter-api">Twitter</a> é bem popular para aplicar os conhecimentos e estudar.</p>

