# Rest APIs com Python e Flask

Antes de utilizarem Rest APIs, os desenvolvedores utilizavam bancos de dados únicos para aplicações web e aplicativos móveis, causando diversos problemas.

- **Informações do Rest APIs**
    - Criado por Roy Fielding em 2000
    - Soluciona integração Mobile e Web
    - Define, Cria e Disponibiliza recursos via Endpoints (Endereços webs que receberão as requisições dos desenvolvedores)
    - Benefícios
        - Fácil Manutenção
        - Aplicação Segura
        - Provê escalabilidade
    - Bom para a empresa criadora da Rest APIs
    

**Como ativar o ambiente virtual no Windows?**

Com o terminal aberto, digite: 

```sql
.\NomeDoAmbienteVirtual\Scripts\activate.bat
```

ou 

```sql
.\NomeDoAmbienteVirtual\Scripts\activate.**ps1**
```

# **API vs Web Service**

- **APIs**
    - Application Programming Interface - É como uma interface (dispositivo que permite a ligação entre dois sistemas diferentes; conexão, ligação. Modo como um computador apresenta uma informação ao usuário de uma forma específica, numa tela com menus, ícones e etc.) entre dois programas diferentes de modo que eles possam se comunicar um com o outro.
    - Ou seja uma API é a forma que terceiros disponibilizam uma interface de modo que possamos consumir um determinado serviço deles sem nos preocuparmos com a implementação do mesmo.
    - A API funciona como um adaptador que faz a conexão entre diversas linguagens e sistemas diferentes, fazendo meio que uma tradução para essa conexão.

- **Web Services**
    - é uma API projetada para se comunicar obrigatoriamente via rede. Tipicamente, HTTP é o protocolo mais comumente usado para a comunicação.
    - Web Services utilizam SOAP, REST ou XML-RPC como meio de comunicação. Ou seja, quando uma API precisa enviar dados através da rede podemos chamar de Web Services.
    

**Obs.:** Todos os Web Services são APIs, porém nem todas APIs são Web Services.

# REST e HTTP

- **HTTP**
    - **Hyper Text Transfer Protocol** (Mais conhecido HTML - Hyper Text Markup Language - Páginas webs que contém links para outras páginas )
    - **GET** (Ler)- Quando clicamos em um link estamos chamando o método GET do HTTP
    - **POST (Inserir)** - Quando enviamos um formulário, chamamos o método POST
    - PUT (Alterar/Atualizar)
    - DELETE (Remover)

- **REST**
    - Quando fazemos uma requisição no REST para Web Services obtemos apenas dados em JSON ou XML

- URI
    - **Uniform Resource Identifier** - Identificador Uniforme de Recursos - Formação dos endereços Webs
    - Exemplo de URI - [reservahotel.com/hotelLookup.do?cities=Rio-de-Janeiro](http://reservahotel.com/hotelLookup.do?cities=Rio-de-Janeiro) (URI baseado em ação)
    - hotel***Lookup*** → Pesquisar Hoteis
    - ***do*** → Executar
    - ***?*** → Query ou Consulta
    - ***cities*** → Parâmetro chamado cidades
- Estruturando REST API
    - reservahotel.com/hoteis?***cities=Rio-de-Janeiro***

## URI baseado em recursos

- API de redes sociais
    - Criar ou postar mensagens
    - Comentar em mensagens
    - Curtir mensagens
    - Compartilhar mensagens
    - CRUD de usuários
    - CRUD - Create, Read, Update, Delete
    - CRUD da API
        - Criar novo usuário
        - Ler dados de usuários
        - Alterar dados de usuários
        - Deletar usuário
    
    No caso acima se fizermos uma assimilação a pastas a URI para encontrar 
    
    o usuário seria /usuário/nomedousuario
    
    URI de postagem:
    
    /postagens/ID
    
    URI de postagem de determinado usuario:
    
    /usuarios/nomeusuario/postagens
    
    URI de postagem específica de usuario específico
    
    /usuarios/nomeusuario/postagens/id
    
    URI de curtida de postagem + comentario + compartilhamento
    
    postagens/id/comentario
    
    postagens/id/compartilhamento
    
    postagens/id/curtida

### Coleção de recursos

- ***URI de recursos únicos*** chamam-se de instâncias
    - /postagens/ID
- ***URI contendo vários recursos*** chamam-se de coleções
    - /postagens

Contundo em coleções podemos usar parâmetros de consultas por conta do tamanho de informações, seria impossível trazer todas as informações das coleções em apenas 1 lista, portanto podemos usar paginação.

paginação - podemos definir quantas informações podemos definir por página quantos elementos serão exibidos.

**limit** ( parâmetro de consulta ) - Não mais que a quantidade determinada será exibida

**Offset** ( quantidade de elementos serão pulados )

Exemplos:

/postagens?limit=10&offset=30 - pula 30 primeiras linhas, recebendo dados da linha 31 até 40

/postagens?**ano**=2018 - query usando ano

/postagens?ano=2018&limit=10&offset=30