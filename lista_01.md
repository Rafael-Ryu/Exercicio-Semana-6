# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como `` esta aqui com `  `` ou

````javascript
//esta aqui com ```
let a = "olá";
let b = 10;
print(a);
````

- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove.

# Questões objetivas

**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**

```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```

a) A saída será undefined seguido de erro

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: Alternativa A.

Justificativa: A variável x, é declarada com "var", que faz com que ela seja inicializada como "undefined", já a variável y, é declarada com "let", que não inicializa a variável, fazendo com que ela retorne um erro, ao tentar ser acessada antes de sua declaração.

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
  if (a || b === 0) {
    return "Erro: número inválido";
  }
  return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Resposta: Alternativa A.

Justificativa: Na condição original, a condição é interpretada como: `if ((a) || (b === 0))`, então mesmo que "b" seja igual a 0, caso "a" seja "truthy" (qualquer número diferente de 0), a condição retorna true.

---

**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**

```javascript
function calcularPreco(tipo) {
  let preco;

  switch (tipo) {
    case "eletrônico":
      preco = 1000;
    case "vestuário":
      preco = 200;
      break;
    case "alimento":
      preco = 50;
      break;
    default:
      preco = 0;
  }

  return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

Resposta: Alternativa B.

Justificativa: Como o case "eletrônico" não possui um "break", o código continua até o próximo case que possui um break, que no caso é o do "vestuário", que define o preço como 200.

---

**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**

```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros
  .map((x) => x * 2)
  .filter((x) => x > 5)
  .reduce((a, b) => a + b, 0);

console.log(resultado);
```

a) 0

b) 6

c) 18

d) 24

Resposta: Alternativa D.

Justificativa: `map((x) => x * 2)` múltiplica os números da array por 2, `filter((x) => x > 5)`, filtra apenas os valores maiores que 5, `reduce((a, b) => a + b, 0)` soma todos os elementos.

---

**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Resposta: Alternativa C.

Justificativa: ```lista.splice(1, 2, "abacaxi", "manga")``` começa no índice 1 (maçã), remove 2 elementos (maça e uva) e coloca "abacaxi" e "manga" no lugar deles.

---

**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Resposta: Alternativa B.

Justificativa: A primeira afirmação está correta, pois a herança permite que uma classe herde os comportamentos de outra, evitando a repetição de código. A segunda afirmação está correta, pois a palavra "extends" é utilizada para implementar a herança. Dessa forma, mesmo que as duas afirmações estejam corretas, a segunda afirmação não justifica a primeira, pois a primeira fala sobre o propósito da herança e a segunda fala sobre como "extends" é utilizado para implementar essa henrança.

---

**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```

I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Resposta: Alternativa A.

Justificativa: A afirmação 1 está correta, pois a classe "Funcionario" herda de "Pessoa", sendo possível ter acesso aos atributos "nome" e "idade". A afirmação 2 também está correta, o método ```apresentar()``` da classe "Funcionario" sobrescreve o método da classe pai, mas ele usa ```super.apresentar()``` para chamar a implementação original. A afirmação 3 é falsa, pois JavaScript suporta herança de classes.

---

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Resposta: Alternativa B.

Justificativa: "Asserção" está correta, o polimorfismo permite que objetos de diferentes tipos respondam o mmesmo método de maneiras diferentes. Já a "Razão" está incorreta, pois JavaScript não suporta nativamente sobrecarga de métodos, o polimorfismo normalmente é implementado através do mecanismo de prototipagem.

---

# Questões dissertativas

9. O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {
  for (i = 0; i < numeros.size; i++) {
    soma = 2 * numeros[i];
  }
  return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Código corrigido:

```javascript
function somaArray(numeros) {
  // Inicializa a variável soma com zero para acumular o resultado
  let soma = 0; 
  
  // Correções:
  // Usar 'let' para declarar i no escopo local
  // Arrays em JavaScript usam .length, não .size para obter seu tamanho
  for (let i = 0; i < numeros.length; i++) {
    // Acumular os valores com += em vez de substituir
    // A função deve somar o dobro dos valores, não apenas armazenar o último
    soma += 2 * numeros[i];
  }
  
  return soma;
}

console.log(somaArray([1, 2, 3, 4])); // Resultado: 20
```

---

10. Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Exemplo prático:

```javascript
class Produto {
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }
  
  // Método que calcula o desconto de 10%
  calcularDesconto() {
    return this.preco * 0.9; // aplica 10% de desconto
  }
}

// Herda de Produto
class Livro extends Produto {
  constructor(nome, preco, autor) {
    super(nome, preco); // chama o construtor da classe Produto
    this.autor = autor;
  }
  
  // Sobrescrevendo o método para aplicar um desconto de 20%
  calcularDesconto() {
    return this.preco * 0.8; // aplica 20% de desconto
  }
}

// Exemplo de utilização:
const produto = new Produto("Açaí", 20);
console.log(`Preço com desconto do produto: R$ ${produto.calcularDesconto()}`); // R$ 18

const livro = new Livro("Orientação a Objetos em Java", 100, "Autor X");
console.log(`Preço com desconto do livro: R$ ${livro.calcularDesconto()}`); // R$ 80
```

A classe "Livro" tem todas as características da classe "Produto", mas com características adicionais. ```class Livro extends Produto``` herda os atributos, os métodos e o protótipo de "Produto", o ```super(nome, preco)``` chama o construtor da classe pai para inicializar os atributos herdados e a classe "Livro" sobrescreve o método ```calcularDesconto()``` para aplicar o desconto de 20%.