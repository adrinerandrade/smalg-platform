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
  Uma Lista Encadeada é uma estrutura de dados linear composta por nós que apontam para o seu próximo vizinho.
	Para criar uma lista encadeada, basta definir um nó inicial e para cada nó existente salvar o seu sucessor.
	A imagem abaixo ilustra uma lista encadeada:
  ```
* Clique no botão ![image](https://drive.google.com/u/0/uc?id=11q6igJBlbEeUYq4ay4bbzxPicPGYc_2t&export=download) disponível da barra de ferramentas do editor de texto. Cole o seguinte endereço no tooltip apresentado: `https://drive.google.com/u/0/uc?id=1LWCd7WTSEP8pER6dUEnAEj05ZcTTh_3t&export=download`.
* ```
  Performática para operações de adição e exclusão de elementos, a lista encadeada não se torna performática em operações de acesso direto a uma posição da lista,
	pois precisa percorrer todos os nós anteriores.
	Existem variações da lista encadeada, como a lista duplamente encadeada, na qual cada nó aponta para o seu sucessor e o seu antecessor.
	Neste exercício trabalharemos apenas com a lista encadeada simples.
  
  Você deverá implementar o método de adição, remoção, obtenção de um elemento, tamanho da lista e verificação se a lista contém um determinado elemento. 
  ```

No exemplo acima, foi primeiro contextualizado o problema, com uma explicação sobre o conteúdo e definido quais eram os objetivos da implementação. Essas etapas são interessantes para oferecer ao usuário um melhor entendimento sobre o assunto a ser abordado.

Se você quiser, pode adicionar materiais complementares a partir de links externos, imagens e vídeos.

`Dica: Apesar das imagens serem acessíveis apenas através de url, é possível hospedá-las em serviços presentes na Web como o Google Drive e One Drive.`

Concluindo esta etapa, clique em **próximo**.

![image](https://drive.google.com/u/0/uc?id=1lYdky7ApuaYnuwdoKuvON_MrYcSxgJ2X&export=download)

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
| `adicionar` | `elemento` | `Adiciona um elemento na lista.` |

Concluindo esta etapa, clique em **próximo**.

![image](https://drive.google.com/u/0/uc?id=15-1pz1B9hLM4kDzrJIHaIZbmWsNpcEhq&export=download)

### Cenários

Clique no botão **ADICIONAR CENÁRIO**. Selecione a aba criada e altere o nome do cenário para **Adicionar**. Na descrição deste cenário, cole a seguinte descrição:

```
Este cenário adiciona 3 elementos na lista.

Para fins de testes, coloque o nome do atributo do nó que possui o valor como "valor" e o atributo que aponta para o próximo nó como "próximo".
```

Cole o seguinte código para este cenário:

```javascript
listaEncadeada.adicionar(1);
listaEncadeada.adicionar(2);
listaEncadeada.adicionar(3);

const objects = context.getObjects();
const containers = context.getContainers();
const primitives = context.getPrimitives();

assertion.assertEquals(3, objects.length, 'O número de objetos deveria ser 3.');
assertion.assertEquals(0, containers.length, 'Não podem ser utilizados containers nesse problema.');
assertion.assertEquals(3, listaEncadeada.obterTamanho(), 'O tamanho da lista encadeada deveria ser 3.');

let objNo = listaEncadeada.noInicial.obj;
assertion.assertEquals(1, objNo['valor'], 'O primeiro elemento não é 1.');
objNo = objNo['proximo'].obj;
assertion.assertEquals(2, objNo['valor'], 'O segundo elemento não é 2.');
objNo = objNo['proximo'].obj;
assertion.assertEquals(3, objNo['valor'], 'O terceiro elemento não é 3.');
```

Crie um novo cenário, chamado **Remover** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 4 elementos na lista. Após isso ele remove um dos elementos, o número 30.

Para fins de testes, coloque o nome do atributo do nó que possui o valor como "valor" e o atributo que aponta para o próximo nó como "próximo".
```

Cole o seguinte código:

```javascript
listaEncadeada.adicionar(20);
listaEncadeada.adicionar(30);
listaEncadeada.adicionar(40);
listaEncadeada.adicionar(50);

listaEncadeada.remover(30);

assertion.assertEquals(3, listaEncadeada.obterTamanho(), 'O tamanho da lista deveria ser 3.');
let objNo = listaEncadeada.noInicial.obj;
assertion.assertEquals(20, objNo['valor'], 'O primeiro elemento não é 20.');
objNo = objNo['proximo'].obj;
assertion.assertEquals(40, objNo['valor'], 'O segundo elemento não é 40.');
objNo = objNo['proximo'].obj;
assertion.assertEquals(50, objNo['valor'], 'O terceiro elemento não é 50.');
```

Crie um novo cenário, chamado **Obter** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 3 elementos na lista. Após isso ele obtém o terceiro elemento da lista.
```

Cole o seguinte código:

```javascript
listaEncadeada.adicionar(20);
listaEncadeada.adicionar(30);
listaEncadeada.adicionar(40);

assertion.assertEquals(40, listaEncadeada.obter(2), 'O valor da posição 2 deveria ser 40.');
```

Crie um último cenário chamado **Contém** e cole a seguinte descrição:

```
Este cenário realiza a inserção de 2 elementos na lista. Após isso, ele verifica se a lista contém o elemento 1 e então verifica se a lista possui o elemento 3 que é inexistente. 
```

Cole o seguinte código:

```javascript
listaEncadeada.adicionar(1);
listaEncadeada.adicionar(2);

assertion.assertEquals(true, listaEncadeada.contem(1), 'A lista deveria conter o elemento 1.');
assertion.assertEquals(false, listaEncadeada.contem(3), 'A lista não deveria conter o elemento 3');
```

![image](https://drive.google.com/u/0/uc?id=1PqHWMOFsJVgiTy0tyze14aC0Yagejitd&export=download)

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

	constructor() {
		this.tamanho = 0;
	}

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
		let noAnterior = null;
		let atual = this.noInicial;
		while (atual) {
			const valor = atual.get('valor');
			if (valor === elemento) {
				noAnterior.set('proximo', atual.get('proximo'));
				atual.set('proximo', null);
				this.tamanho--;
				return;
			} else {
				noAnterior = atual;
				atual = this.noInicial.get('proximo');
			}
		}
	}
	/**
	 * Verifica se um elemento existe na lista
	 */
	contem(elemento) {
		let atual = this.noInicial;
		while (atual) {
			const valor = atual.get('valor');
			if (valor === elemento) {
				return true;
			} else {
				atual = atual.get('proximo');
			}
		}
		return false;
	}
	/**
	 * Retorna o elemento presente na posição informada
	 */
	obter(posicao) {
		let noAtual = this.noInicial;
		for (let i = 0; i < posicao; i++) {
			noAtual = noAtual.get('proximo');
		}
		return noAtual.get('valor');
	}
	/**
	 * Retorna o tamanho da lista
	 */
	obterTamanho() {
		return this.tamanho;
	}

}
```

![image](https://drive.google.com/u/0/uc?id=1HHYdwdIDFJ7f6upeatWcLhNxPq1_ZT5a&export=download)

Você pode clicar em executar o cenário para visualizar o resultado final, como mostra a imagem abaixo:

![image](https://drive.google.com/u/0/uc?id=1yLVa3gclQy20dS25iGuOQD-fGdoj1mGJ&export=download)

Pronto! Agora basta criar o problema para que ele seja publicado e consiga ser utilizado por outros usuários.
