# Anotações 
Texto 1 - https://medium.com/baseds/many-nodes-one-distributed-system-9921f85205c4
Vídeo 1 - https://www.youtube.com/watch?time_continue=1&v=jSnLOoGjQ80&feature=emb_logo 

Para o dia 01/11 tragam:
1.   os times e os projetos;
Trello: https://trello.com/w/sistemasdistribuidos36
## Time: 
    MATHEUS LÁZARO HONÓRIO DA SILVA
    JOSE TEIXEIRA MENDES JUNIOR
    IGOR MATEUS FRANCA DINIZ LOVI
    Marcos Rodrigues
## Projeto:
Desenvolver um Web Service multiusuário para criar e resolver questionários usando uma API REST, um banco de dados incorporado, segurança e possível interface de usuário (Web ou móvel).

### Descrição:
1. Criação de modelo cliente-servidor, onde o cliente pode ser um navegador, uma ferramenta como o Curl, ou alguma interface de testes como o Postman.
2. Desenvolvimento back-end com contrução de um banco de dados integrado.
3. Utilização do framework Spring Boot para implementação e testes.

### Etapas do projeto:
1. Desenvolvimento de uma API REST JSON que crie ou retorne um Quiz (Questionário) a ser resolvido, suportando a obtenção do Quiz e a solução dele passando-se uma resposta. Podendo ser múltiplos questionários.
2. Impedimento de criação de questionário inconsistente.
3. Criação do banco de dados para armazenamento e manipulação dos questionários.
4. Criação de serviço de suporte aos usuários e processo de autorização. Criação de privilégios a usuários, com cadastro de usuário e exclusão de questionário criado pelo usuário logado.
5. Mecanismo de Atualização dos questionários, através de PUT e PATCH.
6. Criação de paginação ao obter questionários.
7. Obter todas as conclusões de questionários com paginação.
8. Proteção de conexão utilizando protocolo HTTPS.

### Outros possíveis tópicos de sistemas distribuídos a serem aplicados
1. Computação móvel através de criação da interface.
2. Implementação de um cliente de e-mail para informe de resultado dos questionários, com algum protocolo (como o SMTP, por exemplo).

### Tecnologias:
* Spring Framework
* IDE: Eclipse
* Servidor: Tomcat
* Analisador de API: Postman
<br/>
<hr/>

## Perguntas e respostas da aula
### 1) 3 destaques no texto para uma discussão (pode ser por time)
*  https://medium.com/baseds/many-nodes-one-distributed-system-9921f85205c4
<br/>

* <u>Destaque 1</u> - Conceito de "Computação distribuída":<br/> A Computação distribuída geralmente envolve a resolução de problemas, a divisão das coisas em tarefas discretas e a descoberta de como manipular, armazenar e processar dados.
* <u>Destaque 2</u> - Definição de um sistema distribuído:<br/>Contanto que todos os processos em um sistema sejam autônomos ou capazes de realizar suas próprias operações, enquanto também são capazes de se comunicar com outros processos no sistema, podemos classificar o sistema como distribuído.
* <u>Destaque 3</u> - se o sistema envolve processos conversando entre si, então talvez as entidades sejam apenas “processos”.
* <b> Considerando que o nosso projeto busca desenvolver uma API REST de manipulação de Questionários com usuários, podemos considerar que os verbos HTTP implementados servirão para manipular processos, que serão salvos em banco de dados.<br/>
Do ponto de vista das entidades individuais, os nós do nosso sistema serão os usuários, os questionários e, mais intrinsecamente as opções e respostas. (fazendo uma analogia à Teoria dos grafos).</b>
<br/>

### 2) 3 destaques no vídeo para uma discussão (pode ser por time)
* Vídeo 1 - https://www.youtube.com/watch?time_continue=1&v=jSnLOoGjQ80&feature=emb_logo
<br/>

Destaque 1 -<br/> Arquitetura de desenvolvimento para microsserviços
O vídeo começa tratando sobre a diferença entre microsserviços e "grandes serviços", como por exemplo o SOAP.
Nesse contexto, podemos tratar sobre a evolução dos microsserviços na intenet:

Sistemas que trocam informações tinham a mesma rotina escrita várias vezes por equipes diferentes (o que gerava uma bagunça na troca de informações).
A comunicação em XML usando SOAP é extremamente complexa. Dessa forma, surgiu a arquitetura REST, e em sequência a RESTful Microserviços com responsabilidades definidas.

Com isso, cabe destacar sobre a diferença entre sistemas amarrados e a arquitetura REST
Sistemas amarrados, têm:<br/>
a)  a reutilização do back-end não são acessíveis a mais de uma tecnologia.<br/>
b) Consumo alto do servidor.<br/>
c) Manutenção complicada.<br/>
d) Defícil escalar essa aplicação.<br/>
e) Difícil criar instâncias diferentes em servidores.<br/>
Outros...
A arquitetura REST resolve o problema da troca de informação entre sistemas e a amarração entre Front-End e Back-End.
* Outro ponto a ser considerado é que a arquitetura REST permite que todo o Front seja trocado, sem que serja necessário trocar o Back-End, e vice-versa.

Destaque 2 - "As várias carinhas para microsserviços", por exemplo a arquitetura RESTful de requisições HTTP com JSON
* Regras de um sistema RESTful
1. Tem que existir dois papeis, o cliente e o servidor.
2. Stateless: o sistema não pode ter sessões amarradas/criadas para o cliente e as requisições tem que ser realizado em todos os dados do processo, e a resposta ser completa.
3. Precisa permitir que o cache seja feito caso necessário.
4. Interface uniforme: a API não pode fazer distinção de clientes, não pode diferenciar e processar algo diferente para navegador, desktop ou mobile.
5. Sistemas em camadas, entre o cliente e a API devem ser possíveis de se adicionar algum serviço como log da aplicação.
6. Código sobre demanda, por exemplo, javascript, importado direto do servidor da API.

Destaque 3 - Vale a pena usar microsserviços no nosso projeto? monolito (único banco de dados) vs microsserviços



Questionário para pesquisas transversais

Um questionário para uma pesquisa transversal é aquele administrado a uma pequena amostra dentro de um maior população em um curto espaço de tempo. Este tipo de questionário oferece ao pesquisador um breve resumo do que os entrevistados pensam sobre o tempo que a pesquisa é realizada. Esses questionários são comumente curtos e rápidos de responder e são muito úteis na hora de obter uma opinião de uma situação particular. Saiba mais em: O que é um estudo transversal?

Questionário para pesquisas longitudinais

Outro tipo de questionário são aqueles que são aplicados para estudos longitudinais, que ajudam os pesquisadores a observarem e coletarem dados por um longo período. Questionários desse tipo, focados em tendências, são implementados para entender a  mudança ou transformação de um processo por um longo período de tempo. Esses tipos de questionários são administrados para entender como a inclinação ou os gostos das pessoas mudam com o tempo.