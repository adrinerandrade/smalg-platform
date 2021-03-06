[< Home](/smalg-platform)

# Criando um problema: Lista Dinâmica (Array List)

### Sobre

Nesta seção será exemplificado a criação de um problema que explica e demonstra o funcionamento de uma estrutura de dados chamada *lista dinâmica*, popularmente conhecida como *array list*. Para isso, basta seguir os passos abaixo. Para entender a criação de um problema de uma maneira mais genérica, veja o tópico sobre [Criação de problemas](/smalg-platform/problems/creation).

### Abrindo a tela de criação de problemas

No menu lateral da plataforma, clique no item "Novo problema". Caso você não esteja logado, realize o login (mais detalhes em [Integração com o Github](/smalg-platform/github-integration)).

### Descrição

Cole no campo **título** o seguinte valor: `Criando uma Lista dinâmica (Array List)`.

Cole no editor de texto a **descrição** com os seguintes valores:

* ```
  Uma lista dinâmica, popularmente conhecida como Array List, é uma estrutura de dados indexada onde os elementos podem ser obtidos através de um acesso direto. Ela trabalha realizando um realocamento de espaço a partir de um tamanho inicial pre-fixado, permitindo a adição e remoção de novos elementos, de maneira que o consumidor não se preocupe com o gerenciamento do espaço.

  Devido às suas características, as listas dinâmicas são altamente performáticas ao obter elementos, pelo fato dos elementos estarem em endereços já definidos. Por outro lado, essa abstração vem com um custo. O gerenciamento da estrutura consome processamento ao adicionar e remover elementos. Além disso, o consumo de memória será relativo ao espaço alocado e não a quantidade de elementos na lista.
  ```

No exemplo acima, foi primeiro contextualizado o problema, com uma explicação sobre o conteúdo e definido quais eram os objetivos da implementação. Essas etapas são interessantes para oferecer ao usuário um melhor entendimento sobre o assunto a ser abordado.

Se você quiser, pode adicionar materiais complementares a partir de links externos, imagens e vídeos.
`Dica: Apesar das imagens serem acessíveis apenas através de url, é possível hospedá-las em serviços presentes na Web como o Google Drive e One Drive.`

Concluindo esta etapa, clique em **próximo**.

### Contrato

Na etapa de defição do contrato, digite no campo **Nome** o seguinte valor: `ListaDinamica`. Este valor estará disponível posteriormente na criação dos cenários pela variável `listaDinamica`.

Após definir o nome, adicione os seguintes campos:

| Nome | Descrição |
|-|-|
| `tamanho` | `Tamanho da lista` |
| `vetor` | `Vetor onde serão guardados os elementos` |

Após definir os campos, adicione os seguintes métodos:

| Nome | Parâmetros | Descrição | 
|-|-|-|
| `obterTamanho` | - | `Retorna o tamanho da lista` |
| `obter` | `posicao` | `Retorna o elemento presente na posição informada` |
| `contem` | `elemento` | `Verifica se um elemento existe na lista` |
| `remover` | `elemento` | `Remove um elemento da lista` |
| `adicionar` | `elemento` | `Adiciona um elemento na lista` |
| `inicializar` | `fatorInicial` | `Inicializa a lista. O fatorInicial indica o tamanho inicial do vetor.` |

Concluindo esta etapa, clique em **próximo**.

### Cenários

Clique no botão **ADICIONAR CENÁRIO**. Selecione a aba criada e altere o nome do cenário para **Adicionar**. Na descrição deste cenário, cole a seguinte descrição:

```
Este cenário adiciona 6 elementos na lista. O crescimento do vetor deve ser sempre o dobro do tamanho anterior.
```

Cole o seguinte código para este cenário:

```javascript
listaDinamica.inicializar(2);

listaDinamica.adicionar(1);
listaDinamica.adicionar(2);
listaDinamica.adicionar(3);
context.clear(context.getContainers()[0]);
listaDinamica.adicionar(4);
listaDinamica.adicionar(5);
context.clear(context.getContainers()[0]);
listaDinamica.adicionar(6);

const objects = context.getObjects();
const containers = context.getContainers();
const primitives = context.getPrimitives();

assertion.assertEquals(0, objects.length, 'Não podem ser utilizados containers nesse problema.');
assertion.assertEquals(8, containers[0].properties.size, 'O tamanho do segundo container deveria ser 6.');
assertion.assertEquals(1, containers[0].container[0], 'O primeiro elemento deveria ser 1.');
assertion.assertEquals(2, containers[0].container[1], 'O segundo elemento deveria ser 2.');
assertion.assertEquals(3, containers[0].container[2], 'O terceiro elemento deveria ser 3.');
assertion.assertEquals(4, containers[0].container[3], 'O quarto elemento deveria ser 4.');
assertion.assertEquals(5, containers[0].container[4], 'O quinto elemento deveria ser 5.');
assertion.assertEquals(6, containers[0].container[5], 'O sexto elemento deveria ser 6.');
assertion.assertEquals(6, listaDinamica.obterTamanho(), 'O tamanho da lista deveria ser 6.');
```

