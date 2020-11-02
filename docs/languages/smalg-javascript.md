[< Home](/smalg-platform)

# Smalg Javascript

A linguagem a ser utilizada, basicamente é `javascript`, porém, para executar um problema ou realizar a definição dos cenários, são disponibilizados os elementos `context` e `assertion`.

## `context`

O context é o objeto principal e presenta o contexto de execução do momento. Objetos complexos devem ser criados através dele.

### Objetos

Para criar um objeto, chame o método `context.newObject()`. O retorno será uma estrutura que funciona como um objeto chave/valor. Os seguintes métodos podem ser utilizados:

| Método | Descrição |
| - | - |
| `object.set(<chave>, <valor>): void` | Atribui uma propriedade ao objeto. |
| `object.get(<chave>): <valor>` | Recupera um valor de um objeto a partir de uma chave. |

#### Definição de cenários

Na definição dos cenários, é possível acessar o objeto puro armazenado internamente, evitando assim a geração da animação para as assertivas a serem executadas nos cenários. Para isso, acesse a propriedade `<variavelObjeto>.obj`. O retorno será um objeto javascript puro.

### Containers

Para criar um container/vetor, chame o método `context.newContainer(<tamanho>)`. Deverá ser passado por parâmetro o tamanho do container. O retorno será um container que possuirá alocamento baseado em indexes. Os seguintes métodos estão disponibilizados para utilização.

| Método | Descrição |
| - | - |
| `container.set(<indice>, <valor>): void` | Atribui um valor a uma determinada posição do container. Utilize o indice como um inteiro. |
| `container.get(<indice>): <valor>` | Recupera um valor de um objeto a partir de uma chave. |
| `container.size(): <tamanho>` | Recupera o tamanho definido inicialmente para o container. |

#### Definição de cenários

Na definição dos cenários, é possível acessar o array puro armazenado internamente, evitando assim a geração da animação para as assertivas a serem executadas nos cenários. Para isso, acesse a propriedade `<variavelContainer>.container`. O retorno será um array javascript puro.

### Controle

Para maior controle na definição dos cenários, são disponibilizados os seguintes métodos auxiliares:

| Método | Descrição |
| - | - |
| `context.getObjects()` | Retorna todos os objetos existentes no contexto. |
| `context.getContainers()` | Retorna todos os containers existentes no contexto. |
| `context.getPrimitives()` | Retorna todas as primitivas presentes no contexto. |
| `context.clear(<elemento>)` | Sendo passado em elemento por parâmetro, realiza a limpeza do objeto visual. |

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