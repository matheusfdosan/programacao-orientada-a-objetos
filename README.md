# Programação Orientada a Objetos (POO)

## O que é Programação Orientada a Objetos POO?

Vem do inglês, Oriented Object Programming ou OOP, que é um paradigma de desenvolvedor, ou seja, é uma maneira de pensar e de resolver um problema. No caso, vamos pensar nas coisas como um objeto, logo, o POO não está ligado somente a liguagem programação, mas a um entendimento amplo e atemporal para a criação de softwares.

Usar o POO pode melhorar o entendimento do código, pesando nele como objetos. Separando a complexibilidade de código, abstrair e expor de maneira mais simples.

Em termo de linguagens o JS, TS, Java, Python... usam esse paradigma.

## Utilização no mercado

A maioria dos sistemas atuais usam a POO. É usado por Analistas de Sistemas e não somente por programadores, mas isso não significa que os analistas vão codar, eles irão fazer o levantamento de requisitos do sistema.

## Onde e quando utilizar POO?

Dependendo da linguagem de programação, ela pode ser orientada a objetos, e não há como usar outro paradigma. Mas também, dependendo da linguagem, é possível usar o paradigma funcional, ou seja, não tem como usar POO.

> Existem liguagens que só utilizam o paradigma POO e existem linguagens que só utilizam o paradigma funcional. E existem linguagens multiparadigmas.

Linguagens que são multiparadigmas, são linguagens que tem como escolher programar em POO ou funcional, por exemplo, o JavaScript.

## Objetos

Os objetos podem ser qualquer coisa, por exemplo, uma celular. Todo objeto possui propriedades (atributos), funcionalidades (métodos ou comportamentos) e um estado:

- Um celular tem suas propriedades, tem uma cor, um peso, um tamanho e etc.
- E tem suas funcionalidades, ele liga, manda mensagens, tira fotos entre outros.
- Ele tem um estado, pode estar na vertical, na horizontal, de cabeça para baixo ou em pé.

## Objetos abstratos vs objetos do mundo real

É fácil trazer uma representação de algo do mundo real para objetos, como uma pessoa, um aluno, um produto ou até mesmo um carrinho de compras. Porém, alguns objetos na programação não são fáceis de identificar, pois são abstratos, como uma autenticação ou autorização.

> Nem todo objeto do mundo real fará parte do seu sistema.

## Classes

As classes na orientação a objetos funcionam como um molde para os objetos. Os objetos são criados a partir de uma classe e muitos deles podem ser feitos da mesma classe.

Exemplo: Uma máquina de biscoitos, podemos colocar os ingredientes nela, e ela faz um biscoito. A máquina produz tudo, um molde, mistura, esquenta. Apenas colocamos os ingredientes e ela devolve um biscoito pronto, se quisermos, poderá produzir 1000 biscoitos, sendo uma máquina.

Essa é a ideia de classes, a máquina de biscoitos é a classe, e o biscoito é o objeto ou instância, significa que estamos criando um objeto através da classe.

### Classes na prática

O conceito de classes no JavaScript é totalmente diferente do conceito de classes numa programação totalmente orientada a objetos. Pois, o JavaScript é uma programação multiparadigmas, então ela envolve POO e programação funcional.

Contudo, as classes no JavaScript são chamadas de **Syntactical Sugar**, ou seja, é uma maneira bela, mais bonitinha de se escrever em **prototypes** (protótipos). Em JavaScript, os objetos são protótipos, significa que é uma cadeia, como assim cadeia? Exemplo:

Imagina um objeto que acabamos de criar, um objeto com o nome `pessoa1` que é uma instância de uma classe com o nome `Pessoa`, essa classe irá dar ao objeto um identificador, um nome e uma funcionalidade de `dizerNome()`.

```js
class Pessoa {
  // propriedades
  constructor(nome) {
    this.id = ~~(Math.random() * 100000) // ramdom number
    this.nome = nome
  }

  // funcionalidades
  dizerNome() {
    console.log(this.nome)
  }
}

// instanciando - tirando o biscoito da máquina
const pessoa1 = new Pessoa("Matheus")

// utilizando a funcionalidade
pessoa1.dizerNome() // Matheus
```

Porém, percebemos no JavaScript, que mesmo com as funcionalidades criadas na classe, o JavaScript trará mais funcionalidades, o que chamamos de herança, ou seja, há uma matriz de classes no JavaScript que herdam funcionalidades:

```js
console.log(pessoa1.nome.length)
console.log(pessoa1.id.toString())
```

