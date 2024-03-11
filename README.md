# Qualidade de software

# Descrição
Modularizando e organizando o jogo (scripts e cenas). Compartilhamento dos pontos fortes dos códigos já desenvolvidos e dicas para desenvolvimento com Phaser. A atividade em sala auxiliará a produção de artefatos desta sprint.

# Assuntos relacionados
Lógica algorítmica


## 1 Refatoração

A refatoração de programa é o processo de reestruturar e modificar o código fonte de um programa de software, sem alterar seu comportamento externo. 

## Objetivo da Refatoração

Melhorar a qualidade interna do código, tornando-o mais legível, compreensível, eficiente e fácil de dar manutenção, sem introduzir novas funcionalidades ou bugs.

## O que fazer numa Refagoração?

Durante o processo de refatoração, os desenvolvedores podem reorganizar a estrutura do código, renomear variáveis e funções, extrair partes do código para funções separadas, eliminar duplicações, simplificar a lógica do programa e realizar outras mudanças que visam tornar o código mais limpo e claro. 

Isso ajuda a reduzir a complexidade do código, facilitando sua compreensão e modificação no futuro.

## Quando usar Refatoração?

* Quando adicionar uma funcionalidade
* Ao corrigir um bug
* Ao revisar um código

## Métodos de Refatoração

### Método Pull-up

O método "Pull-up Method" na refatoração de programas é uma técnica que visa **mover um método de uma classe filha para uma classe pai**, quando esse método é usado por várias classes filhas e possui o mesmo comportamento em todas elas. 

Isso ajuda a evitar duplicação de código, aumentar a legibilidade e facilitar a manutenção do programa.

Exemplo em JavaScript:

Considere um código JavaScript com duas classes filhas, Cachorro e Gato, que herdam de uma classe pai Animal. Ambas as classes filhas possuem um método comer com o mesmo comportamento:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }
}

class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
  }

  comer() {
    console.log(`O cachorro ${this.nome} está comendo!`);
  }
}

class Gato extends Animal {
  constructor(nome) {
    super(nome);
  }

  comer() {
    console.log(`O gato ${this.nome} está comendo!`);
  }
}

const cachorro = new Cachorro('Rex');
cachorro.comer(); // O cachorro Rex está comendo!

const gato = new Gato('Mia');
gato.comer(); // O gato Mia está comendo!
```

Observe que o método ```comer``` é duplicado nas classes Cachorro e Gato. Podemos usar o "Método Pull-up" para mover esse método para a classe pai ```Animal```, onde será definido apenas uma vez e herdado por ambas as classes filhas:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }

  comer() {
    console.log(`O ${this.constructor.name} ${this.nome} está comendo!`);
  }
}

class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
  }
}

class Gato extends Animal {
  constructor(nome) {
    super(nome);
  }
}

const cachorro = new Cachorro('Rex');
cachorro.comer(); // O Cachorro Rex está comendo!

const gato = new Gato('Mia');
gato.comer(); // O Gato Mia está comendo!
```

Neste exemplo, o método ```comer``` foi movido para a classe ```Animal```. Agora, ele é executado da mesma maneira em ambas as classes filhas, sem duplicação de código.

