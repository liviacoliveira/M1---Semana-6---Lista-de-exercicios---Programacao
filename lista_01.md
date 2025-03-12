# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
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
--> a) A saída será undefined seguido de erro 

A alternativa correta é a letra A, uma vez que por ser declarada com var, a primeira variável (x) é hoisted, ou seja, a declaração dela é "movida para cima" do escopo antes do código ser executado, mas é inicializada como undefined. Já no segundo caso, como a variável (y) é declarada com let, essa é hoisted, porém não inicializada, o que gera um erro no resultado esperado.

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


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

---> a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

A resposta certa é a alternativa A, uma vez que o operador (===), que representa igualdade restrita, tem uma precedência maior no javascript do que o operador (||), OU lógico. Isso significa que, com base na linha de código anteriormente escrita, primeiramente ele iria verificar se b === 0, o que nesse caso é verdadeiro, e representa que a condição passará a ser analisada assim: if (a || true), que não é a intenção do código, já que ele passará a verificar se a é um valor "verdadeiro", e não se ele é idêntico a zero. E já na nova formatação, a verificação seria feita para ambos (a e b): caso a === 0 OU b === 0, o que nessa situação é verdadeiro, e retornaria o erro, mas dessa vez, com o código em perfeita execução.

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
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

---> b) O código imprime 200.

A resposta correta é a alternativa B, uma vez que, já que a condicional utilizada é a switch, que divide o código em cases, o case "eletrônico" desejado pelo console.log lá no fim será executado, atribuindo inicialmente o valor de 1000 ao preço. Porém, ele continuará sendo executado por não haver um break, resultando em uma nova atribuição no case "vestuário", em que o preço passa a valer 200. Como nesse caso há um break, indicando a interrupção desse código, o valor impresso será 200.

c) O código imprime 50.

d) O código gera um erro.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

---> d) 24

A resposta correta é a alternativa D, uma vez que o código acima segue a estrutura: 
1. Em numeros.map ele multiplica todos os valores do array por 2, resultando em 2,4,6,8 e 10.
2. Logo em seguida, em .filter, ele filtra apenas os números maiores que 5, nesse caso 6,8 e 10.
3. Depois disso, em .reduce, ele soma os valores do array, obtendo como resultado final 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

---> c) ["banana", "abacaxi", "manga", "laranja"]

A resposta correta é a alternativa C, uma vez que o método .splice() é utilizado para remover ou modificar elementos de um array. Nesse caso, ele indica, a partir dos números 1 e 2, que serão removidos 2 elementos a partir do item 1 da lista, que corresponde a "maçã", e que esses serão substituidos por: "abacaxi" e "manga". Logo, a nova lista será a da letra C.

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


---> a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

A resposta correta é a alternativa A, uma vez que herança está dentro da Programação Orientada a Objetos, tendo como principal objetivo justamente herdar códigos sem que seja necessário repeti-los. Desse modo, as duas afirmações acima são verdadeiras, sendo a primeira justificada pela segunda, que explica de que forma uma classe é herdada dentro do javascript.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
______
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

---> a) I e II são verdadeiras.

A resposta correta é a alternativa A, uma vez que a herança está descrita perfeitamente na afirmativa 1, da mesma forma como a afirmativa 2 explica corretamente como o método da classe Funcionario sobrepõe o anterior, mas ainda sim chama o método da classe pai, garantindo a apresentação inicial antes da adição do salário. Apenas essas duas estão corretas pois o código funciona perfeitamente, considerando que o javascript permite a herança de classes.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

---> b) A asserção é verdadeira e a razão é falsa.

A alternativa correta é a letra B, uma vez que o polimorfismo em javascript realmente permite que objetos de diferentes tipos respondam a métodos de diversas formas, porém o javascript não suporta a sobrecarga de métodos em uma mesma classe, logo o polimorfismo acontece de maneira diferente, como redefinindo métodos de uma classe pai em uma classe filha.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.
