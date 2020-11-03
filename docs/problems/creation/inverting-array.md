[< Home](/smalg-platform)

# Invertendo os elementos de um container

### Sobre

Nesta seção será exemplificado a criação de um problema simples, que possui unicamente o objetivo de inverter os elementos de um container. Para entender a criação de um problema de uma maneira mais genérica, veja o tópico sobre [Criação de problemas](/smalg-platform/problems/creation).

### Abrindo a tela de criação de problemas

No menu lateral da plataforma, clique no item "Novo problema". Caso você não esteja logado, realize o login (mais detalhes em [Integração com o Github](/smalg-platform/github-integration)).

### Descrição

Cole no campo **título** o seguinte valor: `Invertendo os elementos de um container`.

Cole no editor de texto a **descrição** com os seguintes valores:

* ```
	Containers, na plataforma, são elementos que possuem um tamanho pré-determinado e com posições indexadas. O objetivo aqui será simples. 
	
	Você receberá um container com 'n' posições e você deverá inverter as posições de todos os seus elementos. Desse modo, o elemento que se encontra na primeira posição deverá ir para a última, o segundo para a penúltima e assim por diante.

	Utilize os métodos get e set para trabalhar com o container.
	```

No exemplo acima, foi primeiro contextualizado o problema, com uma explicação sobre o conteúdo e definido quais eram os objetivos da implementação. Essas etapas são interessantes para oferecer ao usuário um melhor entendimento sobre o assunto a ser abordado.

Se você quiser, pode adicionar materiais complementares a partir de links externos, imagens e vídeos.
`Dica: Apesar das imagens serem acessíveis apenas através de url, é possível hospedá-las em serviços presentes na Web como o Google Drive e One Drive.`

Concluindo esta etapa, clique em **próximo**.

### Contrato

Na etapa de defição do contrato, digite no campo **Nome** o seguinte valor: `ProblemaDeInversao`. Este valor estará disponível posteriormente na criação dos cenários pela variável `problemaDeInversao`.

Não adicione nenhum campo e adicione o seguinte método:

| Nome | Parâmetros | Descrição | 
|-|-|-|
| `inverter` | `vetor` | `Recebe um container/vetor para ter os seus elementos invertidos` |

Concluindo esta etapa, clique em **próximo**.

### Cenários

Clique no botão **ADICIONAR CENÁRIO**. Selecione a aba criada e altere o nome do cenário para **Inverter**. Na descrição deste cenário, cole a seguinte descrição:

```
Este cenário adiciona 6 elementos na lista. O crescimento do vetor deve ser sempre o dobro do tamanho anterior.
```

Cole o seguinte código para este cenário:

```javascript
const container = context.newContainer(5);
container.set(0, 5);
container.set(1, 5);
container.set(2, 1);
container.set(3, 4);
container.set(4, 2);

problemaDeInversao.inverter(container);

assertion.assertEquals(2, container.container[0], 'O primeiro elemento está errado');
assertion.assertEquals(4, container.container[1], 'O segundo elemento está errado');
assertion.assertEquals(1, container.container[2], 'O terceiro elemento está errado');
assertion.assertEquals(5, container.container[3], 'O quarto elemento está errado');
assertion.assertEquals(5, container.container[4], 'O quinto elemento está errado');
```

### Solução

Como solução cadastre o seguinte código:

```javascript
class ProblemaDeInversao {

	constructor() {}

	/**
	 * Recebe um vetor e realiza a inversão dos seus elementos baseando em suas posições.
	 */
	inverter(vetor) {
		const tamanhoVetor = vetor.size();
		for (let indice = 0; indice < (tamanhoVetor - 1) / 2; indice++) {
			const indiceInverso = vetor.size() - 1 - indice;
			const elementoIndice = vetor.get(indice);
			const elementoInverso = vetor.get(indiceInverso);
			vetor.set(indiceInverso, elementoIndice);
			vetor.set(indice, elementoInverso);
		}
	}

}
```