`pessoa1.nome`, por ser uma string, vai herdar funcionalidades de uma string como `length`, `slice`, `indexação[1]`, `trim` e etc. E `pessoa.id` também herdará funcionalidades de números.

Em resumo, as classes no JavaScript é uma maneira bonita de representar protótipos, todo objeto criado no JavaScript é um protótipo, e trará uma herança de outras funcionalidades e propriedades de outros objetos acima dele.

## Encapsulamento

Encapsulamento é colocar numa cápsula, um agrupamento de funções e variáveis todas colocadas dentro de uma classe, ou seja, estão encapsuladas, com seus detalhes de implementação escondidos. Então, nos usamos as funcionalidades e variáveis, sem se preocupar em saber detalhes sobre a implementação.

O conceito de encapsulamento, é como dirigir um carro sem precisar entender como ele funciona, é possível dirigir um carro e deixar as partes complexas para outro momento.

## Encapsulamento na prática

```js
// Estrutural

let altura = 50
let largura = 60

function calcularArea() {
  return altura * largura
}

let area = calcularArea()
```

Acima, há um código estrutural, com uma variável `altura` e `largura` que recebem um número cada, em seguida, tem uma função que retorna a altura vezes a largura. Logo após, uma variável `area`, recebe o resultado da função.

O problema é que, em algum momento, vamos trocar a altura ou a largura, entretanto, isso pode impactar de maneira negativa para que usará o código.

Uma maneira de resolver esse problema é utilizar a **programação orientação a objetos** e **encapsular** os dados e a lógica relacionada em uma classe:

```js
class Poligono {
  constructor(altura, largura) {
    this.altura = altura
    this.largura = largura
  }

  get area() {
    return this.#calcularArea()
  }

  #calcularArea() {
    return this.altura * this.largura
  }
}

const poligono = new Poligono(50, 60)
// propriedade para calcular a área
console.log(poligono.area) // 3000
```

Definimos uma classe `Poligono`, que traz um objeto que tem as propriedades de altura e largura.

Depois, temos o método `area`, que é definido como um **getter**, que permite acessá-la como se fosse uma propriedade, ou seja, não precisa de parênteses para seu uso. Esse método retorna o resultado do método privado `#calcularArea()`, o prefixo `#`, o torna um método privado.

O método privado é um método que não vai ser utilizado pelo programador, seu acesso é apenas dentro da classe. Fora da classe, com o objeto instânciado, esse método não estará acessível

```js
console.log(poligono.#calcularArea())
//Isso não funcionará
```

## Programação Estruturada vs POO

Vai processar a entrada dos dados, e manipular até a saída dos dados, uma maneira linear de fazer as coisas. O uso de sequências, um código vem abaixo do outro, podendo ter sobrescrições de variáveis, além de, usar estruturas de repetições e condições. Sendo assim, uma bagunça no código!

A solução para isso, é a programação orientada a objetos, pois surge um cuidado ao uso estruturado, trazendo o conceito como objetos, classes, encapsulamento e heranças.

Exemplo estruturado:

```js
var valorHora = 50
var tempoEstimado = 20
var desconto = valorHora * tempoEstimado * (10 / 100)
var custoEstimado = valorHora * tempoEstimado - desconto
console.log(custoEstimado) // 900
```

Exemplo orientado a objetos:

```js
class Job {
  constructor(valorHora, tempoEstimado, desconto) {
    this.valorHora = valorHora
    this.tempoEstimado = tempoEstimado
    this.desconto = desconto
  }

  calcularEstimativa() {
    const desconto = this.valorHora * this.tempoEstimado * (this.desconto / 100)
    return this.valorHora * this.tempoEstimado - desconto
  }
}

const valorHora = 50
const tempoEstimado = 20
const desconto = 10

const job = new Job(valorHora, tempoEstimado, desconto)
console.log(job.calcularEstimativa())
```

## Herança

A herança, nada mais é do que, pais e filhos. Os objetos podem herdar, ou estender características bases de outros objetos. Então, é como se fosse uma cópia de métodos e atributos de outra classe.

```js
/* Classe Pai */
class Veiculo {
  rodas = 4

  mover(direcao) {...}
  virar(direcao) {...}
}
```

No código acima, há uma classe pai, uma classe chamada `Veiculo`, que tem quatro rodas e os métodos de mover e virar.

```js
/* Classe Filho */
class Moto extends Veiculo {
  constructor() {
    super()
    this.rodas = 2
  }
}
```

Já na classe `Moto`, afinal, moto também é um veículo, portanto, é uma classe filha. Logo, `Moto` estende de `Veiculo`, ele herda seus métodos e atributos. Contudo, no _constructor()_, guarda o `super()`, significa que, está puxando os atributos e métodos da classe pai. E depois, colocamos que a moto terá 2 rodas, os métodos mover e virar já existem dentro da classe.