Crie um novo cenário, chamado **Remover** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 6 elementos na lista. Logo após um dos elementos é removido.
```

Cole o seguinte código:

```javascript
listaDinamica.inicializar(3);

listaDinamica.adicionar(1);
listaDinamica.adicionar(2);
listaDinamica.adicionar(3);
listaDinamica.adicionar(4);
context.clear(context.getContainers()[0]);
listaDinamica.adicionar(5);
listaDinamica.adicionar(6);

listaDinamica.remover(4);

const containers = context.getContainers();

assertion.assertEquals(5, listaDinamica.obterTamanho(), 'O primeiro da lista deveria ser 5.');
assertion.assertEquals(1, containers[0].container[0], 'O primeiro elemento deveria ser 1.');
assertion.assertEquals(2, containers[0].container[1], 'O segundo elemento deveria ser 2.');
assertion.assertEquals(3, containers[0].container[2], 'O terceiro elemento deveria ser 3.');
assertion.assertEquals(5, containers[0].container[3], 'O quarto elemento deveria ser 5.');
assertion.assertEquals(6, containers[0].container[4], 'O quinto elemento deveria ser 6.');
```

Crie um novo cenário, chamado **Obter** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 4 elementos na lista. 
Após isso ele obtem um dos elementos.
```

```javascript
listaDinamica.inicializar(2);

listaDinamica.adicionar(1);
listaDinamica.adicionar(2);
listaDinamica.adicionar(4);
context.clear(context.getContainers()[0]);
listaDinamica.adicionar(5);

assertion.assertEquals(4, listaDinamica.obterTamanho(), 'O primeiro da lista deveria ser 5.');
assertion.assertEquals(4, listaDinamica.obter(2), 'O terceiro elemento deveria ser 4.');
```

Crie um novo cenário, chamado **Contém** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 4 elementos na lista. 
Após ele verifica se a lista contém o número 2 e se não contem um número não existente.
```

```javascript
listaDinamica.inicializar(2);

listaDinamica.adicionar(1);
listaDinamica.adicionar(2);
listaDinamica.adicionar(3);
context.clear(context.getContainers()[0]);
listaDinamica.adicionar(4);


assertion.assertEquals(4, listaDinamica.obterTamanho(), 'O primeiro da lista deveria ser 5.');
assertion.assertEquals(true, listaDinamica.contem(2), 'A lista deveria conter o elemento 2.');
assertion.assertEquals(false, listaDinamica.contem(6), 'A lista não deveria conter o elemento 6.');
```

### Solução

Como solução cadastre o seguinte código:

```javascript
class ListaDinamica {

	/**
	 * Vetor onde serão guardados os elementos
	 */
	vetor;
	/**
	 * Tamanho da lista
	 */
	tamanho;

	constructor() {}

	/**
	 * Inicializa a lista. O fatorInicial indica o tamanho inicial do vetor.
	 */
	inicializar(fatorInicial) {
		this.vetor = context.newContainer(fatorInicial);
		this.tamanho = 0;
	}

	/**
	 * Adiciona um elemento na lista
	 */
	adicionar(elemento) {
		const tamanhoAtual = this.vetor.size();
		if (tamanhoAtual === this.tamanho) {
			const novoVetor = context.newContainer(tamanhoAtual * 2);
			for (let i = 0; i < tamanhoAtual; i++) {
				novoVetor.set(i, this.vetor.get(i));
			}
			this.vetor = novoVetor;
		}
		this.vetor.set(this.tamanho++, elemento);
	}
	/**
	 * Remove um elemento da lista
	 */
	remover(elemento) {
		for (let i = 0; i < this.tamanho; i++) {
			if (this.vetor.get(i) === elemento) {
				this.vetor.set(i, null);
				for (let y = i + 1; y < this.tamanho; y++) {
					this.vetor.set(y - 1, this.vetor.get(y));
					this.vetor.set(y, null);
				}
				this.tamanho--;
			}
		}
	}
	/**
	 * Verifica se um elemento existe na lista
	 */
	contem(elemento) {
		for (let i = 0; i < this.tamanho; i++) {
			if (this.vetor.get(i) === elemento) {
				return true;
			}
		}
		return false;
	}
	/**
	 * Retorna o elemento presente na posição informada
	 */
	obter(posicao) {
		return this.vetor.get(posicao);
	}
	/**
	 * Retorna o tamanho da lista
	 */
	obterTamanho() {
		return this.tamanho;
	}

}
```