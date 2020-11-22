---


---

<blockquote>
<p>Written with <a href="https://stackedit.io/">StackEdit</a>.</p>
</blockquote>
<h3 id="conceitos-de-arquitetura-em-aplicações-para-internet">Conceitos de arquitetura em aplicações para internet</h3>
<h4 id="tipos-de-arquitetura">Tipos de arquitetura</h4>
<ul>
<li>Monolito</li>
</ul>
<p>Mobile apps e Web Apps (aplicações clientes) conversam com um serviços através de um protcolo HTTP. Se conectam com instâncias de uma aplicação, conectadas a um banco de dados, tudo isso dentro do servidor.</p>
<p>Várias instâncias do aplicativo são necessárias para distribuir a demanda para não sobrecarregar as individuais, além de proteger contra erros.</p>
<ul>
<li>Microserviços</li>
</ul>
<p>Diferente do monolito que possui várias instâncias de um único aplicativo, teremos diversos microsserviços para cada demanda. Os serviços são distribuídos por nodos, e estes nodos funcionam como monolitos.<br>
Os serviços devem possuir a possibilidade de se comunicar entre si, seja por protocolo próprio ou por HTTP.</p>
<p>Os clientes acessam o proxy HTTP que verifica o serviço responsável pela operação, que redireciona para um serviço x ou y. Também podemos ter serviços internos que não se comunicam com o proxy externo.</p>
<p>Podemos ter uma arquitetura de microserviços em que os serviços se comunicam a um <em>message broker</em> externo, cuja vantagem é que não há mais comunicação interna entre os serviços. A desvantagem é que a arquitetura fica refém do message broker caso ele caia.</p>
<p>Também podemos ter uma arquitetura em que os serviços não comunicam entre si, e a demanda passa anteriormente por um gerenciador de <em>pipeline</em>. Cada serviço pode operar de forma desacoplada, reduzindo o código e por conseguinte os <em>bugs</em>. O pipeline vê a request, comunica com o serviço 1 que executa o que precisa ser feito e repassa ao pipeline, que manda a resposta ao serviço 2, e assim por diante até encerrar o pipeline, que retorna ao cliente caso a request tenha sucesso. O problema é que caso o serviço 2 esteja fora do ar, o gerenciador deve ser capaz de retornar ao serviço 1 e reverter o que for feito para que não quebre o sistema.</p>
<h4 id="comparação-entre-os-dois-tipos">Comparação entre os dois tipos</h4>
<ul>
<li>
<p>Monolito<br>
Possui baixa complexidade e um monitoramento simplificado.  Porém, contém apenas uma stack única. Outro problema é o compartilhamento de recursos, onde não é possível escalonar funcionalidades avulsas sem compartilhar o sistema inteiro. Isso se dá pois todas as funcionalidades são acopladas no sistema inteiro e o escalonamento se torna mais complexo por conta disso.</p>
</li>
<li>
<p>Microserviços (acoplados diretamente)<br>
-A stack é dinâmica, então os serviços podem trabalhar com  diversas tecnologias.  E pelos serviços serem menores e mais simples a escalonabilidade torna-se mais simples. Porém, os serviços ainda são acoplados pois cada um deles comunicam-se de forma direta e se um deles estiver fora do ar o sistema inteiro acaba quebrando. O monitoramento torna-se mais complexo, pois precisamos observar cada um dos serviços que rodam em tecnologias diferentes. Precisamos também de um provisionamento mais complexo pois precisamos de mais e mais <em>dockers</em> conforme a quantidade de serviços aumentam.</p>
</li>
<li>
<p>Microserviços (com <em>message broker</em>)<br>
Além de termos a stack dinâmica e a escalabilidade simples dos microserviços, temos o desacoplamento oriundo da comunicação asíncrona do message broker, utilizado pelos serviços para se comunicar de forma indireta. As desvantagens do monitoramento e provisionamento complexos continuam.</p>
</li>
<li>
<p>Microserviços (com gerenciador de <em>pipeline</em>)<br>
Temos as três vantagens anterires de stack dinâmica, escalonabilidade simples e desacoplamento, e agora temos a menor complexidade, pois conseguimos observar os passos da request de forma explícita dentro do gerenciador de <em>pipeline</em>.<br>
O provisionamento se torna mais complexo, pois temos de prover manutenção constante para garantir que o gerenciador esteja sempre online, pois o sistema inteiro depende dele. Ele deve ser capaz de gerenciar os erros em cada um dos serviços para reverter os passos anteriores e a incosistência do sistema.</p>
</li>
</ul>
<h4 id="gerenciamento-de-erros-e-volume-de-acessos">Gerenciamento de Erros e Volume de Acessos</h4>
<p>Onde é mais complexo?</p>
<p>Nos processos assíncronos (como <em>message brokers</em>) e com gerenciadores de pipeline. No pipeline, a solução geralmente é realizar um <em>rollback</em> do passo anterior. Entretanto um <em>rollback</em> pode ser complexo de realizar.</p>
<p>Soluções:</p>
<ul>
<li><em>Dead Letter Queue</em><br>
Uma fila separada onde as mensagens de erros ficam para não atrapalhar as mensagens normais.</li>
<li>Filas de Re-tentativas<br>
A request ofensora é repetida diversas vezes até que seja realizada com sucesso, e as mensagens de erro são enviadas para a <em>dead letter queue</em>.</li>
</ul>
<p>Suporte de exercícios <a href="https://github.com/jeffhsta/fundamentos_arquitetura">https://github.com/jeffhsta/fundamentos_arquitetura</a></p>

