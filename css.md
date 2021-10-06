# CSS3:

## Textos e fontes:

- Web Safe Fonts: fontes encontradas na maioria dos dispositivos;
- Quando o valor de uma propriedade é 0 não precisamos incluir a unidade.
- Quando adicionamos 2 fontes: caso a primeira não funcione a segunda é utilizada.

~~~css
.classeTexto {
  font-family: cursive, Times;      /* Redundância para fontes. */
  font-family: "Times New Roman";   /* Usamos "" para fontes com mais de uma palavra. */
  font-size: 18px;                  /* px = pixels, em 200% ou em 1.3em */
  font-style: italic;               /* Valores: normal, italic, oblique*/
  font-weight: bold;                /* Valores: normal, 100, 200, ..., 800, 900*/
  text-transform: uppercase;        /* Valores: uppercase, capitalize, lowercase */
  text-decoration: underline;       /* Padrão Default browsers: Times New Roman*/
  text-shadow: 2px 2px 4px #FF0000; /* Valores: overline, underline */
  text-indent: 30px;                /* Posição horiz, vertical, desfoque e cor */
  text-align: left;                 /* Valores: center right */
  font-variant: small-caps;         /* Valores: normal, small-caps */
  word-spacing: 0.3em;              /* Valores: default = 0.25em */
  letter-spacing: 0.3em;
  line-height: 1.8;
  white-space: nowrap;              /* Valores: pre, pre-line, pre-wrap, initial */
  color: white;
  line-height: 1.7em;               /* Valores: em px ou ems aumentar espaço entre linhas*/
}
~~~

## Cores: 

- Há 147 named colors (ex blue).

~~~css
p {
  color: red;
  color: rgb(123, 20, 233);         /* Cor na base 10 */
  color: rgba(123, 88, 9, 0.5);     /* RGB Alpha 0 <= a <= 1 */
  color: #09AA34;                   /* Hexadecimal. #FFFFFF é a mesma cor que #FFF, #AA33BB é a mesma cor que #A3B */
  color: hsl(182.2, 20%, 50%);      /* HSL colors: Hue, Saturation, and Lightness; ex: hsl(182, 20%, 50%). Hue: 0 a 360. Saturation: 0% a 100%. Lightness: 0% a 100%. */
  color: hsla(239, 45%, 22%, 0.4);
  opacity: 0.5;                     /* Nível de transparencia em porcentagem */
  box-shadow: 10px 10px 5px green;
}

/* Redundância para caso o navegador não tenha suporte para rgba. 
A última declaração têm prioridade */
h1 {
  color: rgb(22, 34, 88);
  color: rgba(22, 34, 88, 0.4);
}

/* Linear Gradient */
div {
  background: linear-gradient(to top right, rgba(255, 0, 0, 0), blue, green, yellow); /* to right, left, top;  to top right /// Angulos: 80deg */
}

/* Radial Gradient */
div {
  background: radial-gradient(red, green, blue);
}
~~~

## Backgrounds:

