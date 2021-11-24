# http-tupi:  _Descrição DECAT HTTP/Tupi_

## _Rhuan Lima Ruiz de Oliveira_

 [HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Overview) é um protocolo que permite a obtenção de recursos na web. É um protocolo extensível com uso do  cabeçalho ( _headers_) para inclusão de novos campos e valores.  A especificação das mensagens HTTP e extensões estão definidas na [RFC 7230](https://datatracker.ietf.org/doc/html/rfc7230). Nesta RFC são definidos os conceitos de proxy, gateway e túneis HTTP como agentes intermediários capazes de interpretar campos de mensagens de cliente e servidor e em alguns casos traduzir para outros formatos não padronizados pelo HTTP ou redirecionar para servidores internos. Atualmente existe um [grupo de trabalho na Internet](https://httpwg.org/specs/) pesquisando novas extensões para o HTTP. 
 
__Proponha__ uma nova aplicação para resolver um problema específico de um usuário na web. Defina uma nova extensão para o HTTP denominada HTTP Tupi com a inclusão de novos campos de cabeçalho. __Implemente o cliente e servidor HTTP Tupi__, para sua solução proposta. O servidor HTTP Tupi deve ser capaz de reconhecer uma mensagem HTTP Tupi e realizar ações, incluindo a reposta com conteúdo diferente do HTTP/1.1. As respostas podem incluir dados em outros formatos diferentes do HTML, como XML e JSON, por exemplo, de acordo com a especificação de sua proposta.

Se seu servidor receber mensagens sem a extensão do campo proposto, o servidor deve agir de acordo com o protocolo HTTP/1.1. Se a mensagem originada do cliente incluir a extensão no cabeçalho, o servidor deve responder de acodo comm protocolo HTTP Tupi.

## Qual o problema considerado?  
_Justifique a aplicação de sua solução proposta_

>O Departamento de Estatística e Ciências Atuariais (DECAT) está recebendo visitantes e instalou um televisor em sua entrada que exibe a descrição do departamento presente em sua página web. Para isso, sempre que um visitante chega, uma requisição é enviada ao HTTP tupi que retorna um html com a descrição. Ao mesmo tempo, é possível requerer outros arquivos htmls quando a localização é especificada na requisição. Como solicitado pela problemática, também é possível atender requisições do próprio HTTP/1.1.

## Qual o público alvo?  
_Descreva quais os usuários em potencial para sua aplicação web_

> Professores do DECAT e visitantes do departamento.

## Qual a arquitetura?  
_Descreva quais os módulos de hardware, software e protocolos necessários para sua aplicação, restringindo-se às características dos protocolos da camada de aplicação_

> Hardware: Dois computadores, um deles atuando como servidor e o outro como cliente, conectados à mesma rede. Software: qualquer capaz de estabalecer conexão cliente-servidor. Protocolos: HTTP e TCP.

## Qual o formato do protocolo?
_Especifique o que um programador precisa saber para implementar seu protocolo em qualquer linguagem_

>Requisições do protocolo HTTP e especificar a localização dos arquivos html necessários para execução do protocolo.

### Como as mensagens são definidas?
_Especifique mensagens enviadas pelo cliente e respostas do servidor_

>Cliente envia: GET / HTTP/Tupi ou GET / (DESTINO DO ARQUIVO HTML)  
>Servidor responde:   
>HTTP/1.1 200 OK  
>Tupi  
>Server: Apache  
>Content-Type: text/html               
>!DOCTYPE html...  
>(TEXTO EM HTML)  
>                   
>Caso o Cliente envie algo diferente
>Servidor responde: HTTP/1.1 404 Not Found ou HTTP/1.1 400 Bad Request
>
>As requições GET / HTTP/1.1 seguem o padrão.

### Quais os campos definidos?
_campos devem seguir padrão NOME_DO_CAMPO: VALORES_  

>Tupi: 1  
>Server: Apache  
>Content-type: text/html  

### Quais os possíveis valores de cada campo?

>Tupi: 1  
>Server: Apache  
>Content-type: text/html  

## Como a aplicação pode ser testada no Core?
_Descreva como o servidor pode ser implantado e testado, apresentando um manual de uso_ 

> Após abrir o CORE, adiciona um servidor e um cliente a interface e ligar ambos, gerando uma conexão. Em seguida, inicia a sessão e testa conectividade por meio do comando ping. Em procedência, importa-se o código http.py para o servidor e o cliente.py para o cliente. Primeiramente se é executado o código do servidor e em seguida o do cliente. A partir deste momento é possível realizar as requisições definidas acima ao servidor. O usuário possui o poder de alterar os arquivos htmls sem a necessidade de alterar o código fonte do protocolo.

## Faça um registro do funcionamento de sua aplicação 
_Apresente um exemplo de teste mostrando que o cliente e o servior  HTTP Tupi funcionou corretamente

> ![labredes](https://user-images.githubusercontent.com/54746864/143238786-02191d5d-62fc-4211-8f37-f18bb04317cb.png)  
> ![labredes2](https://user-images.githubusercontent.com/54746864/143239006-6f548843-f362-42db-a118-55d54837f596.png)