> Uma classe pode estender de outra classe de forma infinita

## Polimorfismo

Quando um objeto estende o outro (`herança`) talvez haja necessidade de reescrever algumas características (`atributos e métodos`) nesse novo objeto, ou seja, quando um objeto herda características de outro objeto, podemos alterar algumas ou todas essas características.

**Exemplo**: Há uma classe `Ave`, que herda características para outra classe chamada `Pato`, logo, um pato não voa igual a uma ave voa, contudo, reescreveremos o método `voar()` do pato, para não ser possível voar por longas horas.

> Polimorfismo significa muitas formas

```js
class Atleta {
  peso
  altura

  constructor(peso) {
    this.peso = peso
  }

  defirCategoria() {
    if (this.peso <= 50) {
      this.categoria = "infantil"
    } else if (this.peso <= 65) {
      this.categoria = "juvenil"
    } else {
      this.categoria = "adulto"
    }

    return this.categoria
  }
}
```

Aqui há uma classe `Atleta`, com um método de `definirCategoria`, que retorna uma categoria conforme o peso passado.

```js
class Lutador extends Atleta {
  constructor(peso) {
    super(peso)
  }

  defirCategoria() {
    if (this.peso <= 54) {
      this.categoria = "peso galo"
    } else if (this.peso <= 57) {
      this.categoria = "peso pena"
    } else if (this.peso < 75) {
      this.categoria = "peso médio"
    } else {
      this.categoria = "peso pesado"
    }

    return this.categoria
  }
}
```

A classe `Lutador` estende da classe `Atleta`, significa que, os métodos e atributos de `Atleta`, serão passadas ao `Lutador`. Mas as definições de categorias para lutadores não são as mesmas dos atletas, e é aí, que entra o **polimorfismo**, alteramos o código do método `definirCategoria`. Ao criar o método no `Lutador`, tendo o mesmo nome do método `definirCategoria` de `Atleta`, já abre portas para o polimorfismo, daí podendo alterar as propriedades e funcionalidades.

```js
const atleta = new Atleta(80)
console.log(atleta.defirCategoria()) // adulto

const mikeTayson = new Lutador(100)
console.log(mikeTayson.defirCategoria()) // peso pesado
```

Nesse trecho de código, vemos que o código funciona. O método `definirCategoria()`, tem funcionalidades diferentes conforme o objeto.

## Abstração

Abstração significa a ideia de um template (máscara/esqueleto) ou uma identidade de uma classe que será construída no futuro, quero dizer que, é possível construir uma classe sem fazer a implementação dela, sem construir inteiramente.

Contudo, a abstração, basicamente, é a construção de funcionalidades e propriedades que consideramos importantes, e a rejeição de informações não importantes. Simplificando a complexidade do sistema e focando apenas nos aspectos mais relevantes.

Vamos começar usando **classes abstratas** ou **superclasses**, que é uma classe que não pode ser instanciada diretamente, mas serve como base para outras classes que a estendem.

```js
class Parafuso {
  constructor() {
    // SuperClasse
    if (this.constructor === Parafuso)
      throw new Error("Classe abstrata não pode ser instânciada")
    // Garante que a claasse não seja instanciada diretamente
  }

  get tipo() {
    throw new Error('Método "get tipo()" precisa ser implementado')
    // Garante que o método "tipo()" seja implementado na classe
  }
}
```

No código acima, escrevemos uma classe abstrata, que vai ser um "molde" para as outras classes, portanto, ela mesma não pode ser instanciada diretamente, caso for instanciada, ativará um erro. E também garante que seu método seja escrito em suas classes.

```js
class Fenda extends Parafuso {
  constructor() {
    super()
  }

  get tipo() {
    return "Fenda"
  }
}

class Philips extends Parafuso {
  constructor() {
    super()
  }

  get tipo() {
    return "Philips"
  }
}
```

Aqui, vemos duas classes (subclasses) que se estendem de `Parafuso`, e com o método `get tipo()` definido.

```js
class Allen extends Parafuso {}
```

Porém, temos aqui uma classe que se estende de `Parafuso`, mas sem o método `get tipo()`, o que vai dar erro quando tal método for chamado.

```js
let fenda = new Fenda()
let philips = new Philips()
let allen = new Allen()

console.log(fenda.tipo, philips.tipo) // Fenda Philips
console.log(allen.tipo) // Erro: Método "get tipo()" precisa ser implementado
```
