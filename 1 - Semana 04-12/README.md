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
* Implementar a obtenção do questionário, com três campos: "titulo" (string), texto (string) e "opcoes" (array). Para obter o questionário, o cliente deve enviar uma solicitação GET para "/api/questionario". O servidor deve retornar a estrutura JSON:
```json 
{
    "titulo": "A logo do Java",
    "texto": "O que está declarado no logotipo java?",
    "opcoes": ["Robô", "Folha de chá", "Xícara de café", "Bug"]
}
```
* Implementar a resolução do questionário, em que o cliente precisa passar o campo "resposta" como parâmetro, usando uma requisição POST para /api/questionario, com conteúdo como parâmetro "resposta" e valor. Esse parâmetro é o índice de uma opção escolhida do array "opcoes".<br/>
O servidor deve retornar um JSON com dois campos: "sucesso" (true ou false) e feedback (string).<br/>
Implementar duas resostas possíveis do servidor:
1) resposta correta (POST para /api/questionario com conteúdo resposta = 2):
```json 
{"sucesso": true, "feedback":"Parabéns, você acertou!"}
```
2) Se a resposta estiver incorreta (por exemplo, POST para /api/questionario com conteúdo resposta = 1):
```json
{"sucesso":false, "feedback":"resposta errada! Por favor, tente novamente."}
```
Poderá ser escrita qualquer outra string no  campo "feedback", mas os nomes dos campos e os valores true/false devem corresponder
<br/>
<hr/>

## 2) Melhorar o Webservice para criar, obter e resolver múltiplos questionários, não apenas um. Armazenamento em memória do serviço, sem armazenamento externo.
* Implementar a criação de um novo questionário, passando um JSON como corpo da solicitação via POST para /api/questionarios. O JSON terá quatro campos: "titulo" (string), "texto" (string), "opcoes" (array de string) e "resposta" (índice inteiro da opção correta). Por hora, todas as chaves serão opcionais.
Exemplo:
```json 
{
    "titulo": "A logo do Java",
    "texto": "O que está declarado no logotipo java?",
    "opcoes": ["Robô", "Folha de chá", "Xícara de café", "Bug"],
    "resposta": 2
}
```
o answer igua a 2 corresponde ao terceiro item do array options ("Xícara de café"). A resposta do servidor será um JSON com quatro campos: id, titulo, texto, opcoes. Exemplo:
```json 
{
    "id": 1,
    "titulo": "A logo do Java",
    "texto": "O que está declarado no logotipo java?",
    "opcoes": ["Robô", "Folha de chá", "Xícara de café", "Bug"]
}
```
O campo id é um identificador inteiro exclusivo gerado para o questionário. A resposta pode ou não incluir o campo "resposta", dependendo do cliente.
* Implementar a obtenção de questionário por "id". O cliente enviará uma solicitação GET para /api/questionarios/{id}. Exemplo:
```json 
{
    "id": 1,
    "titulo": "A logo do Java",
    "texto": "O que está declarado no logotipo java?",
    "opcoes": ["Robô", "Folha de chá", "Xícara de café", "Bug"]
}
```
A resposta não incluirá o campo "resposta", caso contrário qualquer usuário poderia encontrar a resposta correta do questionário.<br/>
Se o questionário especificado não existir, o servidor retornará um erro 404 (Not found).
* Implementar a obtenção de todos os questionários existentes no serviço. O cliente enviará uma solicitação GET para /api/questionarios.<br/>
A resposta deverá conter um array JSON de questionários:
```json 
[
    {
        "id": 1,
        "titulo": "A logo do Java",
        "texto": "O que está declarado no logotipo java?",
        "opcoes": ["Robô", "Folha de chá", "Xícara de café", "Bug"]
    },
    {
        "id": 2,
        "titulo": "A última questão",
        "texto": "Qual é a resposta para a última questão da vida, do universo e de tudo?",
        "opcoes": ["Tudo está certo", "42", "2+2=4", "11011100"]
    }  
]
```
A resposta não incluirá o campo answer, caso contrário, qualquer usuário poderá encontrar a resposta para qualquer questionário.<br/>
Se não houver questionários, o serviço retornará um amatriz JSON vazia []. Em ambos os casos o código de status seráa 200 (OK)

* Implementar a resolução de determinado questionário. O cliente enviará uma solicitação POST para /api/questionarios/{id}/resolver e passar o parâmetro "resposta". Esse parâmetro será o índice de uma solicitação escolhida do array "options".<br/>
O serviço retornará um JSON com dois campos: "sucesso" (true ou false), e feedback (string). Haverão três respostas possíveis.<br/>
Se a resposta passada estiver correta (por exemplo, POST para /api/questionarios/1/solve com conteúdo resposta=2)
```json 
{"sucesso":true,"feedback":"Parabéns, você tem acertou!"}
```
Se a resposta estiver incorreta (por exemplo, POST para /api/questionarios/1/resolver com conteúdo resposta = 1)
```json 
{"sucesso":false,"feedback":"resposta errada! Por favor, tente novamente."}
```
Se o questionário especificado não existir, o servidor retornará o erro 404 (Not found).
<br/>
<hr/>

