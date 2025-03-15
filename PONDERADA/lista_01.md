1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.  

console.log(x);
var x = 5;
console.log(y);
let y = 10;

// resposta
a) A saída será undefined seguido de erro. Isso acontece devido ao comportamento de hoisting no JavaScript. Quando usamos var para declarar uma variável, a declaração é elevada ao topo do escopo, mas a atribuição do valor só ocorre na linha onde a inicialização acontece. No caso do console.log(x), a variável x já foi declarada, mas ainda não foi atribuída com o valor 5, logo o valor retornado é undefined. Por outro lado, quando utilizamos let para declarar uma variável, ela também sofre hoisting, mas com uma diferença crucial: a variável entra em uma "temporal dead zone" até o momento da sua inicialização. Isso significa que qualquer tentativa de acessar a variável y antes de sua inicialização resulta em um ReferenceError. Assim, o segundo console.log(y) gera o erro. 

2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.

function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
      
      // resposta
a) Substituir if (a || b === 0) por if (a === 0 || b === 0) pois a expressão original não verifica corretamente se a ou b são iguais a 0 devido à precedência dos operadores em JavaScript. O operador === tem maior precedência que o operador ||, o que faz com que a comparação b === 0 seja feita independentemente de a, levando a resultados indesejados. Ao substituir por if (a === 0 || b === 0), a condição passa a verificar corretamente se qualquer um dos valores é 0, o que, no contexto da função de soma, é um comportamento esperado para retornar um erro quando um número inválido (0) é encontrado. Essa alteração garante que o código funcione conforme a lógica desejada, tratando corretamente os valores inválidos para a soma. 

3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.

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

// resposta
b) O código imprime 200, pois a ausência do break após o case "eletrônico" faz com que o fluxo de execução continue para o próximo case, resultando na atribuição de 200 ao preço.

 4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.

 let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);

// resposta
d) 24

//justificativa:
 Ao analisar o código apresentado, podemos entender a sequência de operações realizadas sobre o array numeros. Primeiramente, o método map() é utilizado para multiplicar cada elemento do array por 2, resultando no array [2, 4, 6, 8, 10]. Em seguida, o método filter() é aplicado para filtrar apenas os números maiores que 5, gerando o array [6, 8, 10]. Por fim, o método reduce() é usado para somar os elementos filtrados, começando com o valor inicial 0 e acumulando os valores de forma sequencial: 0 + 6 = 6, 6 + 8 = 14, e 14 + 10 = 24. 


5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.

let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);


// resposta
c) ["banana", "abacaxi", "manga", "laranja"] //alternativa correta

// justificativa
O método splice substitui dois elementos a partir do índice 1 e insere "abacaxi" e "manga" na mesma posição, resultando no array mencionado. 

6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.

II. Em JavaScript, a herança é implementada através da palavra-chave extends.

// resposta
a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

// justificativa
Ambas as afirmações estão corretas, e a segunda, que menciona o uso da palavra-chave extends, explica como a herança é implementada, o que justifica o conceito descrito na primeira afirmação. 


7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.

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
I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.
II) O método apresentar() da classe Funcionario sobrepõe o método apresentar() da classe Pessoa, mas chama o método da classe pai usando super.
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

// resposta
a) I e II são verdadeiras.

// justificativa
 As afirmações I e II estão corretas, enquanto a afirmação III é incorreta, já que JavaScript suporta herança de classes a partir do ES6. 


8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.

Asserção: O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.
Razão: Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

// resposta
b) A asserção é verdadeira e a razão é falsa. 

//justificativa
 A asserção está correta sobre o polimorfismo, mas a razão está errada, pois em JavaScript não usamos sobrecarga de métodos para implementar polimorfismo. Em vez disso, usamos sobrescrita de métodos. 

 9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.


// codigo corrigido (resposta)
function somaArray(numeros) {
    // Inicializa a variável soma como 0. A gente vai usar ela pra acumular o resultado final
    let soma = 0;

    // Aqui, a gente faz um loop pra percorrer todos os números do array
    // A condição 'i < numeros.length' é o jeito certo de pegar o tamanho do array
    for (let i = 0; i < numeros.length; i++) {
        // Em vez de substituir o valor de soma, a gente vai somando o dobro de cada número no array
        // Ou seja, 2*numeros[i] vai ser adicionado à soma a cada volta do loop
        soma += 2 * numeros[i];
    }

    // Por fim, a função retorna a soma total depois do loop
    return soma;
}

// Aqui estamos testando o código. O esperado é 20, porque a soma do dobro dos números 1, 2, 3, e 4 é 20
console.log(somaArray([1, 2, 3, 4]));  // Esperado: 20

10) Crie um exemplo prático no qual você tenha duas classes:
Uma classe Produto com atributos nome e preco, e um método calcularDesconto() que aplica um desconto fixo de 10% no preço do produto.
Uma classe Livro que herda de Produto e modifica o método calcularDesconto(), aplicando um desconto de 20% no preço dos livros.
Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe Livro.

//codigo: 
// Classe Produto
class Produto {
  // Construtor da classe Produto, que recebe o nome e o preço
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }

  // Método para calcular o desconto de 10% no preço do produto
  calcularDesconto() {
    const desconto = 0.10;  // 10% de desconto
    const precoComDesconto = this.preco - (this.preco * desconto);
    return precoComDesconto;
  }
}

// Classe Livro que herda de Produto
class Livro extends Produto {
  // Construtor da classe Livro, que recebe nome, preço e autor
  constructor(nome, preco, autor) {
    // Chama o construtor da classe Produto para inicializar nome e preço
    super(nome, preco);
    this.autor = autor;  // Atributo específico de Livro
  }

  // Sobrescreve o método calcularDesconto para aplicar 20% de desconto para livros
  calcularDesconto() {
    const desconto = 0.20;  // 20% de desconto para livros
    const precoComDesconto = this.preco - (this.preco * desconto);
    return precoComDesconto;
  }
}

// Criando um produto normal
const produto1 = new Produto("Produto A", 100);
console.log(`Preço com desconto do Produto A: ${produto1.calcularDesconto()}`);  // Esperado: 90

// Criando um livro
const livro1 = new Livro("Livro A", 50, "Autor X");
console.log(`Preço com desconto do Livro A: ${livro1.calcularDesconto()}`);  // Esperado: 40

//Explicando o codigo

//Classe Produto:
 A classe Produto tem os atributos nome e preco. O método calcularDesconto aplica um desconto de 10% no preço do produto e retorna o novo preço.

//Classe Livro:
 A classe Livro herda tudo que a classe Produto tem, ou seja, ela herda os atributos nome e preco, e o método calcularDesconto. Mas, como a gente quer que livros tenham um desconto maior, a gente modifica o método calcularDesconto para dar 20% de desconto, ao invés de 10%. A palavra-chave super(nome, preco) serve para chamar o construtor da classe Produto, que vai inicializar os valores de nome e preco na classe Livro.

//Como funciona a herança:
Herança faz com que a classe Livro "herde" as coisas da classe Produto. Ou seja, o Livro pode usar tudo o que já foi feito na classe Produto, como os atributos nome e preco, e até mesmo o método calcularDesconto, mas também pode modificar o que quiser.
 Então, a classe Livro pode ter um desconto diferente (20%) do produto normal, mas ainda usa o mesmo conceito que foi criado na classe Produto.



