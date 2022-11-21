# Cronograma de implementação

# 1. Planejamento e pesquisa
1.1 Requisitos<br/>
1.2 Tecnologias<br/>
1.3 Cronograma de estudos e implementação do projeto<br/>

# 2.1 [6 semanas] Estudo e desenvolvimento - Estudo e implementação da API, na arquitetura RESTFUL e implementação com Spring Boot
<u>Semanas: 06/11, 13/11, 20/11, 27/11, 04/12 e 11/12</u>


### 1) Desenvolver uma API Restful JSON que retorne um quiz a ser resolvido. 
* Implementar a obtenção do questionário. Para obter o questionário, o cliente deve enviar uma solicitação GET.

* Implementar a resolução do questionário, em que o cliente precisa passar o campo "resposta" como parâmetro, usando uma requisição POST, com conteúdo como parâmetro "resposta" e valor.<br/>
<br/>
<hr/>

### 2) Melhorar o Webservice para criar, obter e resolver múltiplos questionários, não apenas um. Armazenamento em memória do serviço, sem armazenamento externo.
* Implementar a criação de um novo questionário, passando um JSON como corpo da solicitação via POST.
* Implementar a obtenção de questionário por "id"
* Implementar a obtenção de todos os questionários existentes no serviço.<br/>
* Implementar a resolução de determinado questionário. O cliente enviará uma solicitação POST e passar o parâmetro "resposta". Esse parâmetro será o índice de uma solicitação escolhida do array "opcoes".<br/>
<hr/>

### 3)  Corrigir o serviço para que não aceite questionários incorretos. Tornar os questionários mais interessantes, com número arbitrário de opções corretas (zerou ou todas). O cliente poderá enviar todas as opções corretas de uma vez, ou zero se todas as opções estiverem erradas.<br/>

<hr/>
* Implementar na solução do questionário, na requisição POST, com o JSON que contém os índices de todas as opções escolhidas como resposta.
<hr/>

### 4) Obter todos os questionários com paginação. O cliente enviará uma solicitação GET. A API deverá retornar uma quantidade limitada de questionários de uma vez, e suportar a capacidade de especificar qual parte dos questionário é necessária.
Obter todas as conclusões de questionários com paginação. O serviço fornecerá uma nova operação para obter todas as conclusões de questionários para um usuário especificado enviando um solicitação GET juntamente com os dados de autenticação do usuário.

Classificar as conclusões da mais recente para a mais antiga.
### 5) Implementar perguntas aleatórias
### 6) Implementar questionário de resposta curta de texto.


### 7) Mover os questionários para o banco de dados.
* Armazenar permanentemente os dados em um banco de dados, para que após o reinício do serviço, não perca todos os questionários criados pelos usuários.

### 8) Análise de estrutura hierárquica do projeto, com relacionamento em banco de dados.

<hr/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>


# 2.2 - [1 semana] Estudo e desenvolvimento - Controle de segurança da API
1. Implementação do modelo de usuários no sistema; 

<u>Semana 18/12</u>



### Parte 1 de Autenticação - Autenticação de usuário no sistema para acessar as requisições da API


#### 8) Autorização dos usuários. Acesso público ou privado
* Melhorar o serviço de suporte aos usuários, e o processo de autorização. Fornecer diferentes privilégios aos usuários, entendendo o que eles fazem no serviço.<br/>
Operações a serem adicionadas:
1) Cadastrar novo usuário, que aceita e-mail com login e senha.
2) Exclusão de questionário, criado pelo usuário atual.<br/>

Implementação de acessibilidade dessas operações. Para realizar qualquer operação com questionários (criar, resolver, obter um, obter todos, deletar), o usuário deverá estar cadastrado e autorizado via HTTP Basic Auth, enviando seu e-mail e senha para cada solicitação. Caso contrário, o serviço retornará o erro. A única operação que não requer autorização será o registro.<br/>
* Não armazenar a senha real no banco de dados. Configurar a criptografia de senha usando alguma biblioteca ou algoritmo.

* Implementar o registro de usuário:<br/>
Enviar uma solicitação via JSON com email e senha.

