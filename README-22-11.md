---------------------------------------------------------------------------------------------------
Aula 22/11/2022
### 1. Serviço em nuvem e justificativa
* Possíveis serviços de hospedagem do Webservice para gerenciamento de questionários
   * Considerações: Nosso serviço web será implementado em Spring Boot com servidor Tomcat, que é um container de servlets.
   * Precisaremos subir um servidor Tomcat nas hospedagem com querermos implementar.
#### 1ª opção) Serviço da AWS - especificamente a Amazon EC2
- Ela pode ser testada gratuitamente
- O nível gratuito inclui 750 horas de instância Linux e Windows t2.micro ou t3micro, todo mês durante 1 ano.
- A limitação é que o nível gratuito deve ser usado somente em instâncias micro do EC2.
- Existem outras instâncias disponíveis que poderão ser pagas futuramente.
#### 2ª opção) Mocha host
- Hospedagem Java com Tomcat
Plano pago 
- Fornece pacote Tomcat comparitlhado, privado e VPS/nuvem com SSL gatis
   Business PJVM (Tomcat) 64MB Taxa de Instalação	R$26.67
   Business PJVM (Tomcat) 64MB - centerquiz.com (11/22/2022 - 02/21/2023) Plano de 3 Mêses	R$138.55
   Registo de Dominio - centerquiz.com - 1 Ano(s) (11/22/2022 - 11/21/2023)
   + Gestão de DNS *	R$79.76
   Total	R$244.98

### 2. Captítulo 2 - Arquiteturas e paradigmas de comunicação de sistemas distribuídos
* Qual arquitetura irá atender o problema do grupo?
   - **Cliente-servidor**: implementação do protocolo de requisição-resposta, que envolverá a troca por pares de mensagens do cliente para o servidor,
   e então do servidor de volta para o cliente. Através de requisições HTTP na arquitetura RESTful.
<img src="https://user-images.githubusercontent.com/85274838/203180015-831c3210-aea7-43c8-88cb-d1d790aa01f9.png"/>

* Qual paradigma de comunicação o grupo irá utilizar?
   **Invocação Remota**
   Protocolos de requisição-resposta
      HTTP: um exemplo de protocolo de requisição-resposta

        O protocolo HTTP é implementado sobre TCP. Na versão original do protocolo, cada
      interação cliente-servidor consiste nas seguintes etapas:
      • O cliente solicita uma conexão com o servidor na porta HTTP padrão ou em uma
      porta especificada no URL.
      • O cliente envia uma mensagem de requisição para o servidor.
      • O servidor envia uma mensagem de resposta para o cliente.
      • A conexão é fechada.

      Principais Métodos HTTP
      GET   HEAD    POST  PUT  DELETE  OPTIONS  TRACE
