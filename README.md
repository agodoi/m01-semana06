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

#### Observações

Benefícios do Pull-up Method:

* Evita duplicação de código: Reduz a quantidade de código repetido em diferentes classes.
* Aumenta a legibilidade: Torna o código mais fácil de entender e manter.
* Facilita a manutenção: Permite modificar o comportamento em um único lugar, impactando todas as classes que o utilizam.
* Limitações do Pull-up Method:

Nem sempre é possível: 

* O método só pode ser movido se for usado por todas as classes filhas da mesma forma.
* Pode afetar a performance: Se o método for muito grande, movê-lo para a classe pai pode aumentar o tamanho da classe e afetar a performance.

Quando usar o Pull-up Method:

* Quando um método é duplicado em várias classes filhas.
* Quando o método tem o mesmo comportamento em todas as classes filhas.
* Quando você deseja aumentar a legibilidade e facilitar a manutenção do código.

### Método Pull-up field

Pull-up Field é uma técnica de refatoração de programas que visa **mover um atributo de uma classe filha para uma classe pai**, quando esse atributo é usado por várias classes filhas e possui o mesmo valor em todas elas.

Exemplo em JavaScript:

Considere um código com duas classes filhas, ```Cachorro``` e ```Gato```, que herdam de uma classe pai ```Animal```. Ambas as classes filhas possuem um atributo especie com o mesmo valor:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }
}

//classe Cachorro herdando de Animal
class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
    this.especie = 'Cachorro';
  }
}

//classe Gato herdando de Animal
class Gato extends Animal {
  constructor(nome) {
    super(nome);
    this.especie = 'Gato';
  }
}

// Criando instâncias de Cachorro e Gato
const cachorro = new Cachorro('Rex');
console.log(cachorro.especie); // Cachorro

// Acessando o atributo `especie` nas instâncias
const gato = new Gato('Mia');
console.log(gato.especie); // Gato

```

Observe que o atributo ```especie``` é duplicado nas classes Cachorro e Gato. Podemos usar o Pull-up Field para mover esse atributo para a classe pai Animal, onde será definido apenas uma vez e herdado por ambas as classes filhas:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
    this.especie = 'Animal';
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
console.log(cachorro.especie); // Animal

const gato = new Gato('Mia');
console.log(gato.especie); // Animal
```

Neste exemplo, o atributo especie foi movido para a classe Animal. Agora, ele tem o mesmo valor em ambas as classes filhas, sem duplicação de código.

#### Observações

Benefícios do Pull-up Field:

* Evita duplicação de código: reduz a quantidade de código repetido em diferentes classes.
* Aumenta a legibilidade: torna o código mais fácil de entender e manter.
* Facilita a manutenção: Permite modificar o valor em um único lugar, impactando todas as classes que o utilizam.

Limitações do Pull-up Field:

* Nem sempre é possível: O atributo só pode ser movido se for usado por todas as classes filhas com o mesmo valor.
* Pode afetar a performance: Se o atributo for muito grande, movê-lo para a classe pai pode aumentar o tamanho da classe e afetar a performance.

Quando usar o Pull-up Field:

* Quando um atributo é duplicado em várias classes filhas.
* Quando o atributo tem o mesmo valor em todas as classes filhas.
* Quando você deseja aumentar a legibilidade e facilitar a manutenção do código.
