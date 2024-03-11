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

### Método de Refatoração Pull-up field

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

### Método de Refatoração Push-down

O Push Down Method é uma técnica de refatoração de programas que visa **mover um método de uma classe pai para uma classe filha**, quando esse método é usado apenas por uma classe filha específica.

Exemplo: considere um código JS com uma classe pai ```Animal``` e uma classe filha ```Cachorro```. A classe ```Animal``` possui um método ```comer``` que é usado apenas pela classe ```Cachorro```:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }

  comer() {
    console.log(`O animal ${this.nome} está comendo!`);
  }
}

class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
  }

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

const cachorro = new Cachorro('Rex');
cachorro.comer(); // O animal Rex está comendo!
cachorro.latir(); // O cachorro Rex está latindo!
```

Observe que o método comer na classe Animal é usado apenas pela classe Cachorro. Podemos usar o Push Down Method para mover esse método para a classe Cachorro, onde será definido apenas uma vez e não estará presente na classe Animal:

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

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

const cachorro = new Cachorro('Rex');
cachorro.comer(); // O cachorro Rex está comendo!
cachorro.latir(); // O cachorro Rex está latindo!
```

Neste exemplo, o método ```comer``` foi movido para a classe ```Cachorro```. Agora, o método ```comer``` não está presente na classe ```Animal```, evitando código morto.

#### Observações:

Benefícios do Push Down Method:

* Evita código morto: remove métodos da classe pai que não são utilizados por nenhuma classe filha.
* Aumenta a legibilidade: torna o código mais fácil de entender, pois os métodos estão mais próximos das classes que os utilizam.
* Facilita a manutenção: permite modificar o comportamento do método em um único lugar, impactando apenas a classe que o utiliza.

Limitações do Push Down Method:

* Nem sempre é possível: o método só pode ser movido se for usado apenas por uma única classe filha.
* Pode afetar a performance: se o método for muito grande, movê-lo para a classe filha pode aumentar o tamanho da classe e afetar a performance.

Quando usar o Push Down Method:

* Quando um método é usado apenas por uma classe filha.
* Quando você deseja evitar código morto na classe pai.
* Quando você deseja aumentar a legibilidade e facilitar a manutenção do código.

### Método de Refatoração Push-down field

O Push Down Field é uma técnica de refatoração que visa **mover um atributo de uma classe pai para uma classe filha** quando esse atributo é utilizado apenas por essa classe filha.

Exemplo. Considere uma classe pai ```Animal``` e uma classe filha ```Cachorro```. A classe ```Animal``` possui um atributo especie que é usado apenas pela classe ```Cachorro```:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
    this.especie = 'Animal'; // Atributo "especie" definido na classe pai
  }
}

class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
  }

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

const cachorro = new Cachorro('Rex');
console.log(cachorro.especie); // "Animal"
```

Observe que o atributo especie na classe ```Animal``` é usado apenas pela classe ```Cachorro```. Podemos usar o **Push Down Field** para mover esse atributo para a classe ```Cachorro```, onde será definido apenas uma vez e não estará presente na classe ```Animal```:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }
}

class Cachorro extends Animal {
  constructor(nome) {
    super(nome);
    this.especie = 'Cachorro'; // Atributo "especie" movido para a classe filha
  }

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

const cachorro = new Cachorro('Rex');
console.log(cachorro.especie); // "Cachorro"
```

Neste exemplo, o atributo ```especie``` foi movido para a classe ```Cachorro```. Agora, o atributo ```especie``` não está presente na classe ```Animal```, evitando duplicação de código.

#### Observações:

Benefícios do Push Down Field:

* Evita duplicação de código: remove a necessidade de definir o mesmo atributo em múltiplas classes filhas.
* Aumenta a legibilidade: torna o código mais fácil de entender, pois os atributos estão mais próximos das classes que os utilizam.
* Facilita a manutenção: permite modificar o valor do atributo em um único lugar, impactando apenas a classe que o utiliza.

