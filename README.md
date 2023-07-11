# Primeiros passos com Spring BOOT

O Spring Boot é uma ferramenta que visa facilitar o processo de configuração e publicação de aplicações que utilizem o ecossistema Spring.

O Spring Boot fornece a maioria dos componentes baseados no Spring, necessários em aplicações de maneira pré-configurada, tornando possível termos uma aplicação rodando em produção rapidamente e com o esforço mínimo de configuração e implantação.

No final, a será gerado um projeto Maven ou Gradle, que são gerenciadores de dependências da linguagem Java (semelhante ao NPM do JavaScript/Typescript), pré-configurado e com todos os componentes solicitados especificados. Nossos projetos Spring Boot utilizarão o Maven como Gerenciador Dependências.

## Apacha Maven
A palavra Maven significa acumulador de conhecimento. No Universo Java, o Maven é uma ferramenta usada para construir e gerenciar qualquer projeto Java, tornando o trabalho diário dos desenvolvedores mais fácil, além de simplificar a compreensão de qualquer projeto baseado na linguagem Java.

[Documentação Apache Maven](https://maven.apache.org/guides/index.html)

Entre as principais características do Maven, destaca-se:

1. Gerenciador de dependências:
O Maven é responsável por fazer o download das bibliotecas que você vai precisar no seu projeto. Para efetuar esta tarefa, o Maven utiliza o arquivo pom.xml, onde você precisa declarar todas as dependências necessárias para o seu projeto.

2. Repositório central:
Todas as ferramentas e bibliotecas utilizadas nos projetos Spring Boot estão disponíveis em um único servidor na nuvem chamado Maven Central Repository. O Maven Repository facilita e centraliza o download de todas as dependências independente de serem as oficiais do Spring ou Desenvolvidas por outras Empresas ou Pessoas Desenvolvedoras (Lombok, Flyway, MOckito, entre outras), dispensando a necessidade de procurar as dependências no Google, por exemplo.

3. Automatizador de tarefas:
Um projeto que possui muitas bibliotecas e muitas dependências gera alguns problemas no dia a dia, tais como: manter todas atualizadas, fazer o build da sua aplicação, realizar alguns testes e etc. O MAVEN auxilia nestes e outros processos através dos seus scripts prontos que automatizam todas estas tarefas.

### Como funciona um projeto SPRING BOOT?
A Classe Principal, que possui o Método main, inicia um servidor WEB (TOMCAT), que vai gerenciar todas as URL's (Endpoints) disponíveis na API.
Cada URL deve ser mapeada para um determinado Método de uma Classe.
A execução desse Método retornará uma resposta quando acionamos a URL.
A partir daí, criamos nossos objetos que implementarão todas as lógicas necessárias.

### Como planejar um projeto SPRING BOOT?
Quais ENDPOINTS vamos oferecer? (Um Endpoint é uma URL associada a um Método do protocolo HTTP: GET, POST, PUT, DELETE).

Em geral, temos 1 Endpoint para cada Método HTTP (podemos ter mais de um desde que os endereços sejam diferentes), em cada objeto do nosso modelo de negócios:

Objeto de Negócios: PRODUTO

- URL para recuperar dados de um produto (GET)
- URL para inserir novo produto (POST)
- URL para atualizar dados de um produto (PUT)
- URL para remover um produto do sistema (DELETE)

## Projeto - Loja Games
Dentro do STS, utilize o caminho File -> New -> Spring Starter Project para criar seu projeto Spring
![Captura de tela 2023-07-11 190003](https://github.com/mateuzu/ProjetoLojaGames_Generation/assets/102612137/e190ef09-6780-485c-927a-de9548b23e0b)

No print abaixo, veremos algumas configurações iniciais para criação do projeto:
![Captura de tela 2023-07-11 185938](https://github.com/mateuzu/ProjetoLojaGames_Generation/assets/102612137/e6f81734-cd49-40e9-b2dd-361c9ce7e819)

<table>
  <tr>
    <th>Item </th>
    <th>Descrição</th>
  </tr>
  <tr>
    <td>Project</td>
    <td>Define o Gerenciador de Dependências (Maven Project).</td>
  </tr>
    <td>Language</<td>
    <td>Define a Linguagem (Java).</td>
  </tr>
  <tr>
    <td>Spring Boot</td>
    <td>Define a versão do Spring Boot, que será utilizada. Mantenha a versão indicada pelo Spring Initializr.</td>
  </tr>
  <tr>
    <td>Group</td>
    <td>O Endereço reverso do Domínio da sua Empresa ou Organização. Exemplo: generation.com 🡪 com.generation</td>
  </tr>
  <tr>
    <td>Artifact</td>
    <td>O artefato a ser gerado, ou seja, o mesmo nome do projeto.</td>
  </tr>
  <tr>
    <td>Name</td>
    <td>Nome do Projeto (letras minúsculas, sem acentos ou espaços).</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Breve descrição do projeto.</td>
  </tr>
  <tr>
    <td>Package Name</td>
    <td>Estrutura do pacote inicial da aplicação (Group + Artifact). Exemplo: com.generation.helloworld</td>
  </tr>
   <tr>
    <td>Packaging</td>
    <td>Define como a aplicação será empacotada (JAR).</td>
  </tr>
   <tr>
    <td>Java Version	</td>
    <td>Versão do Java (a versão da imagem pode ser diferente da sua tela).</td>
  </tr>
</table>

## Entendendo a estrutura do projeto
<table>
  <tr>
    <th>Item </th>
    <th>Descrição</th>
  </tr>
  <tr>
    <td>src/main/java</td>
    <td>	Source Folder mais importante da aplicação, onde será desenvolvido todo o código da nossa aplicação dentro do pacote principal (em nosso exemplo: com.helloworld.helloworld). Dentro deste pacote existe um arquivo com o nome do projeto + a palavra Application (em nosso exemplo: HelloworldApplication.java), que é responsável por inicializar a aplicação (Classe Main).Não apague este arquivo ou altere a estrutura de pastas do projeto</td>
  </tr>
    <td>src/main/resources</<td>
    <td>DSource Folder responsável por manter os recursos da aplicação, ou seja, os arquivos de configuração do projeto. O mais importante deles é o application.properties, que é o responsável por manter as configurações de Data, Hora, Fuso-horário, Banco de Dados, entre outras</td>
  </tr>
  <tr>
    <td>src/test/java</td>
    <td>	Source Folder onde serão desenvolvidas as Classes de Teste da aplicação, dentro do pacote de testes. Observe que o nome do pacote é o mesmo do pacote da Source Folder Principal.</td>
  </tr>
  <tr>
    <td>JRE System Library</td>
    <td>Neste pacote, o Maven faz o download do Compilador Java (JDK) durante a importação do projeto para o STS</td>
  </tr>
  <tr>
    <td>Maven Dependencies</td>
    <td>Neste pacote, o Maven faz o download de todas as Dependências inseridas no projeto (ver arquivo pom.xml) durante a importação do projeto para o STS</td>
  </tr>
  <tr>
    <td>pom.xml</td>
    <td>O Project Object Model (POM) é o arquivo principal de configuração do Maven. É um arquivo XML que contém informações sobre o projeto e detalhes de configuração usados pelo Maven para construir o projeto. Não apague este arquivo e ao fazer alterações tenha muito cuidado para manter a estrutura do arquivo.</td>
  </tr>
</table>
 

## Dependências
As dependências do Spring Boot são bibliotecas de software adicionais que são incluídas em um projeto para aproveitar os recursos e funcionalidades fornecidos pelo Spring Boot. O Spring Boot é um framework de desenvolvimento de aplicativos Java que simplifica a criação de aplicativos autônomos e prontos para produção.

As dependências do Spring Boot são projetadas para facilitar o desenvolvimento, fornecendo funcionalidades prontas para uso que você pode adicionar ao seu aplicativo com apenas algumas configurações. Essas dependências podem incluir recursos, as principais dependências são:

- Spring Boot Starter Web: Essa dependência é essencial para criar APIs RESTful com o Spring Boot. Ela inclui o Spring MVC (Model-View-Controller) e configurações relacionadas para a criação de endpoints REST.
- Spring Boot Starter Data JPA: Interagir com um banco de dados relacional, essa dependência é útil. Ela inclui o Spring Data JPA, que facilita a implementação de camadas de acesso a dados e operações de persistência.
- Spring Boot Starter Validation: Validar os dados recebidos pela API, essa dependência é útil. Ela inclui o Spring Validation, que fornece anotações para validar e restringir os dados de entrada.
- Spring Boot Starter Test: Facilita a escrita de testes para sua API REST com o uso do framework de teste do Spring Boot. Você pode testar seus controladores, serviços e componentes de forma fácil e eficiente.
- Spring Boot Starter Security:Inclui o Spring Security, que permite configurar autenticação e autorização para proteger seus endpoints.

## Importando um projeto Spring para o STS
Para importar um projeto em Spring para a IDE STS basta seguir esse caminho: File -> Import -> Existing Maven Projects

![Importar projeto](https://camo.githubusercontent.com/6c4e3ea21a2ea93c06c9655279d47feae25d6c4fffd76b256efb0d0916787b5b/68747470733a2f2f692e696d6775722e636f6d2f64526634426d322e706e67)

No item Root Directory, clique no botão Browse e selecione a pasta do projeto (indicado em azul na imagem abaixo).
Em Projects, selecione o arquivo pom.xml e clique no botão Finish para concluir a importação

![Importar projeto](https://camo.githubusercontent.com/fa8a723f585995815706247c80e48f8e34911e8b9631762de18619271785e35e/68747470733a2f2f692e696d6775722e636f6d2f6a6d496947706d2e706e67)

[Voltar](https://github.com/mateuzu/Spring_Generation)
