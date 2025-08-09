# 🖥️ Projeto de Compiladores - UFABC 2025.2

- **Arthur Sena De Andrade Souza** - RA: 11202231725

## 📚 Tema do Projeto
Este projeto tem como objetivo desenvolver um compilador que converta uma linguagem especificada em Java. O projeto também visa garantir a compilação correta do programa-objeto gerado.

## ✍️ Desafio
Defina a sua própria gramática (baseada na parte em AZUL do exemplo a seguir) e os tokens
necessários. Os requisitos mínimos são os de uma calculadora simples, que recebe como
entrada variáveis, parênteses, operadores e números reais , e dá como resultado uma mensagem de erro explicativa, ou o valor calculado

### Regras
1. Atribuições de valores devem ser realizadas.
2. Possuir comando de leitura e impressão
3. A parte de expressões envolvendo os operadores matemáticos deve ser realizada de
maneira correta, respeitando a precedência.
4. O compilador deve aceitar números decimais.
5. (Extra) Possuir mensagem de erro. 
6. (Extra) Deve ter estrutura condicional.

⚠️ Os comandos de leitura do teclado e de impressão na tela devem ser disponibilizados.

## 🛠️ Execução
   
Digite no terminal os seguintes comandos:
```bash
cd IsiLanguageEmbriao
````

```bash
javac -cp "src;antlr-4.7.2-complete.jar" src\br\com\professorisidro\isilanguage\main\MainClass.java
````

```bash
java -cp "src;antlr-4.7.2-complete.jar" br.com.professorisidro.isilanguage.main.MainClass
````

```bash
javac MainClass.java
````

```bash
java MainClass
````

Seu código .isi será exibido no console e um arquivo **MainClass.java** será gerado com seu código em java.

⚠️ Caso precise editar a gramática para algum tipo de teste, digite esse comando no terminal para atualizar as regras.

```bash
java -jar antlr-4.7.2-complete.jar -o src/br/com/professorisidro/isilanguage/parser -package br.com.professorisidro.isilanguage.parser IsiLang.g4
````

## Exemplos de códigos do input.isi utilizados para conferir itens obrigatórios:
Item 1 - Declaração de Variáveis e atribuição de valores:
```bash
programa
  numero a, b;

  leia(a);
  leia(b);
fimprog.
```
Item 2 - Possuir comando de leitura e impressão
```bash
programa
  numero a, b;

  numero a, b;

  leia(a);
  leia(b);

  escreva (a);
  escreva (b);
fimprog;
```
Item 3 - Operações respeitando precedência:
```bash
programa
  numero a, b, c, d;

  a = 3;
  b = 5;
  c = 2;

  d = a + b * c;
  escreva (d);
fimprog;
```
Item 4 - Aceitar números decimais.
```bash
programa
  numero a, b, c, d;

  a = 3.5;
  b = 5.2;
  c = 2.7;

  d = a + b * c;
  escreva (d);
fimprog;
````

Item 5 - Possuir mensagem de erro.
```bash
programa

  numero a, resultado;
  texto  t1;

  leia(a);
  leia(t1);

  resultado = a + t1;

  escreva (resultado);
fimprog;

Semantic error - ERRO: Expressao com tipos incompativeis. Nao pode misturar numero e texto.
````

Item 6 - Deve ter estrutura condicional.
```bash
programa
  numero a, b, c;

  a = 2.2;
  b = 1.7;

  caso (a < b)
  {
  	c = a + 2;
  }
  senao
  {
  	c = a - 2;
  }

  escreva (c);
fimprog;
````

## Gramática

ID	: [a-z] ([a-z] | [A-Z] | [0-9])*;
NUMBER	: [0-9]+ ('.' [0-9]+)?;
OP	: '+' | '-' | '*' | '/';
ATTR : '=';
OPREL : '>' | '<' | '>=' | '<=' | '==' | '!=';
AP	: '(';
FP	: ')';
SC	: ';';
VIR  : ',';
ACH  : '{';
FCH  : '}';
WS	: (' ' | '\t' | '\n' | '\r') -> skip;

### ▶️ Link do vídeo no Youtube: [Link]()
