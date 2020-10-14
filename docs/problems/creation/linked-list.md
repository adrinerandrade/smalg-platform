[< Home](/smalg-platform)

# Criando um problema: Lista Encadeada

### Sobre

Nesta seção será exemplificado a criação de um problema que explica e demonstra o funcionamento de uma estrutura de dados chamada *lista encadeada*. Para isso, basta seguir os passos abaixo. Para entender a criação de um problema de uma maneira mais genérica, veja o tópico sobre [Criação de problemas](/smalg-platform/problems/creation).

### Abrindo a tela de criação de problemas

No menu lateral da plataforma, clique no item "Novo problema". Caso você não esteja logado, realize o login (mais detalhes em [Integração com o Github](/smalg-platform/github-integration)).

### Descrição

Cole no campo **título** o seguinte valor: `Criando uma Lista Encadeada`.

Cole no editor de texto a **descrição** com os seguintes valores:

* ```
  Uma Lista Encadeada é uma estrutura de dados linear composta por nós que apontam para o seu próximo vizinho. Para criar uma lista encadeada, basta definir um nó inicial e para cada nó existente salvar o seu sucessor. A imagem abaixo ilustra uma lista encadeada:
  ```
* Clique no botão ![image](https://drive.google.com/u/0/uc?id=11q6igJBlbEeUYq4ay4bbzxPicPGYc_2t&export=download) disponível da barra de ferramentas do editor de texto. Cole o seguinte endereço no tooltip apresentado: `https://drive.google.com/u/0/uc?id=1LWCd7WTSEP8pER6dUEnAEj05ZcTTh_3t&export=download`.
* ```
  Performática para operações de adição e exclusão de elementos, a lista encadeada não se torna performática em operações de acesso direto a uma posição da lista, pois precisa percorrer todos os nós anteriores. Existem variações da lista encadeada, como a lista duplamente encadeada, na qual cada nó aponta para o seu sucessor e o seu antecessor. Neste exercício trabalharemos apenas com a lista encadeada simples.
  
  Você deverá implementar o método de adição, remoção, obtenção de um elemento, tamanho da lista e verifição se a lista contém um determinado elemento. 
  ```

No exemplo acima, foi primeiro contextualizado o problema, com uma explicação sobre o conteúdo e definido quais eram os objetivos da implementação. Essas etapas são interessantes para oferecer ao usuário um melhor entendimento sobre o assunto a ser abordado.

Se você quiser, pode adicionar materiais complementares a partir de links externos, imagens e vídeos.

`Dica: Apesar das imagens serem acessíveis apenas através de url, é possível hospedá-las em serviços presentes na Web como o Google Drive e One Drive.`

Concluindo esta etapa, clique em **próximo**.

### Contrato

Na etapa de defição do contrato, digite no campo **Nome** o seguinte valor: `ListaEncadeada`. Este valor estará disponível posteriormente na criação dos cenários pela variável `listaEncadeada`.

Após definir o nome, adicione os seguintes campos:

| Nome | Descrição |
|-|-|
| `tamanho` | `Tamanho da lista` |
| `noInicial` | `Primeiro nó da lista` |
| `noFinal` | `Último nó da lista` |

Após definir os campos, adicione os seguintes métodos:

| Nome | Parâmetros | Descrição | 
|-|-|-|
| `obterTamanho` | - | `Retorna o tamanho da lista` |
| `obter` | `posicao` | `Retorna o elemento presente na posição informada` |
| `contem` | `elemento` | `Verifica se um elemento existe na lista` |
| `remover` | `elemento` | `Remove um elemento da lista` |
| `adicionar` | `elemento` | `Adiciona um elemento na lista` |

Concluindo esta etapa, clique em **próximo**.

### Cenários

Clique no botão **ADICIONAR CENÁRIO**. Selecione a aba criada e altere o nome do cenário para **Adicionar**. Na descrição deste cenário, cole a seguinte informação:

```
Este cenário apenas 3 elementos na lista. Após isso, obtém o tamanho da lista e os valores para validar a ordem de inserção.
```

Cole o seguinte código para este cenário:

```javascript
const primitive_1 = context.newPrimitive(1);
const primitive_2 = context.newPrimitive(2);
const primitive_3 = context.newPrimitive(3);

listaEncadeada.adicionar(primitive_1);
listaEncadeada.adicionar(primitive_2);
listaEncadeada.adicionar(primitive_3);

const objects = context.getObjects();
const containers = context.getContainers();
const primitives = context.getPrimitives();

assertion.assertEquals(3, objects.length, 'O número de objetos deveria ser 3.');
assertion.assertEquals(0, objects.length, 'Não podem ser utilizados containers nesse problema.');
assertion.assertEquals(3, listaEncadeada.obterTamanho());

assertion.assertEquals(primitive_1, listaEncadeada.obter(0), 'O primeiro elemento não é 1.');
assertion.assertEquals(primitive_2, listaEncadeada.obter(1), 'O segundo elemento não é 2.');
assertion.assertEquals(primitive_3, listaEncadeada.obter(2), 'O terceiro elemento não é 3.');
```

### Solução

Como solução cadastre o seguinte código:

```javascript
class ListaEncadeada {

	/**
	 * Último nó da lista
	 */
	noFinal;
	/**
	 * Primeiro nó da lista
	 */
	noInicial;
	/**
	 * Tamanho da lista
	 */
	tamanho;

	constructor() {}

	/**
	 * Adiciona um elemento na lista
	 */
	adicionar(elemento) {
		const no = context.newObject();
		if (!this.noInicial) {
			this.noInicial = no;
		}
		no.set('valor', elemento);
		if (this.noFinal) {
			this.noFinal.set('proximo', no);
		}
		this.noFinal = no;
		this.tamanho++;
	}
	/**
	 * Remove um elemento da lista
	 */
	remover(elemento) {
		
	}
	/**
	 * Verifica se um elemento existe na lista
	 */
	contem(elemento) {
		
	}
	/**
	 * Retorna o elemento presente na posição informada
	 */
	obter(posicao) {
		let noAtual = this.noInicial;
		for (let i = 0; i < this.tamanho; i++) {
			noAtual = this.noAtual.get('proximo');
		}
		return noAtual.get('valor');
	}
	/**
	 * Retorna o tamanho da lista
	 */
	obterTamanho() {
		
	}

}
```
