# GlossarioPOO

Glossário da matéria de Programação Orientada a Objetos.

Índice
========

   * [Construtor](#construtor)
      * [Construtor Default](#construtor-default)
      * [Construtor sem parâmetros](#construtor-sem-parâmetros)
      * [Construtor com parâmetros](#construtor-com-parâmetros)
   * [Instanciação](#instanciação)
   * [Encapsulamento](#encapsulamento)
   * [Getters e Setters](#getters-e-setters)
   * [Assinatura de Método](#assinatura-de-método)
   * [Sobrecarga de Método](#sobrecarga-de-método)
   * [Escopo de variável e método](#escopo-de-variável-e-método)
      * [Escopo de classe](#escopo-de-classe)
      * [Escopo de objeto](#escopo-de-objeto)
   * [Palavras reservadas](#palavras-reservadas)
      * [Palavra reservada new](#palavra-reservada-new)
      * [Palavra reservada instanceof](#palavra-reservada-instanceof)
      * [Palavra reservada this](#palavra-reservada-this)
      * [Palavra reservada public](#palavra-reservada-public)
      * [Palavra reservada private](#palavra-reservada-private)
      * [Palavra reservada final](#palavra-reservada-final)
   * [Relacionamentos](#relacionamentos)
      * [Relacionamento de Dependência](#relacionamento-de-dependência)
      * [Relacionamento de Agregação](#relacionamento-de-agregação)
      * [Relacionamento de Composição](#relacionamento-de-composição)
      

Construtor
========

Um construtor é um processo pertencente a uma classe, tendo como objetivo a criação
de de um objeto. Mais especificamente é uma operação que é realizada quando um objeto
é instanciado, retornando assim no final da operação a nova instancia do objeto.
Uma classe pode definir nenhum ou vários construtores (caso nenhum seja definido, o 
construtor default é utilizado).

Os construtores são representados no Diagrama de Classes da UML pelo estereótipo *create*.

Construtor default
--------

O construtor default é o construtor padrão de uma classe que não definiu nenhum construtor.
Caso a classe possua pelo menos um construtor, o construtor default não pode ser aplicado 
para essa mesma classe.

Construtor sem parâmetros
--------

Um construtor pode ou não possuir parâmetros de entrada, porém cada classe só pode conter 
um contrutor sem parâmetros (obedecendo a regra das [assinaturas de método](#assinatura-de-método)).

**Exemplo:**

```java
public class ExemploConstrutor {

    public ExemploConstrutor() {
        // realiza operacoes
    }

}
```

Construtor com parâmetros
--------

O construtor de uma classe pode conter parâmetros de entrada, ademais não existe limitação
referente ao tipo ou quantidade de parâmetros.

**Exemplo:**

```java
public class ExemploConstrutor {

    public ExemploConstrutor(int valor1, int valor2) {
        // realiza operacoes
    }

}
```

Instanciação
========

A instanciação de uma classe é o processo utilizado para gerar uma materialização da
classe, sendo que essa materialização é denominada objeto. Para realizar a instanciação
é utilizada a palavra reservada [new](#palavra-reservada-new).

**Exemplo:**

```java
public class ExemploInstanciacao {

    public void foo() {
        ExemploInstanciacao exemplo = new ExemploInstanciacao();
        
        //realiza outras operacoes
    }

}
```

Encapsulamento
========

Encapsulamento é um dos princípios da orientação a objetos, sendo que seu objetivo
é ocultar os atributos de uma classe, assim protegendo o estado de cada objeto.

Getters e Setters
========

Getters e Setters são métodos de classe utilizados para aplicar o princípio
do encapsulamento. 
Os métodos getters servem para recuperar os atributos da classe. 
Os métodos setters servem para atribuir valores para os atributos da classe.

**Exemplo:**

```java
public class ExemploEncapsulamento {
    
    private int valor;
    
    public void setValor(int novoValor) {
        valor = novoValor;
    }
    
    public int getValor() {
        return valor;
    }
}
```

Assinatura de Método
========

A assinatura de um método demonstra a exclusividade de um método, ou seja, sua
identidade. A assinatura de um método é composta por seu nome, tipo de retorno,
tipo dos parâmetros e a quantidade de parâmetros. Desta forma, não pode haver
dois métodos pertencentes a mesma classe com todas as características 
definidas acima exatamente iguais.

Sobrecarga de Método
========

A sobrecarga de um método demonstra a capacidade de criação de vários métodos
como o mesmo nome, porém com diferenciações nos parâmetros e/ou tipo do retorno.

**Exemplo:**

```java
public class ExemploSobrecarga {

    public int foo(int a) {
        // faz algo
    }
    
    public double foo(double a) {
        // faz algo
    }

}
```

Escopo de variável e método
========

O escopo de uma variável ou método demonstra a visibilidade deste componente perante 
o sistema desenvolvido. De certa forma, podem haver dois tipos de escopos: o escopo 
de classe e o escopo de objeto.


Escopo de classe
--------

No escopo de classe o atributo ou método é pertencente a classe onde foi definido,
desta forma, não é necessário ter uma instância da classe para acessar o componente.

No Java, para representar uma variável ou método como sendo do escopo de uma classe é 
utilizada a palavra reservada static.

**Exemplo:**

```java
public class ExemploEscopo {

    // variavel de classe
    public static int valor = 10;
    
    // metodo de classe
    public static void foo() {
        // faz algo
    }

}
```

Escopo de objeto
--------

No escopo de objeto quaisquer métodos ou atributos pertencentes a classe que não
forem estáticos são de escopo do objeto. Assim, podem ser alterados individualmente
necessitando de instâncias do objeto. Caso não seja utilizada a palavra reservada
static os componentes são por padrão considerados como escopo de objeto.


Palavras reservadas
========

As palavras reservadas são comandos da linguagem que não podem ser utilizadas
para a definição de nomes de variáveis/métodos pois só podem ser usadas para 
realizar suas funções específicas.

Palavra reservada new
--------

A palavra reservada 'new' tem por função [instanciar](#instanciação) um objeto
a partir de uma classe. Esse objeto criado pode ser referênciado por uma variável
ou não.

**Exemplo:**

```java
public class ExemploPalavrasReservadas {

    public void foo() {
        // instanciacao sem referencia
        new ExemploPalavrasReservadas();
        
        // instanciacao com referencia
        ExemploPalavrasReservadas pr = new ExemploPalavrasReservadas();
    }

}
```

Palavra reservada instanceof
--------

A palavra reservada 'instanceof' tem por função comparar se um objeto pertence ao mesmo 
tipo de determinada classe especificada. Deste modo, é retornado um valor booleano pela
comparação, sendo interessante utilizar esse comando em desvio de fluxos.

**Exemplo:**

```java
public class ExemploPalavrasReservadas {

    public void foo(Objeto obj) {
        
        if(obj instanceof ExemploPalavrasReservadas) {
            // faz algo
        }
        
    }

}
```

Palavra reservada this
--------

A palavra reservada 'this' é utilizada para um objeto fazer referência dele mesmo.
Geralmente é utilizado dentro de métodos para fazer referência a atributos do
próprio objeto. Também é utilizado nos métodos [setters](#getters-e-setters) para
diferenciar as variáveis locais dos atributos.

**Exemplo:**

```java
public class ExemploPalavrasReservadas {

    private int valor;

    public void foo(int valor) {
        this.valor = valor;
        
        // realiza operacoes
    }

}
```

Palavra reservada public
--------

A palavra reservada 'public' é um modificador de acesso utilizado para definir a visibilidade
de um atributo ou método de uma classe, ou até mesmo da própria classe. Usando esta palavra 
reservada, os componentes marcados com a mesma serão visiveis por toda e qualquer classe do sistema.

Esta palavra chave é utilizada antes do tipo/retorno da variável/método.

**Exemplo:**

```java
// exemplo em classe
public class ExemploPalavrasReservadas {

    // exemplo em variavel
    public double PI;
    
    // exemplo em metodo
    public void foo() {
        // faz algo
    }
    
}
```

Palavra reservada private
--------

A palavra reservada 'private' é um modificador de acesso utilizado para definir a visibilidade
de um atributo ou método de uma classe. Usando esta palavra reservada os componentes da classe
serão visíveis apenas pela própria classe, permitindo apenas que o próprio objeto acesse
ou altere seus dados e/ou comportamentos.

**Exemplo:**

```java
public class ExemploPalavrasReservadas {

    // exemplo em variavel
    private double PI;
    
    // exemplo em metodo
    private void foo() {
        // faz algo
    }
    
}
```

Palavra reservada final
--------

A palavra reservada 'final' indica que o atributo marcado será apenas de leitura, ou seja, seu
valor é constante. Quando utilizado em variáveis primitivas, seu valor será realmente constante,
porém em objetos, a referência não pode ser mudada, mas isso não impede do estado do objeto ser
alterado.

Quando utilizada em métodos de uma classe, significa que o método não poderá ser sobrescrito, assim
como é possível definir uma classe como final, desta forma não permitindo que ela seja a classe
pai de outras classes.

**Exemplo:**

```java
// exemplo em classe
final class ExemploPalavrasReservadas {

    // exemplo em variavel
    final double PI = 3.14d;
    
    // exemplo em metodo
    final void foo() {
        // faz algo
    }
    
}
```

Relacionamentos
========

Relacionamento de dependência
--------

O relacionamento de dependência de classes ocorre quando uma classe necessita
da instância de outra classe que que a mesma consiga realizar suas operações.
Desta forma, geralmente esse objeto é recebido como argumento pela classe para
que a operação seja realizada.

**Exemplo:**

```java
public class ExemploRelacionamentos {

    public void foo(ObjetoDependencia objDep) {
        // realiza operacoes com o objDep
    }

}
```

**Exemplo UML:**

<img align="center" src="/imagens/dep.png">

Relacionamento de Agregação
--------

A agregação é um relacionamento onde uma classe é composta por outras classes
internamente, ademais esses classes que compõem a classe podem existir mesmo
sem que a classe exista. Desta forma, os mesmos objetos fazem sentido mesmo que
esta classe que os compõem deixe de existir.

**Exemplo UML:**

<img align="center" src="/imagens/agreg.png">

Relacionamento de Composição
--------

A composição é um relacionamento onde uma classe é composta por outras classes
internamente, ademais os objetos que compõem a classe pertencem exclusicamente
a ela mesma, desta forma, as classes que compõem esta mesma naõ fazem sentido
caso esta classe não exista.

**Exemplo UML:**

<img align="center" src="/imagens/comp.png">
