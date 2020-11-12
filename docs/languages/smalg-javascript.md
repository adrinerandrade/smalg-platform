[< Home](/smalg-platform)

# Smalg Javascript

A linguagem a ser utilizada é `javascript`, porém, para executar um problema é disponibilizado o elemento `context`.

## `context`

O context é o objeto principal e presenta o contexto de execução do momento. Objetos complexos devem ser criados através dele.

### Objetos

Para criar um objeto, chame o método `context.newObject()`. O retorno será uma estrutura que funciona como um objeto chave/valor. Os seguintes métodos podem ser utilizados:

```javascript
const object = context.newObject();
```

| Método | Descrição |
| - | - |
| `object.set(<chave>, <valor>): void` | Atribui uma propriedade ao objeto. |
| `object.get(<chave>): <valor>` | Recupera um valor de um objeto a partir de uma chave. |

### Containers

Para criar um container/vetor, chame o método `context.newContainer(<tamanho>)`. Deverá ser passado por parâmetro o tamanho do container. O retorno será um container que possuirá alocamento baseado em indexes. Os seguintes métodos estão disponibilizados para utilização.

```javascript
const container = context.newContainer(5);
```

| Método | Descrição |
| - | - |
| `container.set(<indice>, <valor>): void` | Atribui um valor a uma determinada posição do container. Utilize o indice como um inteiro. |
| `container.get(<indice>): <valor>` | Recupera um valor de um objeto a partir de uma chave. |
| `container.size(): <tamanho>` | Recupera o tamanho definido inicialmente para o container. |

### Log

Caso precise logar, utilize `console.log(<valor>)`, aperte `f12` e acompanhe pelo console do navegador.

### Criação de problemas

Se você está criando um problema, acesse a documentação das funcionalidades da linguagem para utilizar na definição de cenários: [Smalg Javascript (Criação de cenários)](/smalg-platform/languages/smalg-javascript-assertion).