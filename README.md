# Qualidade de software

# Descrição
Modularizando e organizando o jogo (scripts e cenas). Compartilhamento dos pontos fortes dos códigos já desenvolvidos e dicas para desenvolvimento com Phaser. A atividade em sala auxiliará a produção de artefatos desta sprint.

# Assuntos relacionados
Lógica algorítmica


## O que é Qualidade de Software?

É um conjunto de características que um software, antes de ser posto para produção, deve ter para atender às necessidades dos seus usuários e às expectativas dos stakeholders. Ela envolve diversos aspectos, como:

* Conformidade com requisitos: o software deve atender aos requisitos especificados pelos usuários e stakeholders.
* Ausência de defeitos: ele deve estar livre de erros e bugs que afetem seu funcionamento.
* Usabilidade: deve ser fácil de usar e entender pelos usuários.
* Manutenabilidade: deve ser fácil de modificar e corrigir quando necessário.
* Segurança: deve ser protegido contra acessos não autorizados e ataques cibernéticos.
* Escalabilidade: deve ser capaz de lidar com o aumento da carga de trabalho e do número de usuários.

Mas vamos focar nesses aqui:

### 1. Modularidade:

A modularidade se refere à organização do código em unidades menores e independentes, chamadas de módulos. Cada módulo possui uma função específica e bem definida, o que torna o código mais organizado, fácil de entender e modificar.

<!--
No exemplo, as funções somar, subtrair, multiplicar e dividir são módulos que implementam operações matemáticas específicas. A função calcular utiliza esses módulos para realizar diferentes operações, evitando duplicação de código e aumentando a legibilidade.
-->

### 2. Reuso de código:

O reuso de código consiste em utilizar o mesmo código em diferentes partes do programa. Isso evita duplicação de código e aumenta a eficiência do desenvolvimento.

<!--
No exemplo, a função calcular reutiliza as funções somar, subtrair, multiplicar e dividir para realizar diferentes operações matemáticas. Isso evita a duplicação do código que realiza os cálculos matemáticos e torna o código mais eficiente.
-->

### 3. Legibilidade:

A legibilidade se refere à facilidade de ler e entender o código. Um código legível é escrito de forma clara, concisa e organizada, com nomes de variáveis e funções descritivos.

<!--
No exemplo, o código está bem formatado e utiliza nomes de variáveis e funções descritivos, como somar, subtrair, multiplicar e dividir. Isso facilita a leitura e compreensão do código.
-->

### 4. Teste de erros:

O teste de erros consiste em verificar se o código apresenta erros. Isso garante que o código funcione corretamente e atenda às expectativas dos usuários.

<!--
No exemplo, a função calcular verifica se a operação é válida antes de realizar o cálculo. Isso evita erros de operação inválida e garante que o código funcione corretamente.
-->

### 5. Documentação:

A documentação consiste em fornecer informações sobre o código, como sua função, funcionamento e como usá-lo. Uma boa documentação facilita a compreensão, o uso e a manutenção do código.

<!--
No exemplo, as funções possuem comentários que explicam seu funcionamento. Isso facilita a compreensão e o uso das funções.
-->

### 6. Ausência de bugs:

A ausência de bugs significa que o código não apresenta erros que afetem seu funcionamento. Um código livre de bugs é mais confiável e seguro para os usuários.

<!--
No exemplo, o código foi testado e não apresenta erros conhecidos. Isso garante que o código funcione corretamente e seja confiável para os usuários.
-->

### 7. Eficiência:

A eficiência se refere à capacidade do código de realizar suas tarefas de forma rápida e com o mínimo de recursos. Um código eficiente utiliza algoritmos eficientes e evita desperdícios de recursos.

<!--
No exemplo, o código utiliza algoritmos eficientes para realizar os cálculos matemáticos. Isso garante que o código funcione rapidamente e utilize o mínimo de recursos.
-->

### 8. Portabilidade:

A portabilidade se refere à capacidade do código de ser executado em diferentes plataformas e ambientes. Um código portátil pode ser usado em diferentes sistemas operacionais, navegadores e dispositivos.

<!--
No exemplo, o código pode ser executado em qualquer navegador que suporte JavaScript. Isso garante que o código seja portátil e possa ser usado em diferentes plataformas e dispositivos.
-->

### 9. Compatibilidade:

A compatibilidade se refere à capacidade do código de funcionar com diferentes versões de software e hardware. Um código compatível pode ser usado com diferentes versões do JavaScript e de outros softwares.

<!--
No exemplo, o código é compatível com diferentes versões do JavaScript. Isso garante que o código possa ser usado com diferentes versões do software e hardware.
-->

### 10. Desempenho:

O desempenho se refere à capacidade do código de responder rapidamente às solicitações dos usuários. Um código com bom desempenho oferece uma boa experiência de uso para os usuários.

<!--
No exemplo, o código responde rapidamente às solicitações do usuário. Isso garante que o código ofereça uma boa experiência de uso para os usuários.
-->

### Mãos à obra


<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/m01-semana06/blob/main/imgs/imaos_a_obra.jpg">
   <img alt="Página HTML Estática" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/m01-semana06/blob/main/imgs/imaos_a_obra.jpg)">
</picture>




Dado o código a seguir, o grupo deve encaixar os 10 itens acima nesse código, encontrando e justificando o uso dos 10 itens.

```
function somar(a, b) {
  return a + b;
}

function subtrair(a, b) {
  return a - b;
}

function multiplicar(a, b) {
  return a * b;
}

function dividir(a, b) {
  return a / b;
}

function calcular(operacao, a, b) {
  switch (operacao) {
    case '+':
      return somar(a, b);
    case '-':
      return subtrair(a, b);
    case '*':
      return multiplicar(a, b);
    case '/':
      return dividir(a, b);
    default:
      throw new Error('Operação inválida');
  }
}

const resultado = calcular('+', 2, 3);
console.log(resultado); // 5

const resultado2 = calcular('*', 4, 5);
console.log(resultado2); // 20
```


#### Fatores que influenciam a qualidade de software:

* Processo de desenvolvimento: A qualidade do software depende do processo de desenvolvimento utilizado. Um processo bem definido e documentado ajuda a garantir que o software seja desenvolvido de forma eficiente e eficaz.
* Qualidade dos requisitos: A qualidade dos requisitos é fundamental para a qualidade do software. Requisitos claros, completos e consistentes facilitam o desenvolvimento do software e evitam problemas futuros.
* Testes: Os testes são essenciais para garantir a qualidade do software. Testes rigorosos podem identificar e corrigir erros antes que o software seja lançado para os usuários.
* Ferramentas: As ferramentas utilizadas no desenvolvimento de software podem influenciar sua qualidade. Ferramentas adequadas podem ajudar a aumentar a produtividade e a qualidade do código.
* Pessoas: As pessoas envolvidas no desenvolvimento de software também influenciam sua qualidade. Desenvolvedores experientes e qualificados são essenciais para a criação de software de alta qualidade.

#### Benefícios de um software de qualidade:

* Satisfação dos usuários: Um software de qualidade atende às necessidades dos usuários e proporciona uma boa experiência de uso.
* Redução de custos: Um software de qualidade é menos propenso a apresentar erros e bugs, o que reduz os custos de manutenção e correção.
* Aumento da produtividade: Um software de qualidade facilita o trabalho dos usuários e aumenta sua produtividade.
* Melhoria da imagem da empresa: Uma empresa que oferece software de qualidade terá uma imagem mais positiva no mercado.

Em resumo... A qualidade de software é um fator essencial para o sucesso de qualquer software. Um software de qualidade deve atender às necessidades dos usuários, ser livre de erros, fácil de usar e manter, e seguro. Investir na qualidade de software pode trazer muitos benefícios para as empresas e para os usuários.


### Normas de Qualidade de Software

* ISO 9126 --> Características da qualidade de produtos de software.
* NBR 13596 --> Versão brasileira da ISO 9126.
* ISO 14598 --> Guias para a avaliação de produtos de software, baseados na utilização prática da norma ISO 9126.
* ISO 12119 --> Características de qualidade de pacotes de software (software de prateleira, vendido como um produto embalado).
* IEEE P1061 --> Standard for Software Quality Metrics Methodology. Norma que trata das metodologias para padronização da qualidade de software, incluindo algumas abordagens de medição.
* ISO 12207 --> Software Life Cycle Process. Norma para a qualidade do processo de desenvolvimento de software.
* NBR ISO 9001 --> Sistemas de qualidade – Modelo para garantia de qualidade em projeto, desenvolvimento, instalação e assistência técnica (processo).
* NBR ISO 9000-3 --> Gestão de qualidade e garantia de qualidade. Aplicação da norma ISO 9000 para o processo de desenvolvimento de software.
* NBR ISO 10011 --> Auditoria de Sistemas de Qualidade (processo).
* CMMI --> Capability Maturity Model Integration. Modelo da SEI (Instituto de Engenharia de Software do Departamento de Defesa dos USA) para avaliação da qualidade do processo de desenvolvimento de software. Não é uma norma ISO, mas é muito bem aceita no mercado.
* SPICE ISO 15504 --> Projeto da ISO/IEC para avaliação do processo de desenvolvimento de software. Ainda não é uma norma oficial ISO, mas o processo está em andamento.
* 
### Outros Aspector de Como Medir a Qualidade

