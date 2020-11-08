[< Home](/smalg-platform)

# Visualização da execução

### Organização

A visualização de um problema é contruída com base na interação que se tem com a engine de execução de código e seus elementos. No momento, a visualização não realiza a organização dos elementos automaticamente, mas ela permite a interação do usuário que pode realizar a organização conforme sua preferência.

### Elementos

Os elementos do cenário são interativos, com exceção dos tipos primitivos.

- Objetos: Representam uma estrutura que trabalha em cima de chave/valor.

![image](https://drive.google.com/u/0/uc?id=1G0VTm_wsSeSxle9P6rCsg6q-yPcM4JCf&export=download)

- Containers: Representam uma estrutura indexada com funcionamento equivalente a um vetor.

![image](https://drive.google.com/u/0/uc?id=1036f3xE9rq6UcJMoVS825v1aRxBH-qqx&export=download)

- Primitivas: Representam valores do tipo número, string ou booleano.
  
![image](https://drive.google.com/u/0/uc?id=18rsuyPpAgrMzHB7l4Tql1siwIvM_t-5-&export=download)

### Relacionamentos:

Quando um elemento é referenciado, o seu comportamento irá variar conforme o seu tipo. Sendo assim, tipos primitivos serão tratados com cópia e os tipos complexos serão através de referência.

![image](https://drive.google.com/u/0/uc?id=1bnx3X7anVbhw5kfMkpjaY2rYX-T5-jkw&export=download)

### Controle de execução

Durante a execução do cenário é possível controlar a execução através do componente de controle de execução: 

![image](https://drive.google.com/u/0/uc?id=13TMGBxZ12QRu6dko1Ttek2nEf8uzFP5I&export=download)

A seguir uma descrição de cada um dos botões:

* **Parar**: Interrompe a visualização;
* **Passo anterior**: Quando a execução está pausada, permite voltar ao passo anterior da visualização;
* **Resumir**: Retoma a execução automática;
* **Pausar**: Quando a visualização está em execução automática, permite pausar a execução;
* **Próximo passo**: Quando a execução está pausada, permite executar o próximo passo, trabalhando de maneira incremental.

### Botões auxiliares

* **Centralizar**: Pressione o botão centralizar para que a visualização seja centralizada.