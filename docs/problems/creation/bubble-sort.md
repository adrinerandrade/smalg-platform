[< Home](/smalg-platform)

# Ordenando uma lista com o método bolha (Bubble Sort)

### Sobre

Nesta seção será exemplificado a criação de um problema que ordena um container/vetor através do método bolha (Bubble Sort). Para entender a criação de um problema de uma maneira mais genérica, veja o tópico sobre [Criação de problemas](/smalg-platform/problems/creation).

### Abrindo a tela de criação de problemas

No menu lateral da plataforma, clique no item "Novo problema". Caso você não esteja logado, realize o login (mais detalhes em [Integração com o Github](/smalg-platform/github-integration)).

### Descrição

Cole no campo **título** o seguinte valor: `Ordenando através do método bolha (Bubble Sort)`.

Cole no editor de texto a **descrição** com os seguintes valores:

* ```
	O método bolha é um método de ordenação simples. Ele é executado percorrendo o vetor diversas vezes com o objetivo de a cada percorrida completa no vetor transferir o menor elemento para o topo da lista (no caso de uma ordenação crescente).

  Sendo assim, no primeira vez que o vetor é percorrido, o menor elemento da lista é jogado para a primeira posição. Na segunda vez, o segundo menor elemento vai para a segunda posição e assim por diante. A cada verificação, ocorre uma comparação entre o elemento de uma determinada posição `n` e o elemento da posição `n + 1`. Se o elemento na posição `n + 1` for menor, são trocadas as posições. 

  Para realizar uma ordenação decrescente basta inverter a lógica.

  Apesar do método bolha ser amplamente conhecido no mundo da programação ele não é o método de ordenação mais efetivo. 
	```

No exemplo acima, foi primeiro contextualizado o problema, com uma explicação sobre o conteúdo e definido quais eram os objetivos da implementação. Essas etapas são interessantes para oferecer ao usuário um melhor entendimento sobre o assunto a ser abordado.

Se você quiser, pode adicionar materiais complementares a partir de links externos, imagens e vídeos.
`Dica: Apesar das imagens serem acessíveis apenas através de url, é possível hospedá-las em serviços presentes na Web como o Google Drive e One Drive.`

Concluindo esta etapa, clique em **próximo**.

### Contrato

Na etapa de defição do contrato, digite no campo **Nome** o seguinte valor: `BubbleSort`. Este valor estará disponível posteriormente na criação dos cenários pela variável `bubbleSort`.

Não adicione nenhum campo e adicione o seguinte método:

| Nome | Parâmetros | Descrição | 
|-|-|-|
| `ordenar` | `vetor` | `Recebe um container/vetor que deverá ser ordenado conforme a implementação do método bolha.` |

Concluindo esta etapa, clique em **próximo**.

### Cenários

Clique no botão **ADICIONAR CENÁRIO**. Selecione a aba criada e altere o nome do cenário para **Ordenar**. Na descrição deste cenário, cole a seguinte descrição:

```
Realize a ordenação do container/vetor recebido utilizando o método bolha conforme explicado na descrição do problema.
```

Cole o seguinte código para este cenário:

```javascript
const container = context.newContainer(5);
container.set(0, 5);
container.set(1, 2);
container.set(2, 3);
container.set(3, 1);
container.set(4, 4);

bubbleSort.ordenar(container);

const raw = container.container;
assertion.assertEquals(1, raw[0], 'O primeiro elemento está inválido.');
assertion.assertEquals(2, raw[1], 'O segundo elemento está inválido.');
assertion.assertEquals(3, raw[2], 'O terceiro elemento está inválido.');
assertion.assertEquals(4, raw[3], 'O quarto elemento está inválido.');
assertion.assertEquals(5, raw[4], 'O quinto elemento está inválido.');
```

### Solução

Como solução cadastre o seguinte código:

```javascript
class BubbleSort {

	constructor() {}

	ordenar(vetor) {
		// Variável que otimiza a ordenação parando-a
		// caso não tenha mais itens a serem ordenados
		let trocou = false;

		let ultimo_indice = 0;

		do {
			trocou = false;
			for (let i = vetor.size() - 2; i >= ultimo_indice; i--) {
				const elemento_1 = vetor.get(i + 1);
				const elemento_2 = vetor.get(i);
				if (elemento_1 < elemento_2) {
					vetor.set(i + 1, elemento_2);
					vetor.set(i, elemento_1);
					trocou = true;
				}
			}
			ultimo_indice++;
		} while (trocou);
	}

}
```