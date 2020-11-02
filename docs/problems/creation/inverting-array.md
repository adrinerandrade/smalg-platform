class Inversao {

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