* Excluir. O usuário poderá excluir um questionário enviando uma requisição DELETE.

<hr/>
Outras implementações<br/>
Implementar PUT ou PATH para atualizar questionários existentes.
<hr/>


### Parte 2 de Autenticação - Configuração de Token de acesso na API


<hr/>

<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>




# 3.1 - [1 semana] Testes de controle de qualidade
<u>Semana 08/01</u>

### Teste manuais
### Testes de performance
<hr/>
<br/>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 4.1 - [1 semana] Estudo sobre performance
<u>Semana 15/01</u>

### Estudo sobre performance 1 - POOL de conexões de servidor para resolver possível lentidão

### Estudo sobre performance 2 - Implementação de Cache para performance

<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 5.1 - [1/2 semana] Autenticação com token em banco de dados
<u>semana 22/01</u><br/>

<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 6.1 - [1/2 semana] Tratamento de erros
### Tratamento de erros
<u>semana 22/01</u><br/>

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

### 4) Implementar limite de tempo para responder questionário.

<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 8.1 - [1 semana] Implementar serviço de notificação ao cliente, para que informe o resultado dos questionários, com algum protocolo como o SMTP
### 11) Implementar serviço de notificação ao cliente, para que informe o resultado dos questionários, com algum protocolo como o SMTP.
<u>Semana 12/02</u>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 9.1 - [1/2 semana] Implementar o protocolo HTTPS de segurança
### 12) Implementar o protocolo HTTPS de segurança
<u>Semana 12/02</u>
<hr/>
<hr/>
<hr/>
<hr/>
<hr/>

# 10.1 - [1 semana] Documentação da API
<u>Semanas 12/02, e semana final</u>

### Documentação da API - Visão geral

### Documentação da API - conexão e autenticação

### Documentação da API - Métodos da API

### Documentação da API - Tratamento de erros


<hr/>
<hr/>
<hr/>
<hr/>
<hr/>
## Instalação do projeto em hospedagem

---------------------------------------------------------------------------------------------------
Aula 22/11/2022
1. Serviço em nuvem e justificativa
- Possíveis serviços de hospedagem do Webservice para gerenciamento de questionários
 * Considerações: Nosso serviço web será implementado em Spring Boot com servidor Tomcat, que é um container de servlets.
 * Precisaremos subir um servidor Tomcat nas hospedagem com querermos implementar.
 1ª opção) Serviço da AWS - especificamente a Amazon EC2
  - Ela pode ser testada gratuitamente
  - O nível gratuito inclui 750 horas de instância Linux e Windows t2.micro ou t3micro, todo mês durante 1 ano.
  - A limitação é que o nível gratuito deve ser usado somente em instâncias micro do EC2.
  - Existem outras instâncias disponíveis que poderão ser pagas futuramente.
 2ª opção) Mocha host
 - Hospedagem Java com Tomcat
  Plano pago 
  - Fornece pacote Tomcat comparitlhado, privado e VPS/nuvem com SSL gatis
      Business PJVM (Tomcat) 64MB Taxa de Instalação	R$26.67
      Business PJVM (Tomcat) 64MB - centerquiz.com (11/22/2022 - 02/21/2023) Plano de 3 Mêses	R$138.55
      Registo de Dominio - centerquiz.com - 1 Ano(s) (11/22/2022 - 11/21/2023)
      + Gestão de DNS *	R$79.76
      Total	R$244.98

3. Captítulo 2 - Arquiteturas e paradigmas de comunicação de sistemas distribuídos
  * Qual arquitetura irá atender o problema do grupo?
     - Cliente-servidor: implementação do protocolo de requisição-resposta, que envolverá a troca por pares de mensagens do cliente para o servidor,
     e então do servidor de volta para o cliente. Através de requisições HTTP na arquitetura RESTful.
<img src="https://user-images.githubusercontent.com/85274838/203180015-831c3210-aea7-43c8-88cb-d1d790aa01f9.png"/>

  * Qual paradigma de comunicação o grupo irá utilizar?
              