Limitações do Push Down Field:

* Nem sempre é possível: O atributo só pode ser movido se for usado apenas por uma única classe filha.
* Pode afetar a performance: Se o atributo for muito grande, movê-lo para a classe filha pode aumentar o tamanho da classe e afetar a performance.

Quando usar o Push Down Field:

* Quando um atributo é usado apenas por uma classe filha.
* Quando você deseja evitar duplicação de código na classe pai.
* Quando você deseja aumentar a legibilidade e facilitar a manutenção do código.

### Método de Refatoração Extract Subclass

Esse método é utilizado quando uma classe possui funcionalidades que são usada somente em algumas instâncias. Então, você deve remover essas funcionalidades para uma classe específica, ou seja, visa criar uma nova subclasse a partir de uma classe existente, quando um conjunto de funcionalidades dentro da classe original é utilizado apenas por um subconjunto de seus objetos. 

Considere um código JS com uma classe ```Veiculo``` que possui funcionalidades para ```carros``` e ```bicicletas```:

```
class Veiculo {
  constructor(modelo, ano) {
    this.modelo = modelo;
    this.ano = ano;
  }

  dirigir() {
    console.log(`O veículo ${this.modelo} está dirigindo!`);
  }

  pedalar() {
    console.log(`O veículo ${this.modelo} está pedalando!`);
  }
}

const carro = new Veiculo('Fiat Argo', 2023);
carro.dirigir(); // O veículo Fiat Argo está dirigindo!

const bicicleta = new Veiculo('Caloi', 2020);
bicicleta.pedalar(); // O veículo Caloi está pedalando!
```

Observe que a classe ```Veiculo``` possui métodos que são específicos para carros (```dirigir```) e bicicletas (```pedalar```). Podemos usar o Extract Subclass para criar duas novas subclasses: ```Carro``` e ```Bicicleta```, cada uma com seus métodos específicos:

```
class Veiculo {
  constructor(modelo, ano) {
    this.modelo = modelo;
    this.ano = ano;
  }
}

class Carro extends Veiculo {
  constructor(modelo, ano) {
    super(modelo, ano);
  }

  dirigir() {
    console.log(`O carro ${this.modelo} está dirigindo!`);
  }
}

class Bicicleta extends Veiculo {
  constructor(modelo, ano) {
    super(modelo, ano);
  }

  pedalar() {
    console.log(`A bicicleta ${this.modelo} está pedalando!`);
  }
}

const carro = new Carro('Fiat Argo', 2023);
carro.dirigir(); // O carro Fiat Argo está dirigindo!

const bicicleta = new Bicicleta('Caloi', 2020);
bicicleta.pedalar(); // A bicicleta Caloi está pedalando!
```

Neste exemplo, a classe ```Veiculo``` foi dividida em duas subclasses: ```Carro``` e ```Bicicleta```. Cada subclasse possui os métodos específicos para o tipo de veículo que representa.

#### Observações

Benefícios do Extract Subclass:

* Melhora a organização do código: separa funcionalidades distintas em classes diferentes, tornando o código mais organizado e legível.
* Aumenta a legibilidade: facilita a compreensão do código, pois cada classe possui um único propósito.
* Facilita a manutenção: permite modificar funcionalidades específicas sem afetar outras partes do código.

Limitações do Extract Subclass:

* Nem sempre é possível: A técnica só pode ser aplicada se um conjunto de funcionalidades é utilizado apenas por um subconjunto de objetos da classe original.
* Pode aumentar a complexidade do código: Criar muitas subclasses pode aumentar a complexidade do código e dificultar a compreensão.

Quando usar o Extract Subclass:

* Quando uma classe possui funcionalidades que são utilizadas apenas por um subconjunto de seus objetos.
* Quando você deseja melhorar a organização, legibilidade e manutenabilidade do código.
* Quando você deseja aplicar o princípio da responsabilidade única, ou seja, cada classe deve ter um único propósito.