[Acesse o link](https://www.devmedia.com.br/qualidade-de-software-engenharia-de-software-29/18209)


## 1 Refatoração

A refatoração de programa é o processo de reestruturar e modificar o código fonte de um programa de software, sem alterar seu comportamento externo. 

### Objetivo da Refatoração

Melhorar a qualidade interna do código, tornando-o mais legível, compreensível, eficiente e fácil de dar manutenção, sem introduzir novas funcionalidades ou bugs.

### O que fazer numa Refagoração?

Durante o processo de refatoração, os desenvolvedores podem reorganizar a estrutura do código, renomear variáveis e funções, extrair partes do código para funções separadas, eliminar duplicações, simplificar a lógica do programa e realizar outras mudanças que visam tornar o código mais limpo e claro. 

Isso ajuda a reduzir a complexidade do código, facilitando sua compreensão e modificação no futuro.

### Quando usar Refatoração?

* Quando adicionar uma funcionalidade
* Ao corrigir um bug
* Ao revisar um código

### Métodos de Refatoração

#### Método Pull-up

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

#### Método de Refatoração Pull-up field

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

#### Método de Refatoração Push-down

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

#### Método de Refatoração Push-down field

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

#### Método de Refatoração Extract Subclass

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
 
#### Método Extract Super Class

O Extract Superclass visa **criar uma nova superclasse a partir de um conjunto de características comuns em duas ou mais classes filhas**. 

Exemplo. Um código com duas classes filhas ```Cachorro``` e ```Gato``` que herdam da classe ```Animal```:

```
class Animal {
  constructor(nome) {
    this.nome = nome;
  }
}

class Cachorro extends Animal {
  constructor(nome, raça) {
    super(nome);
    this.raça = raça;
  }

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

class Gato extends Animal {
  constructor(nome, raça) {
    super(nome);
    this.raça = raça;
  }

  miar() {
    console.log(`O gato ${this.nome} está miando!`);
  }
}

const cachorro = new Cachorro('Rex', 'Labrador');
cachorro.latir(); // O cachorro Rex está latindo!

const gato = new Gato('Mia', 'Siamês');
gato.miar(); // O gato Mia está miando!
```

Observe que as classes ```Cachorro``` e ```Gato``` possuem atributos e métodos em comum, como ```nome``` e ```raça```. Podemos usar o Extract Superclass para criar uma nova superclasse ```Mamifero``` que herda as características comuns:

```
class Mamifero {
  constructor(nome, raça) {
    this.nome = nome;
    this.raça = raça;
  }
}

class Cachorro extends Mamifero {
  constructor(nome, raça) {
    super(nome, raça);
  }

  latir() {
    console.log(`O cachorro ${this.nome} está latindo!`);
  }
}

class Gato extends Mamifero {
  constructor(nome, raça) {
    super(nome, raça);
  }

  miar() {
    console.log(`O gato ${this.nome} está miando!`);
  }
}

const cachorro = new Cachorro('Rex', 'Labrador');
cachorro.latir(); // O cachorro Rex está latindo!

const gato = new Gato('Mia', 'Siamês');
gato.miar(); // O gato Mia está miando!
```

Neste exemplo, a superclasse ```Mamifero``` foi criada para agrupar as características comuns das classes ```Cachorro``` e ```Gato```. As classes filhas herdam essas características e implementam seus próprios métodos específicos.

#### Observações

Benefícios do Extract Superclass:

* Elimina a duplicação de código: remove a necessidade de repetir código em diferentes classes filhas.
* Aumenta a legibilidade: Torna o código mais fácil de entender, pois as características comuns estão agrupadas em uma única classe.
* Facilita a manutenção: Permite modificar as características comuns em um único lugar, impactando todas as classes filhas.

Limitações do Extract Superclass:

* Nem sempre é possível: A técnica só pode ser aplicada se existe um conjunto de características comuns em duas ou mais classes filhas.
* Pode afetar a performance: Se a superclasse for muito grande, pode aumentar o tamanho das classes filhas e afetar a performance.

Quando usar o Extract Superclass:

* Quando duas ou mais classes filhas possuem características comuns.
* Quando você deseja eliminar a duplicação de código.
* Quando você deseja aumentar a legibilidade e facilitar a manutenção do código.

#### Método Replace Temp With Query

É uma técnica de refatoração que visa eliminar variáveis temporárias que armazenam o resultado de expressões complexas. Essa técnica substitui a variável por uma chamada direta à função que calcula a expressão, tornando o código mais legível e fácil de manter.

Exemplo: suponha que temos uma função que calcula o preço total de uma compra com base na quantidade de itens e no preço unitário, e queremos aplicar um desconto de 10% se o preço total for maior que $100.

**Antes da refatoração:**

```
function calculateTotalPrice(quantity, unitPrice) {
    let totalPrice = quantity * unitPrice;
    
    // Aplica um desconto de 10% se o preço total for maior que $100
    if (totalPrice > 100) {
        totalPrice -= (totalPrice * 0.1);
    }
    
    return totalPrice;
}

console.log(calculateTotalPrice(5, 25)); // Saída: 125
```

**Após a refatoração:**

```
function calculateTotalPrice(quantity, unitPrice) {
    // Remove a variável temporária totalPrice e chama uma função para calcular o preço com desconto
    if (calculateDiscountedPrice(quantity, unitPrice) > 100) {
        return calculateDiscountedPrice(quantity, unitPrice);
    } else {
        return quantity * unitPrice;
    }
}

function calculateDiscountedPrice(quantity, unitPrice) {
    let totalPrice = quantity * unitPrice;
    
    // Calcula o preço com desconto de 10%
    if (totalPrice > 100) {
        totalPrice -= (totalPrice * 0.1);
    }
    
    return totalPrice;
}

console.log(calculateTotalPrice(5, 25)); // Saída: 125
```

Neste exemplo, inicialmente tínhamos uma variável temporária ```totalPrice``` que armazenava o preço total calculado. Após a refatoração, essa variável temporária foi removida e substituída por uma chamada à função ```calculateDiscountedPrice```, que calcula o preço total com o desconto aplicado. Isso elimina a necessidade da variável temporária e torna o código mais claro e conciso.

#### Observações

Benefícios do Replace Temp With Query:

* Melhora a legibilidade: elimina variáveis temporárias, tornando o código mais fácil de entender.
* Facilita a manutenção: reduz a quantidade de código e nesse caso, torna mais fácil modificar o cálculo do desconto.
* Evita erros: diminui a chance de erros.

Limitações do Replace Temp With Query:

* Nem sempre é possível: a técnica só pode ser aplicada quando a expressão que calcula o valor da variável temporária é simples e pode ser facilmente transformada em uma função.
* Pode aumentar a complexidade do código: se a expressão for muito complexa, transformá-la em uma função pode aumentar a complexidade do código.

Quando usar o Replace Temp With Query:

* Quando você tem variáveis temporárias que armazenam o resultado de expressões complexas.
* Quando você deseja melhorar a legibilidade e facilitar a manutenção do código.
* Quando você deseja evitar erros relacionados ao cálculo do valor da variável temporária.

## Debugando códigos

### Desafio! Dados os códigos acima, você detectou algum tipo de debug de código?


remover comentário no markdown.


<!--
<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/m01-semana06/blob/main/imgs/Capture.PNG">
   <img alt="Página HTML Estática" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/m01-semana06/blob/main/imgs/Capture.PNG)">
</picture>

--> 

## DESAFIO!

O grupo deve escolher um método de refatoração, desenvolver um código e apresentar o antes e o depois da refatoração.

O melhor grupo leva um prêmio!


<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/m01-semana06/blob/main/imgs/rodadopeao.jpg">
   <img alt="Página HTML Estática" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/m01-semana06/blob/main/imgs/rodadopeao.jpg)">
</picture>


