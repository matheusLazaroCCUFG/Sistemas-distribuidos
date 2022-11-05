# Cronograma de implementação - parte 1

# 1. Planejamento e pesquisa
1.1 Requisitos<br/>
1.2 Tecnologias<br/>
1.3 Cronograma de estudos e implementação do projeto<br/>

# 2.1 [6 semanas] Estudo e desenvolvimento - Estudo e implementação da API, na arquitetura RESTFUL e implementação com Spring Boot
<u>Semanas: 06/11, 13/11, 20/11, 27/11, 04/12 e 11/12</u>


33.1 - Evolução dos micro serviços na internet<br/>
33.2 - Integração de projetos com API REST ou Microserviços<br/>
33.3 - Métodos HTTP de solicitação de requisição<br/>
33.4 - Sistemas Amarrados<br/>
33.5 - Sistemas em arquitetura REST<br/>
33.6 - Modelagem correta de URIs<br/>
33.7 - 6 Regras da da API RESTful verdadeira<br/>
33.8 - Baixando a IDE Spring Tools Suite STS<br/>
33.9 - Criando e configurando um projeto Spring Boot<br/>
33.10 - Criando o primeiro controller e serviço RESTfull<br/>
33.11 - Passando parâmetros para o serviço RESTfull<br/>
33.12 - Retornando usuário em JSON para a tela<br/>
33.13 - Criando serviço RESTful de consulta de usuário<br/>
33.14 - Customizando métodos RESTful e URLs<br/>
33.15 - Baixando e Instalando o PostMan e testando GET<br/>
33.16 - Criando nosso serviço POST e efetuando um cadastro de usuário<br/>
33.17 - Criando a atualização de cadastro com o PUT<br/>
33.18 - Criando a remoção com DELETE<br/>

## 1) Desenvolver uma API Restful JSON que retorne um quiz a ser resolvido. 
* Implementar a obtenção do questionário, com três campos: "titulo" (string), texto (string) e "opcoes" (array). Para obter o questionário, o cliente deve enviar uma solicitação GET.

* Implementar a resolução do questionário, em que o cliente precisa passar o campo "resposta" como parâmetro, usando uma requisição POST, com conteúdo como parâmetro "resposta" e valor.<br/>
<br/>
<hr/>

## 2) Melhorar o Webservice para criar, obter e resolver múltiplos questionários, não apenas um. Armazenamento em memória do serviço, sem armazenamento externo.
* Implementar a criação de um novo questionário, passando um JSON como corpo da solicitação via POST.
* Implementar a obtenção de questionário por "id"
* Implementar a obtenção de todos os questionários existentes no serviço.<br/>
* Implementar a resolução de determinado questionário. O cliente enviará uma solicitação POST e passar o parâmetro "resposta". Esse parâmetro será o índice de uma solicitação escolhida do array "opcoes".<br/>
<hr/>

## 3)  Corrigir o serviço para que não aceite questionários incorretos. Tornar os questionários mais interessantes, com número arbitrário de opções correatas (zerou ou todas). O cliente poderá enviar todas as opções corretas de uma vez, ou zero se todas as opções estiverem erradas.<br/>

<hr/>
* Implementar na solução do questionário, na requsição POST, com o JSON que contém os índices de todas as opções escolhidas como resposta.
<hr/>

## 4) Implementar limite de tempo para responder questionário.
## 5) Implementar perguntas aleatórias
## 6) Implementar questionário de resposta curta de texto.


## 7) Mover os questionários para o banco de dados.
* Armazenar permanentemente os dados em um banco de dados, para que após reinício do serviõ, não perca todos os questionários criados pelos usuários.

## 8) Análise de estrutura hierárquica do projeto, com relacionamento em banco de dados.

33.24 - Criando Relacionamento um para muitos<br/>
33.25 - Evitando recursividade e gerando o JSON de pai e filhos<br/>
33.26 - Cadastrando novos usuários telefones no END-POINT<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>


# 2.2 - [1 semana] Estudo e desenvolvimento - Controle de segurança da API
<u>Semana 18/12</u>

33.30 - Cross Origin - Controle de acesso a API<br/>
33.31 - Cross Origin - Testando a requisição GET e AJAX<br/>
33.32 - Cross Origin - Configuração em controler especifico<br/>
33.33 - Cross Origin - Configuração em END-POINT especifico<br/>
33.34 - Cross Origin - Configuração centralizada<br/>
33.35 - Cross Origin - Testanto a liberacao da API<br/>

## Parte 1 de Autenticação - Autenticação de usuário no sistema para acessar as requisições da API
33.36 - Spring Security - Configurando ROLE<br/>
33.37 - Spring Security - Configurando Usuário<br/>
33.38 - Spring Security - Configurando o Repository e o Service<br/>
33.39 - Spring Security - Configurando o Spring Security<br/>