~~~ css
div {
  background-image: url("../img/hogwarts3.jpg"), url("../img/hogwarts.jpg");
  background-size: 95% 95%;           /* Valores: cover=cobre toda a tela */
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-color: #e6eeff;
  background-position: center center; /* x e y bottom */
  background-origin: content-box;     /* or border-box */
  background-clip: padding-box;       /* content-box   */
  background: url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
  background: radial-gradient(#ccf2ff, #80cbff, #1aa1ff, #002d4d);
}
~~~

## Bordas:

~~~css
div {
  border-radius: 20px 50px 100px 0px; /* Raio da borda arredondada border-top-left-radius */
  border-radius: 50%;                 /* se elemento é quadrado -> vira círculo */
  border-style: dotted;               /* Valores: dotted, dashed, solid, double, groove, ridge, inset, outset */  
  border-color: #ff0000;
  border-left-color: blue;
  border-right-color: blue;
  border-bottom-style: double;
  border-width: 10px;
  border: solid 5px red;
  outline: solid 5px gray;             /* Valores: outline faz quase tudo q o border faz, mas não edita lados individualmente */  
}
~~~


## Listas:

- O navegador insere um padding padrão;
- "\1F44D" = um emoji

> Ex.: lista não ordenada:
~~~css
ul {
  list-style-type: none;            /* Valores: square, "\1F44D" */
  list-style-image: url('a.jpg');   /* Imagem */
  overflow: hidden;                 /* Valores: scroll, hidden, auto, visible */
}
~~~

> Ex.: lista ordenada:
~~~css
ol {
  list-style-type: none;  /* Valores: upper-roman*/ 
}
~~~

> Ex.: last-child: aplica a propriedade somente ao último ítem de uma sequência de itens
~~~css
li:last-child {
  border-right: none;
}
~~~

## Dimensões:

~~~css
div {
  width: 100px;           /* Valores: px, em, %, ... */
  height: 100px;          /* Valores: px, em, %, ... */
  max-width: 400px;       /* Adapta-se ao tam da tela */
  min-width: 50px;        /* */
  box-sizing: border-box; /* */                      
  overflow: auto;         /* Valores: visible, hidden, scroll permite barra rolagem na div */
}
~~~

## Alinhamentos:

~~~css
div {
  float: left;     /* Valores: right, quebra texto ao redor de uma imagem */
  clear: left;     /* Controla o comportamento de elementos flutuantes */
}
~~~

## Posições:

~~~css
div {
  position: static;        /* Valores: static = é o padrão, não faz nada */
  position: fixed;         /* fixa elemento na posição */
  position: relative;   
  top: -20px;   
  left: 20px;              /* Deve ter top, left, ... definidas, posição relativa à pos do elem */
  position: absolute;      /* Igual fixed, porém em rel ao elem relativo mais próximo */
  display: inline-block;   /* Valores: inline (span, a), block(div, p, form, header ...), inline-block */
  direction: ltr;          /* Valores: left to right. há rtl, direciona texto dentro de div */
}
~~~

## Margens e paddings:

- É uma boa prática inserir as margens somente em top ou em bottom;

~~~css
div {
  margin: 50px 0px 0px 50px;    /* Valores: margin-top, margin-right, margin-bottom, margin-left */
  margin: auto;                 /* Cria espaçamento equidistante. */
  padding: 50px 0px 0px 50px;   /* Valores: padding-top, padding-right, padding-bottom, padding-left*/
  padding: 10px 5px             /* 10px top e bottom, 5px right e left */
}
~~~

## Transition: 

- A propriedade transition suaviza a transição de estado.

~~~css
div {
  transition-property: all;                         /* width height all  */
  transition-duration: 1s;                          /* Sempre em segundos! */
  transition-delay: 2s;                             /* Tempo de espera para iniciar a transição.*/
  transition-timing-function: ease;                 /* Valores: ease, ease-in, ease-out, ease-in-out, linear */
  transition: width 2s linear 1s, height 2s linear; /* Insere no estilo do objeto que irá mudar */
}
~~~


## Outros:

~~~css
div {
  cursor: pointer;              /* Valores: wait e outros em https://www.w3schools.com/cssref/pr_class_cursor.asp */
  cursor: url(img.jpg), auto;   /* Insere imagem no lugar do cursor */
}

/* Insere texto antes de todos os parágrafos */
p:before {
  content: " texto antes dos parágrafos. ";
  color: green;
}

/* Insere texto após todos os parágrafos */
p:after {
  content: " texto depois dos paragráfos. ";
  color: red;
}

/* Insere texto apos todos parágrafos quando o mouse passa sobre o parágrafo */
p:hover:after {
  content: " texto surge ao mover mouse no parágrafo. ";
  color: blue;
  background-color: yellow;
}

/* hover: realiza estilo quando mexer mouse sobre o item */
li a:hover:not(.ativo) {
  color: green;
}

/* last-child: insere estilo somente o último item de uma série de itens. Ex.: último elemento de uma lista. */
li:last-child {
  border-right: none;
}
~~~

## Inserindo CSS em páginas HTML:

> Ex.: algumas formas de inclusão:
~~~html

<link rel="stylesheet" type="text/css" href="/caminho/style.css" />

<style type="text/css">@import url("caminho/estilo.css");</style>

<style type="text/css">
body {
  color: #009900;
}
</style>

<div style="padding: 10px; margin: 10px; color: green;">(...) </div>

<link href="https://fonts.googleapis.com/css?family=Raleway" type="text/css" rel="stylesheet">
~~~ 

## Indentação:

~~~css
h1 {  /* um espaço */  
  color: blue; /* dois espaços */  
}
/* Uma linha em branco e segue próximo seletor */
~~~

## Seletores: 

> Ex.: um seletor:
~~~css
p {
  font-size: 42px; /* Edita parágrafo <p> (...) </p> */
}
~~~

> Ex.: multiplos seletores:
~~~css
h1, h2, p {
  color: green;
}
~~~

> Ex.: seleciona o caption de todas tabelas:
~~~css
table caption {
  color: green;
}
~~~

> Ex.: seletor universal - se aplica a todos elementos da página:
~~~css
* {
  color: green;
}
~~~

> Ex.: seletor atributo aplica propriedade somente a inputs do tipo submit:
~~~css
input[type="submit"] {
  width: 300px;
}
~~~

## IDs:

- Só pode haver um elemento na página com um determinado ID.

~~~css
#header {
  color: green;
}
~~~

## Classes:

- Diversos elementos podem possuir a mesma classe.

~~~css
.container {
  color: #008000;
}

div.container {
  color: green;
}
~~~

> Ex.: formata todos os parágrafos da classe .breaking:
~~~css
.p.breaking {
  color: green;
}
~~~

> Ex.: formata os <p> com class=enf q estiver dentro da div class=cont
~~~css
div.cont p.enf {
  color: green;
}
~~~

## Anotações:

- O CSS funciona como uma cascata: dentro de um elemento 'A' tem um elemento 'B' e dentro de 'B' tem um elemento 'C'.
- Box model: margin -> border -> padding -> content;
  - Visualizamos nos navegadores em "Inspecionar elemento" -> "Layout" -> "Box Model";


## Links:

[MDN - mozilla - tutorial CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)

## Continua: 







