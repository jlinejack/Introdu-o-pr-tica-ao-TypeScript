# Introdução prática ao TypeScript


### O que é Typescript? Superset do JavaScript.

- “TypeScript é JavaScript mais alguns recursos adicionais, ou seja, um conjunto de ferramentas e formas mais eficientes de escrever o código JS;
- Adiciona features à linguagem original; e
- Compila para JS.

#### Inicialmente é necessário instalar o typescript globalmente em nossa máquina, utilizando o gerenciador de pacotes da sua preferência.

// Instalando typescript
ts|⇒ yarn add typescript
// Verificando versão
ts|⇒ tsc -v
Version 4.7.4
// Criando o arquivo em que vamos trabalhar
ts|⇒ touch main.ts

### Por que usar TS? Adiciona definição estática de tipos:

- Funcionalidades do código mais explícitas;
- O transpilador TS fornece o recurso de verificação de erros;
- Maior segurança durante o desenvolvimento;
- Detecta erros durante a compilação que só seriam percebidos em execução;
- Compila um JavaScript mais resiliente; e
- Ajuda a desenvolver boas práticas de programação.
npm init
npm install -g typescript
npm install lite-server
tsc --init
everyday-types
tsconfig

### Features do TS

- Tipagem forte: torna o código mais previsível e mais fácil de encontar bugs caso algo dê errado.

- Erros em tempo de compilação: é possível vizualizar os erros em tempo de compilação e não somente em tempo de execução.

- Permite que os editores de texto consiga prever com maior facilidade os tipos das variáveis que estão sendo trabalhadas.

### Relação entre tipos de variáveis

any;//quer dizer qualquer um, declarando uma variável como o tipo any podemos atribuir qualquer valor para ela.
void;// denota um tipo de retorno para representar funções sem retorno
boolean;// representa um valor lógico, verdadeiro e falso.
string;// sequencia de caracteres.
number[] = [1, 2, 3];// Usado para representar números inteiros e frações.
undefined;//doador de valor para todas as variáveis ​​não inicializadas.
null;//indica a ausência de um valor de objeto.
enum;// fornece nome mais amigáveis, ex: enum Color{Red, Green, Blue};


### Lidando com objeto, enum e interface

Objeto - o TypeScript permite que tipos complexos (como objetos e funções) sejam facilmente definidos e usados ​​como restrições de tipo.

O tipo Enum é utilizado para atribuirmos nomes amigáveis para conjuntos de valores numéricos. Por padrão, os enums são numerados a partir do 0, podendo ser modificada essa configuração de forma manual, se necessário. Também podemos obter o nome de um determinado valor a partir da sua numeração, como podemos ver no exemplo 1.

Exemplo 1

// Definição do Enum
enum Color {Red, Green, Blue};
let c: Color = Color.Green;
// Iniciando o Enum com um valor diferente de 0
enum Color {Red = 1, Green, Blue};
let c: Color = Color.Green;
// Pegando o valor a partir da numeração
let colorName: string = Color[2]

Interface

A possibilidade de criarmos interfaces personalizadas, que nos ajudam no momento em que precisamos ter consistência entre os conjuntos de objetos, garantindo assim que os tipos adequados sejam utilizados. Podemos ver um exemplo simples de sua utilização no exemplo 2, onde apresentamos uma interface chamada IPessoa e uma classe que implementa esta interface, chamada PessoaFisica.

interface IPessoa {
    Nome: string;
    Sobrenome: string;
}

class PessoaFisica implements IPessoa {
   Nome : string;
   Sobrenome : string;
   constructor(public nome, public sobrenome) {
       this.Nome = nome
        this.Sobrenome = sobrenome;
   }
}

class ContaCorrente {
    adicionarCorrentista(pessoa: IPessoa){
        alert(pessoa.Nome);
    }
}

let cliente = new PessoaFisica("Edson", "Dionisio");
let conta = new ContaCorrente();
conta.adicionarCorrentista(cliente);

### Sobre o tipo variável Any

Usando any evitamos código duplicado fornecendo uma função que aceita qualquer tipo para o parâmetro, mas estamos perdendo as informações sobre qual era esse tipo quando a função retorna.



let obj: any = { x: 0 };
// Nenhuma das seguintes linhas de código lançará erros do compilador.
// O uso de `any` desativa todas as verificações de tipo adicionais, e é assumido
// você conhece o ambiente melhor que o TypeScript.

obj.foo();
obj();
obj.bar = 100;
obj = "hello";
const n: number = obj;

O tipo variável Any é útil quando você não deseja escrever um tipo longo apenas para convencer o TypeScript de que uma determinada linha de código está correta.



##### Leitura adicional

https://www.typescriptlang.org/docs/handbook/2/everyday-types.html
