[< Home](/smalg-platform)

# Smalg Javascript (Criação de cenários)

Complementação da documentação da linguagem Smalg Javascript, para a criação de cenários. Os comandos aqui se referem mais a controle e maneiras de manipular os objetos.
Assim, além do `context` é disponibilizado o elemento `assertion`, para realização de assertivas. Caso ainda não tenha vista a documentação do `context`, acesse [Smalg Javascript (Criação de cenários)](/smalg-platform/languages/smalg-javascript).

## `context`

O context é o objeto principal e presenta o contexto de execução do momento. Objetos complexos devem ser criados através dele.

### Objetos

Na definição dos cenários, é possível acessar o objeto puro armazenado internamente, evitando assim a geração da animação para as assertivas a serem executadas nos cenários. Para isso, acesse a propriedade `<variavelObjeto>.obj`. O retorno será um objeto javascript puro.

### Containers

Na definição dos cenários, é possível acessar o array puro armazenado internamente, evitando assim a geração da animação para as assertivas a serem executadas nos cenários. Para isso, acesse a propriedade `<variavelContainer>.container`. O retorno será um array javascript puro.

### Controle

Para maior controle na definição dos cenários, são disponibilizados os seguintes métodos auxiliares:

| Método | Descrição |
| - | - |
| `context.getObjects()` | Retorna todos os objetos existentes no contexto. |
| `context.getContainers()` | Retorna todos os containers existentes no contexto. |
| `context.getPrimitives()` | Retorna todas as primitivas presentes no contexto. |
| `context.clear(<elemento>)` | Sendo passado em elemento por parâmetro, realiza a limpeza do objeto visual. Este método é importante para otimizar a visualização de um cenário. Atualmente, não existe um garbage collector que realiza a limpeza automática dos elementos. |

## `assertion`

Para realizar a asserção dos cenários são disponibilizados os seguintes métodos auxiliares:

| Método | Descrição |
| - | - |
| `assertEquals(<expected>, <atual>, <message>)` | Verifica que o esperado e o atual são iguais. Caso não sejam, é necessário informar a mensagem que instruirá sobre o erro. |
| `assertTrue(<valor>, <message>)` | Verifica se o valor passado é `true`. Caso contrário é lançado um erro com a mensagem informada. |
| `assertFalse(<valor>, <message>)` | Verifica se o valor passado é `false`. Caso contrário é lançado um erro com a mensagem informada. |
| `fail(<message>)` | Força a falha do cenário. Pode ser útil em casos para verificação excepcionais com `try/catch` dentro do cenário. |

### Log

Caso precise logar, utilize `console.log(<valor>)`, aperte `f12` e acompanhe pelo console do navegador.