### 8) Autorização dos usuários. Acesso público ou privado
* Melhorar o serviço de suporte aos usuários, e o processo de autorização. Fornecer diferentes privilégios aos usuários, entendendo o que eles fazem no serviço.<br/>
Operações a serem adicionadas:
1) Cadastrar novo usuário, que aceita e-mail com login e senha.
2) Exclusão de questionário, criado pelo usuário atual.<br/>

Implementçaão de acessibilidade dessas operações. Para realizar qualquer operação com questionários (criar, resolver, obter um, obter todos, deletar), o usuário deverá estar cadastrado e autorizado via HTTP Basic Auth, enviando seu e-mail e senha para cada solicitação. Caso contrário, o serviço retornará o erro. A única operação que não requer autorização será o registro.<br/>
* Não armazenar a senha real no banco de dados. Configurar a criptografia de senha usando alguma biblioteca ou algoritmo.

* Implementar o registro de usuário:<br/>
Enviar uma solicitação via JSON com email e senha.

* Excluir. O usuário poderá excluir um questionário enviando uma requisição DELETE.

<hr/>
Outras implementões<br/>
Implementar PUT ou PATH para atualizar questionários existentes.
<hr/>


## Parte 2 de Autenticação - Configuração de Token de acesso na API
33.40 - JSON Web Token (JWT) - Introdução ao JWT<br/>
33.41 - JSON Web Token (JWT) - Funcionamento e estrutura<br/>
33.42 - JSON Web Token (JWT) - Aparência e padrão de uso<br/>
33.43 - JSON Web Token (JWT) - Estrutura de classes do projeto<br/>
33.44 - JSON Web Token (JWT) - Criando a classe JwtTokenAutenticacaoService<br/>
33.45 - JSON Web Token (JWT) - Criando a classe JwtLoginFilter<br/>
33.46 - JSON Web Token (JWT) - Criando a classe JwtApiAutenticacaoFilter<br/>
33.47 - JSON Web Token (JWT) - Testando a autenticação do JSON<br/>
33.48 - JSON Web Token (JWT) - Ententendo a geração do JWT<br/>
33.49 - JSON Web Token (JWT) - Consultando e Deletando<br/>
33.50 - JSON Web Token (JWT) - Cadastrando e editando<br/>
33.51 - JSON Web Token (JWT) - Restringindo dados do usuário<br/>
33.52 - JSON Web Token (JWT) - Atualizando senha do usuário<br/>

<hr/>

<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>




# 3.1 - [1 semana] Testes de controle de qualidade
<u>Semana 08/01</u>

## Teste manuais
## Testes de performance
<hr/>
<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 4.1 - [1 semana] Estudo sobre performance
<u>Semana 15/01</u>

## Estudo sobre performance 1 - POOL de conexões de servidor para resolver possível lentidão
33.54 - Pool de conexão com Hikari
## Estudo sobre performance 2 - Implementação de Cache para performance
33.55 - Implementando o cache para performance<br/>
33.56 - Conhecendo diferença entre CacheEvict e o CachePUT<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 5.1 - [1/2 semana] Autenticação com token em banco de dados
<u>semana 22/01</u><br/>

33.57 - JSON Web Token (JWT) - Autenticação com TOKEN em banco de dados
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 6.1 - [1/2 semana] Tratamento de erros
## Tratamento de erros
33.27 - Implementando o END-POINT de atualização<br/>
33.29 - Testando a API com PostMan e identificando erros<br/>

33.58 - Liberação de CORS e Allow em Origin, Headers , Methods e Request<br/>
33.59 - Controle de erros da API com @ControllerAdvice, @RestControllerAdvice e @ExceptionHandler<br/>
33.60 - Controle de erros da API - Parte 2<br/>
33.61 - Tratamento do TOKEN Expirado<br/>
33.62 - Padrão DTO (Data Transfer Object) dentro de uma API ou projeto<br/>
33.63 - Atualizando TOKEN em novo login
<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 7.1 - [Foco de 2 semanas] Implementar a interface gráfica
<u>Foco nas Semanas 29/01, 05/02, mas será desenvolvido ao longo do projeto.</u>

* Estudar implementação de front-end com AngularJS
* Implementar limite de tempo para responder questionário

## 4) Implementar limite de tempo para responder questionário.
35.32 - Conhecendo o padrão Model - DAO e Controller