## 3)  Corrigir o serviço para que não aceite questionários incorretos. Tornar os questionários mais interessantes, com número arbitrário de opções correatas (zerou ou todas). O cliente poderá enviar todas as opções corretas de uma vez, ou zero se todas as opções estiverem erradas.<br/>
* Implementar: para criar um novo questionário, o cliente precisará enviar um JSON como corpo para a solicitação POST em /api/questionarios. O JSON deverá conter os campos:
    * titulo: string, necessária.
    * texto: string, necessária.
    * opcoes: array de strings, obrigatório (deverá conter pelo menos 2 itens).
    * resposta: array de índices de opções corretas, opcional, posi todas as opções podem estar erradas.
Exemplo:
```json 
{
    "id": 1,
    "titulo": "Bebidas de café",
    "texto": "Selecione apenas bebidas de café.",
    "opcoes": ["Americano", "Chá", "Cappuccino", "Sprite"],
    "resposta": [0, 2]
}
```
O campo "resposta" igual a [0, 2] corresponde ao primeiro e ao terceiro item da matriz opcoes ("Americano" e "Cappuccino").<br/>
A resposta do servidor é um JSON com quatro campos: id, titulo, texto e opcoes. Exemplo:
```json 
{
    "id": 1,
    "titulo": "Bebidas de café",
    "texto": "Selecione apenas bebidas de café.",
    "opcoes": ["Americano", "Chá", "Cappuccino", "Sprite"]
}
```
O campo id será o identificador inteiro exclusivo gerado para o questionário. A resposta poderá ou não incluir o campo answer, dependendo do cliente.<br/>
Se o JSON da solicitação não contiver titulo ou texto, ou forem strings vazias (""), o servidor deverá responder com o erro 404 (Bad request). Se o número de opções no questionário for menor que 2, o servidor retornará o mesmo código de status.
<hr/>
* Implementar na solução do questionário, na requsição POST para /api/questionarios/{id}/resolver, com o JSON que contém os índices de todas as opções escolhidas como resposta.<br/>
O servidor retornará um JSON com dois campos: sucesso (true ou false) e feedback (string).<br/>
Respostas possíveis:<br/>
Se a resposta passada estiver correta:<br/>

```json 
{"sucesso":true, "feedback":"Parabéns, você acertou!"}
```
Se a resposta passada estiver incorreta:<br/>

```json 
{"sucesso":true, "feedback":"resposta errada! Por favor, tente novamente."}
```

Se o questionário especificado não existir, o servidor retornará o erro 404 (Not found).<br/>

```json 
{"sucesso":true, "feedback":"resposta errada! Por favor, tente novamente."}
```
<br/>
<hr/>

## 4) Obter todos os questionários com paginação. O cliente enviará uma solicitação GET. A API deverá retornar uma quantidade limitada de questionários de uma vez, e suportar a capacidade de especificar qual parte dos questionário é necessária.
Obter todos os questionários com paginação. O cliente enviará uma solicitação GET para /api/questionarios. A API deverá retornar apenas 10 questionários de uma vez, e suportar a capacidade de especificar qual parte dos questionário é necessária.<br/>
A resposta deverá conter um JSON com questionários, dentro de "conteudo" de alguns metadados adicionais.<br/>
Exemplo:

```json 
{
    "totalPaginas": 1,
    "totalElementos": 3,
    "ultimo": true,
    "primeiro": true,
    "ordenar": { },
    "numero": 0,
    "numeroElementos": 3,
    "tamanho": 10,

    "vazio":false,

    "paginavel": { },

    "conteudo": [
        {"id": 102, "titulo": "Teste 1", "texto": "Text 1", "opcoes": ["a", "b", "c"]},
        {"id": 103, "titulo": "Teste 2", "texto": "Text 2", "opcoes": ["a", "b", "c", "d"]},
        {
        "id": 202, "titulo": "Bebidas de café","texto": "Selecione apenas bebidas de café.", "opcoes": ["Americano", "Chá", "Cappuccino", "Sprite"]
    }
    ]
}
```
a API deverá suportar a navegação pelas páginas passando o parâmetro page, para /api/questionarios?pagina=1.<br/>
Se não houver questionários, o content será vazio []. Se o usuário estiver autorizado, o código de status será 200 (OK). Caso contrário, será 401 (Unauthorized).
<br/>
<hr/>
* Obter todas as conclusões de questionários com paginação. O serviço fornecerá uma nova operação para obter todas as conclusões de questionários para um usuário especificado enviando um solicitação GET para /api/questionarios/concluidos juntamnete com os dados de autenticação do usuário. Classificar as conclusõe  da mais recente para a mais antiga.<br/>
Cada resposta será separada por páginas. Retornar um JSON com questionários dentro de "conteudo", e alguns metadados adicionais. Exemplo:<br/>

```json 
{
    "totalPaginas": 1,
    "totalElementos": 5,
    "ultimo": true,
    "primeiro": true,
    "vazio": false,

    "conteudo": [
        {"id": 103, "terminarCom": "Data configurada"},
         {"id": 102, "terminarCom": "Data configurada"},
         {"id": 101, "terminarCom": "Data configurada"}
    ]
}
}
```
<br/>


Como será permitido resolver um questionário várias vezes, a resposta poderá conter questionários duplicados, mas com datas de conclusão diferentes.<br/>
Se não houver questionários, "conteudo" retornará vazio []. Se o usuário estiver autorizado, o código será 200 (OK). Caso contrário, será 401 (Unauthorized)
<hr/>

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