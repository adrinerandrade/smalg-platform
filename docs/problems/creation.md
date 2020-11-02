[< Home](/smalg-platform)

# Criando um problema

### Abrindo a tela de criação de problemas

No menu lateral da plataforma, clique no item "Novo problema".

### Criando o seu próprio problema

É possível que você crie os seus próprios problemas para serem solucionados por outros usuários. Para isso, é necessário que você realize o login com o Github. Para mais detalhes, acesse [Integração com o Github](/smalg-platform/github-integration).

Após autenticar o processo de criação de um problema será iniciado seguindo os seguintes passos:

### Descrição

Defina um *título* para o problema que será apresentado ao usuário ao ser listado para execução. Em seguida, defina uma descrição que será apresentada ao usuário durante a execução do problema. Basicamente se trata do enunciado do problema. Se você achar interessante, através do editor de texto é possível adicionar conteúdos que expliquem os conceitos que serão abordados, através de *link externos*, *imagens* e *vídeos*.

### Contrato

Nesta etapa ocorre a definição do nome da classe, dos campos e dos métodos que deverão ser implementados. O nome definido na classe recomenda-se que utilize *Pascal Case*. Ele estará disponível posteriormente na definição dos cenário com a primeira letra em minúscula seguindo o padrão da nomenclatura de variáveis em *Camel Case*.

A descrição contida nos campos e nos métodos serão apresentadas ao usuário durante a execução como forma de documentação. Se achar interessante, informe questões sobre o retorno e o parâmetro recebido.

Os parâmetros informados são opcionais, e quando informados mais de uma vez devem ser separados por vírgula (`,`). Exemplo: `<parametro_1>, <parametro_2>`. A nomenclatura recomendada para cada parâmetro também é *Camel Case*.

### Cenários

Na etapa de definição de cenários, você pode criar diferentes cenários para execuções específicas, simulando um ambiente de testes de unidades. O contrato criado e a definição dos cenários definirão então os planos de execução do problema. Durante a execução o usuário poderá executar um cenário por vez.

Para criação dos cenários fazemos as seguintes recomendações:

* Não faça cenários muitos extensos. Quebre em cenários menores que validam situações específicas, pois assim o entendimento da situação é simplificado sendo divido em pequenos fragmentos que em conjunto proporcionam uma compreensão na totalidade. Este é o mesmo conceito aplicado e defendido no desenvolvimento de testes unitários, a validação de casos isolados que em sua totalidade realizam a validação de um todo.

Para cria um cenário basta clicar no botão *Adicionar cenário* e selecioná-lo e alterá-lo pelo que for desejável. A *descrição* do cenário poderá ser consultada pelo usuário durante a execução. Sendo assim, ela pode ser utilizada para contextualizar o aluno informando o que esse cenário é responsável por realizar.

Para codificar você utilizará a [Smalg Javascript](/smalg-platform/languages/smalg-javascript). Acesse a documentação dela para entender o seu funcionamento.

### Solução

Nesta etapa é cadastrada a solução do problema. Ela também é importante para você validar o problema criado juntamente com seu contrato definido e seus cenários. Ela será disponibilizada para o usuário consultar, caso não esteja conseguindo concluir o problema.

A classe gerada para implementação, se observada, seguirá as suas definições de contrato. A programação dela também é realizada através da [Smalg Javascript](/smalg-platform/languages/smalg-javascript).

Após concluir todos os processos, finalize a criação de problemas.

### Disponibilizando o problema

O seu problema poderá ser acessado através da listagem dos problemas de um usuário a partir do Github, o que necessita autenticação no Github.

Se for de sua preferência, também é possível disponibilizar o problema através de um arquivo. Para isso, acesso o repositório criado conforme consta em [Integração com o Github](/smalg-platform/github-integration) e faça o download do arquivo.

### Exemplos

A seguir temos os seguintes exemplos para demonstrar mais detalhadamente o processo de criação de um problema:

* [Criando um problema: Lista Encadeada](/smalg-platform/problems/creation/linked-list)
* [Criando um problema: Lista Dinâmica (Array List)](/smalg-platform/problems/creation/array-list)