35.1 - Loja de Livros com AngularJS e Spring RESTful<br/>
35.2 - Download e apresentação do projeto completo que será desenvolvido<br/>
35.3 - Importando o projeto no Eclipse e configurando.<br/>
35.4 - Como corrigir erros provenientes da importação de projetos e se livrar do X vermelho<br/>
35.5 - Criando o banco de dados e subindo o sistema<br/>
35.6 - Introdução ao AngularJS 1.6<br/>
35.7 - Criando um projeto AngularJS<br/>
35.8 - Propriedades do AngularJS<br/>
35.9 - Criando um formulário simples em AngularJS<br/>
35.10 - Finalizando um formulário simples em AngularJS<br/>
35.11 - Correção para as próximas aulas<br/>
35.12 - Expressões em AngularJS<br/>
35.13 - Diretivas no AngularJS<br/>
35.14 - Filters em AngularJS<br/>
35.15 - O que são services em AngularJS<br/>
35.16 - Usando o Http e conhecendo o ajax com AngularJS<br/>
35.17 - Montando tabelas de dados<br/>
35.18 - Criando o componente Select com AngularJS e Html<br/>
35.19 - Entendendo sobre o DOM<br/>
35.20 - Conhecendo o Resources Ajax com AngularJS<br/>
35.21 - Conhecendo um pouco de Events no AngularJS<br/>
35.22 - Validando formulários<br/>
35.23 - Animações nas páginas<br/>
35.24 - Formatando um campo de moeda com AngularJS<br/>
35.25 - Conhecendo a injeção de dependência com AngularJS<br/>
35.26 - Criando filter em tabelas de dados<br/>
35.27 - Instalando o Layout BootStrap em nosso projeto<br/>
35.28 - Testando as Rotas do AngularJS<br/>
35.29 - Criando e conhecendo DataSource no Tomcat Apache<br/>
35.30 - Configurando o Hibernate<br/>
35.31 - Configurando o Spring Frameworks<br/>
<hr/>
Back-end modificações
35.32 - Conhecendo o padrão Model - DAO e Controller<br/>

35.33 - Iniciando a criação da lista de cliente<br/>

35.34 - Iniciando a criação da lista de cliente - Parte 2<br/>

35.35 - Iniciando o cadastro de clientes<br/>

35.36 - Editando o cliente e entendedo o RESTful<br/>

35.37 - Adicionando notificação ao nosso sistema<br/>

35.38 - Criando componentes<br/>

35.39 - Criando o select de cidades e estados<br/>

35.40 - Criando o select de cidades e estados - Parte 2<br/>

35.41 - Resolvendo problema com Google Chrome e o Select (Combo)<br/>

35.42 - Conhecendo o Jquery Mask<br/>

35.43 - Criando o Upload de Imagens para nosso projeto<br/>

35.44 - Paginação e desempenho com front e back end<br/>
35.45 - Finando o cadastro de clientes
35.46 - Iniciando o cadastro de fornecedores<br/>
35.47 - Criando o cadastro de livros da nossa loja<br/>
35.48 - Melhorando os cadastros criados<br/>
35.49 - Iniciando a criação da loja de livros<br/>
35.50 - Criando a loja de livros - Parte 2<br/>
35.51 - Criando a loja de livros - Parte 3<br/>
35.52 - Criando a loja de livros - Parte 4<br/>
35.53 - Adicionando cliente a nossa loja de livros<br/>
35.54 - Finalizar o pedido de nossa loja de livros<br/>
35.55 - Imprimindo nosso pedido<br/>
35.56 - Imprimindo nosso pedido - Parte 2<br/>
35.57 - Corrigindo problemas em relatórios<br/>
35.58 - Criando gráfico de pedidos com Google Chart<br/>

35.62 - Escondendo parte com Ng-Hide<br/>
35.63 - Separando os Controllers no AngularJS<br/>
35.64 - UTF-8 e codificação de caracteres<br/>
35.65 - Revisando as configurações do nosso projeto<br/>
35.66 - Redirecionando de acordo com o perfil do usuário<br/>

<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 8.1 - [1 semana] Implementar serviço de notificação ao cliente, para que informe o resultado dos questionários, com algum protocolo como o SMTP
## 11) Implementar serviço de notificação ao cliente, para que informe o resultado dos questionários, com algum protocolo como o SMTP.
<u>Semana 12/02</u>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 9.1 - [1/2 semana] Implementar o protocolo HTTPS de segurança
## 12) Implementar o protocolo HTTPS de segurança
<u>Semana 12/02</u>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 10.1 - [1 semana] Documentação da API
<u>Semanas 12/02, e semana final</u>

## Documentação da API - Visão geral

## Documentação da API - conexão e autenticação

## Documentação da API - Métodos da API

## Documentação da API - Tratamento de erros


<hr/>
<hr/>
<hr/>
<hr/>
<hr/>
## Instalação do projeto em hospedagem
35.61 - Implantando nossa aplicação no servidor<br/>

33.19 - Instalando o MAVEN em nosso computador<br/>
33.20 - Configurando o contexto da nossa aplicação<br/>
33.21 - Revisando configurações da versão do JDK<br/>
33.22 - Gerando Jar executável da Aplicação Spring Boot<br/>
33.23 - Gerando WAR e Implantando no Servidor<br/>
33.28 - Implantando a API na hospedagem<br/>