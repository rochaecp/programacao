# C

## Compiling

~~~c
gcc hello.c -o hello  // compile
./hello               // run
~~~

## Syntax

~~~c

~~~

## Comments

~~~c
// This is a comment
/* This is a multi-line comment */
~~~

## Data Types

### Basic Data Types

- int - 4 bytes  // int x = sizeof(int);
- float - 4 bytes
- double - 8 bytes
- char - 1 byte
- boolean values: 0 == false, otherValue == true

### Derived Data Types

- Array
- Structure
- Union
- Enum
- Pointer

## Modifiers

- short
- long
- signed
- unsigned
- static

## Variables

~~~c
int myInt = 10;
double myFloat = 9.99;
char myLetter = 'a';        
float f1 = 35e3;  // Scientific Numbers - power of 10
double d1 = 12E4;
int x = 5, y = 6, z = 50;  // declare many variables
~~~

## Casting

~~~c

~~~

## Constants

- After the headers of the libraries.
- Default constants:
  - NULL - to pointers
  - EOF - end of file

~~~c
#define SIZE 10
int x[SIZE] = {};
~~~

## Operators

- Arithmetic operators: + - * / % ++ --
  - int / int == integer division
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == != > < >= <=
- Logical operators: && || !
- Bitwise operators: & | ^ << >> ~

## Strings

- C strings are character vectors.
- The last character is '\0'.
- 'a' == character, "a" == string.

~~~c
char name[15] = "Mauricio";     
char name[15] = {'A', 'n', 'a'}; 
char name[] = {'A', 'n', 'a'};              // size == 4
char name[15]; scanf ("%s", name);          // input string - without spaces
char names[2][50] = {"Mauricio", "Joana"} ; 
printf ("%s\n", names[1]); // print Joana

/* lib: string.h */
char myChar = getchar();      // input string - with spaces
gets (name);                  // char name[15];
puts ("ok\n");       
strcpy (name, "Mauricio");   
strcpy (strDest, strOrigem); 
strcat (name, " Barbosa");   
int tam = strlen (name);     
strcmp (s1, s2);               // if s1 == s2 -> 0, if s1 > s2 -> 1, if s1 < s2 -> -1
strstr (phrase, word)          // true if phrase contains word

/* Ex.: strcmp */
if (!strcmp (name, "Mauricio")
  printf ("Ok\n");
else
  puts ("not Ok\n");

/* Ex.: strtok */
#include <stdio.h>
#include <string.h>
int main()
{
  char txt[] = {"Phrase1#Phrase2#Phrase3#"};
  printf ("%s\n", strtok (txt, "#");  
  printf ("%s\n", strtok (NULL, "#");
  printf ("%s\n", strtok (NULL, "#");
  return 0;
}
~~~

## Math

~~~c

~~~

## Booleans

~~~c

~~~

## If...Else

~~~c
int x = 0;
if (x >= 0)
  //command or {commands}
else 
  //command or {commands}
~~~

## Conditional Operator 

~~~myLang

~~~

## Switch

- var: int, long, char

~~~c
switch (var) { 
   case 1: /*commands*/ break;
   case 2: /*command*/ break;
   default: /*command*/   break;
}
~~~

## While Loop

~~~c
while (num >= 0) { 
  //commands
  num--; 
}
~~~

## Do...While Loop

~~~cpp
do {
  //commands
  num--;
} while (num >= 0);
~~~

## For Loop

~~~c
for (i = 0; i <= num; i++) {
  //commands ou {commands}
}
~~~

## Break

~~~c

~~~

## Continue

~~~c

~~~

## Arrays

- Main diagonal of the matrix:  i == j.

~~~cpp
int grades1[5];       
grades[0] = 27;       
int grades2[3] = {1, 2, 3}; 
int x[50] = {0};             // initializes all indexes to zero
int x[5] = {10, 20, 30};     // uninitialized positions are filled with zero

float grades[2][3];              
float grades[2][3][5];           
char names[2][20] = {"Mauricio", "Maria"};  // ("nome = %s\n", names[0]);  -> Maur??cio
char y[2][2] = {'a', 'h'} , {'e', 'h'}};    // this is not a string
int x[2][3] = {1, 2, 3} , {4, 5, 6}}; 

/* Ex.: output */
int x[5][5] = {0};
for (int i = 0; i < 2; i++)
  for (int j = 0; j < 3; j++)
    printf ("%d ", x[i][j]);
~~~

## Pointers

- Ponteiros s??o vari??veis que apontam para uma posi????o na mem??ria.
- Um ponteiro cont??m o endere??o da posi????o de mem??ria.
- O asterisco indica que a vari??vel armazena um endere??o de mem??ria, cujo conte??do ?? do tipo especificado.
- '*' ?? um operador un??rio que devolve o valor da vari??vel localizada no endere??o que o segue.
- '&' ?? um operador un??rio que devolve o endere??o de mem??ria de seu operando.
- Se uma vari??vel 'a' armazena o endere??o de uma vari??vel 'b', dizemos que 'a' aponta para 'b'.
- O endere??o de uma vari??vel ?? sempre o MENOR dos endere??os de seus bytes, isto ??, o endere??o inicial.

- Alguns exemplos:
- **&p ?? o mesmo que *p

- Aritm??tica de Ponteiros:
- Ao serem incrementados, os ponteiros passam a apontar para a posi????o de mem??ria do pr??ximo elemento do seu tipo base.
- O quanto o valor do ponteiro ir?? aumentar ou diminuir depende do n??mero de bytes que o tipo base ocupa.
- Quando um ponteiro ?? declarado o compilador aloca um ponteiro para apontar para a mem??ria, sem que espa??o seja reservado.

- Ponteiros e Vetores:
- H?? uma estreita rela????o entre ponteiros e vetores.
- Vetores s??o SEMPRE passados por refer??ncia, pois s??o ponteiros que apontam para o primeiro elemento do vetor.
- O nome de um vetor ?? um ponteiro que aponta para a primeira posi????o do vetor.

 - *v ?? a mesma coisa que v[0]
 - v ?? a mesma coisa que &v[0]" // somente se v ?? um ponteiro
 - * (v + 1) ?? a mesma coisa que v[1]
 - * (v + i) ?? a mesma coisa que v[i]
 - v + i ?? a mesma coisa que &v[i]
 - **v ?? a mesma coisa que v[][]
 - * (*(v + i) + j) ?? a mesma coisa que v[i][j]

~~~c
// Ex.:
int *a, *b, *c;      // declara???? de ponteiro
c = NULL;         // faz com que ponteiro n??o aponte para lixo.
a = &b;           // 'a' aponta para 'b' ('a' recebe o endere??o de 'b')
c = a;          // 'c' recebe 'a' e tamb??m passa a apontar para 'b'
a = *b;         // 'a' recebe o conte??do apontado por 'b' (a recebe o valor que est?? no endere??o b)
printf ("%p\n", a);  // imprime o endere??o contido no ponteiro 'a'

// Ex.:
int *a, b;
b = 10;
a = &b;
*a = 20;
printf("%d\n", b);  // imprime 20

//Ex.: aritm??tica de ponteiros
int *a, b;
a = &b;
printf ("%p\n", a);  // imprime o endere??o de 'a'
a++;          // aritm??tica de ponteiros, incrementa 'a' em 4 (tamanho do int na minha arquitetura)
printf ("%p\n", a);  // imprime endere??o de 'a' (incrementado em 4 unidades)

// Ex.: prototipo de fun????o que recebe matriz como par??metro por refer??ncia
void somaUm (int matriz[], int tam );  // Ex.: de chamada: somaUm (minhaMatriz, tamanho);

// Ex.: prototipo de fun????o que recebe string como par??metro por refer??ncia: prot??tipo de fun????o que recebe uma string por refer??ncia como par??metro, o tamanho pode ser obtido com a fun????o strlen (namestring)
void trocaEspaco (char nome[]);  // Ex.: de chamada: trocaEspaco (namestring);    

// Ex.: vetores e ponteiros
char nome[9] = "Mauricio";
printf ("%c\n", *nome);      // printa M
printf ("%c\n", * (nome + 1);  // printa a

// Ex.: matriz e ponteiros 
int mat[2][3] = {15, 25, 35}, {10, 20, 30}};
printf ("%d ", * (* (mat + 0) + 0);   //imprime 15
printf ("%d ", * (* (mat + 0) + 1);   //imprime 25
printf ("%d ", * (* (mat + 1) + 2);   //imprime 30

// fun????o que troca os valores de x e y
void troca (int *x, int *y) {// chamar a fun????o: troca(&a, &b); 
  int temp;
  temp = *x;
  *x = *y;
  *y = temp;  
} 

// fun????o que soma 1 em todos os valores de uma matriz
void somaUm (int matriz[], int tam ) {  // chamar a fun????o: somaUm (nomeMatriz, tamanho)
  int i;
  for (i = 0; i < tam; i++)
    matriz[i] += 1;
}

// fun????o que troca os espa??os de uma string por aster??scos
void trocaEspaco (char nome[]) {    // chamar a fun????o: trocaEspaco (namestring);
  int i, tam;  
  tam = strlen (nome);
  for (i = 0; i < tam; i++)
    if (nome[i] == ' ')
      nome[i] = '*';
}
~~~

#### Ex.: pointers

~~~c
// programa com Ex.:s matrizes usando ponteiros

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define LINHAS  3
#define COLUNAS 4

void imprime (int v[][COLUNAS]) {

  int i,j;

  // Imprime arranjo jeito 1
  for (i = 0; i <  (LINHAS*COLUNAS); i++)
     printf ("i= %d ", * (*v + i);

  printf ("\n\n");

  // Imprime arranjo jeito 2
  for  (i = 0; i <  (LINHAS); i++)
    for  (j = 0; j <  (COLUNAS); j++)
       printf ("i= %d ", * (* (v + i) + j);

  printf("\n\n");
}

void imprimeP (int *v) {
   int i,j;

   // Imprime arranjo
   for  (i = 0; i <  (LINHAS * COLUNAS); i++)
        printf("i= %d ", * (v + i);

   printf("\n\n");

}

int main() {
  int v[LINHAS][COLUNAS] = {1, 2, 3, 4}, {5, 6, 7, 8 }, {9, 10, 11, 12}};
  int i=1, j=0;
  
  printf ("%d \n%d \n", * (*(v + i) +j), v[i][j]);

  return 0;
}
~~~

## Functions

- A function must perform a single task.
- Prototypes must be before the main function or in the header.

~~~c
void myFunc () {
  printf ("Hello World\n");
}
~~~

### Function Parameters

- Formal parameters.
- Actual function parameters.
- Parameters by reference

~~~c
/* Ex.: */
int mySum (int a, int b) {
  int result;
  result = a + b;
  return result; 
}

/* Ex.: */
void uppercase (char c) {
  printf ("%c", c - 32);
}

/* Ex.: Parameters by reference */
void mySwap (int *x, int *y) {  // call mySwap (&a, &b);
  int temp;
  temp = *x;
  *x = *y;
  *y = temp; 
} 
~~~

### Function Overloading

~~~c

~~~

## Scope

- Local variables.
- ...

## Recursion

- T??cnica de programa????o, na qual um subprograma (fun????o) chama a si mesmo.
- Importante: todas as fun????es recursivas devem encerrar a recurs??o a partir de um teste de valor ou condi????o!
- sempre pode ser substitu??do por programa????o com commands iterativos
- Vantagens da Recursividade
  - c??digo mais compacto;
  - especialmente conveniente para estruturas de dados definidas recursivamente, tais como ??rvores;
  - c??digo pode ser mais f??cil de entender.
  - implementa????o mais imediata de fun????es matem??ticas que j?? s??o definidas recursivamente.
- Desvantagens da Recursividade
  - maior ocupa????o de mem??ria;
  - maior tempo de processamento

~~~c
// Fatorial sem recurs??o
int fatorial (int n)
{ 
  int fat = 1, i;
  for (i = n; i > 1; i--)
    fat = fat * i;
  return fat;
}

// Fatorial com recurs??o
// Regra de recurs??o: se n=0 fat=1,  se n>0 fat de n=  n * (fat de n-1)
int fatorial (int n)
{ 
  int fat = 1;
  if (n == 0)
    fat = 1;
  else
    fat = n * fatorial (n - 1);
  return fat;
}

// Sequencia de Fibonacci com recurs??o 
unsigned int fib_rec (unsigned int n)
{ 
  if (n < 2)
    return n;
  else 
    return  (fib_rec (n - 1) + fib_rec (n - 2);
}

// Fun????o recursiva se passar num=0 imprime 4 3 2 1 0
void recursive (int num)
{  
  if (num < 5)
  {
    recursive (num + 1);
    printf ("%d ", num);    
  }
}
~~~

## Structures 

- Tipos simples em C: char, int, float, double, ponteiros.
- Tipos estruturados em C: arranjos, estruturas, arquivos.
- typedef permite ao usu??rio criar tipos personalizados. Usar sempre visibilidade global para typedef.
- Ex.:: typedef unsigned int NATURAL;
- Novos tipos s??o declarados como globais. Dados heterog??neos.
- Obs: atribui????es com estrutura: p1 = p2;
- usamos (*p).nome pois o operador Ponto tem maior preced??ncia do que o * do Ponteiro.
- Operador seta: Para fun????es com par??metro do tipo estrutura, onde ponteiros devem ser utilizados.
  - "p->nome ?? o mesmo que (*p).nome

~~~c
// Declara????o de uma estrutura
typedef struct pessoa {
  int idade;
  char nome[60];
} PESSOA;  // nome da estrutura

// Inicializa????es de uma estrutura
PESSOA p1 = {25, "Maur??cio"};    // outra forma: struct pessoa p1 = {25, "Maur??cio"};   

// Acesso aos dados da estrutura
p1.idade = 25;
scanf ("%d", &p1.idade); 
scanf ("%s", p1.nome);  //string n??o recebe &

// Vetores de estruturas
PESSOA p[2] = {25, "Mauricio Rocha"} , {30, "Mauricio Fera"}};  
printf ("%d\n%s\n", p[0].idade, p[0].nome);

// Recebendo estrutura como par??metro por refer??ncia - Ex.: 1
void printaPessoa (PESSOA *p) {  // chamanda printaPessoa (&p1);
  printf ("%d\n", p->idade);    // outra forma printf ("%d\n", (*p).idade);
  printf ("%s\n", p->nome);    // outra forma printf ("%s\n", (*p).nome);
}

// Recebendo estrutura como par??metro por refer??ncia - Ex.: 2
void lePessoa (PESSOA *p) {  // chamanda printaPessoa (&p1);
  scanf ("%d", &p->idade);  // L??-se "p seta idade" ?? o mesmo que scanf ("%d", &(*p).idade);
  scanf ("%s", p->nome);    // ?? o mesmo que scanf ("%s", (*p).nome);
}

// Estrutura dentro de estrutura
typedef struct data {
  int dia, mes, ano;
}DATA;

typedef struct pessoa {
  char nome[50];
  DATA dataNasc;
}PESSOA;

// Inicializando
PESSOA p1 = {"Mauricio", {15, 01, 1992} };
~~~

### Structures - example

~~~c
#include <stdio.h>

typedef struct pessoa {
  int idade;  
  char nome[30];  
}PESSOA;

void lePessoa (PESSOA *p) {
  scanf ("%d", &p->idade);  // L??-se "p seta idade" ?? o mesmo que scanf ("%d", &(*p).idade);
  scanf ("%s", p->nome);    // ?? o mesmo que scanf ("%s", (*p).nome);
}

void printaPessoa (PESSOA *p) {
  printf ("%d\n", p->idade);  // outra forma printf ("%d\n", (*p).idade);
  printf ("%s\n", p->nome);  // outra forma printf ("%s\n", (*p).nome);
}

int main() {
  PESSOA p; 
  lePessoa (&p);
  printaPessoa (&p);
  return 0;
}
~~~

## Lists

~~~myLang

~~~

## Tuples

~~~myLang

~~~

## Sets

~~~myLang

~~~

## Dictionaries

~~~myLang

~~~

## Trees

~~~myLang

~~~

## Hash Tables

~~~myLang

~~~

## Graphs

~~~myLang

~~~

## Files

- Arquivo ?? um conjunto de dados armazenados em mem??ria secund??ria.
- Arquivos em C: Bin??rio (estruturado) ou Texto (caracteres).
- O sistema de E/S do C utiliza o conceito de streams.
- Um stream ?? um dispositivo l??gico (um canal de manipula????o) que representa um arquivo ou um dispositivo qualquer (monitor, teclado,etc).
- Por Ex.:: stdin (que j?? usamos).
- Opera????es sobre streams s??o 'bufferizadas', ou seja, trabalham com uma ??rea de mem??ria intermedi??ria (buffer) e n??o propriamente sobre o disco.
- Os streams arquivos s??o representados por uma estrutura chamada FILE, definida em stdio.h.
- Os programas que manipulam estas streams usam ent??o um apontador para esta estrutura (FILE *)
- Cada leitura/grava????o em um arquivo causa um deslocamento da posi????o corrente do arquivo

### Binary Files

- ?? um agregado de bytes.
- Dados estruturados e dados simples (cada elemento pode conter mais de 1 byte)
- Organizado em blocos, em bytes...

- Compara????o com arquivos de texto:
  - O processamento ?? mais r??pido, pois os dados n??o precisam de qualquer convers??o.
  - Consomem menos espa??o em bytes, o que os torna mais adequados para grandes volumes da dados.
  - Conte??do n??o pode ser entendido sem a 'm??scara' correspondente (struct utilizada).
  - S?? pode ser lido pelo programa que o criou.

- Modos de abertura:
  -  'rb' - abre um arquivo bin??rio para leitura
  -  'wb' - cria/recria um arquivo bin??rio para escrita
  -  'ab' - acrescenta dados ao fim de um arquivo bin??rio existente
  -  'r+b' - abre um arquivo bin??rio para leitura/escrita
  -  'w+b'- cria/recria um arquivo bin??rio para leitura/escrita
  -  'a+b' - acrescenta em/cria um arquivo bin??rio para leitura/escrita

- Fun????o fread (<&varbuffer>,<numbytes>,<quant>,<FILE *>)
  - L?? dados do arquivo para a mem??ria principal.
  - Retorna a quantidade efetivamente lida que poder?? ser menor que o solicitado se o final do arquivo for alcan??ado previamente.
  - varbuffer armazena o dado lido corretamente. Pode ser do mesmo tamanho que numbytes.
  - numbytes ?? o tamanho da unidade a ser lida
  - quant indica quantas unidades daquela ser??o lidas, Logo o n??mero total de bytes que poder??o ser lidos ?? igual a numbytes*quant;
  - FILE * ?? o apontador para o arquivo" 
 
- Fun????o fwrite (<&varbuffer>,<numbytes>,<quant>,<FILE *>)
  - O funcionamento ?? similar a anterior, s?? que para escrita.
  - Retorna a quantidade efetivamente escrita se n??o houver erros.

- Fun????o feof (<FILE *>)
  - Indica se um arquivo chegou ao fim.
  - Retorna verdadeiro (n??o-zero) caso o final foi atingido, falso (zero) caso contr??rio.
  - Ex.: while (!feof (arq){...} 

- Fun????o fflush (<FILE *>)
  - Descarrega o conte??do em buffer para o arquivo sem fechar o stream.

- Fun????o ferror(<FILE *>)
  - Indica se a ??ltima opera????o com um arquivo produziu um erro
  - Cada nova opera????o com o arquivo modifica a condi????o de erro.
  - Ex.: de uso:
    if (ferror (arq) printf ('Erro na Leitura!');

- Acesso Rand??mico
  - Acesso a pontos de um arquivo, sem percorrer o conte??do que antecede o conte??do desejado.

- Fun????o fseek (<FILE *>, numbytesdesloc, origem)
  - Move a posi????o corrente de leitura/escrita para a posi????o calculada."  
  - S?? posiciona. N??o l?? nem grava!
  - posi????o calculada: origem + numbytesdesloc

  - numbytesdesloc: 1 * sizeof (struct estrutura)
  - Valores para origem:
    - SEEK_SET ou 0 = in??cio do arquivo
    - SEEK_CUR ou 1 = ponto corrente no arquivo
    - SEEK_END ou 2 = fim do arquivo

    - Ex.: que Volta uma posi????o

    fseek (arq, -sizeof(struct atleta), SEEK_CUR);

- Fun????o fseek(<FILE *>,<numbytesdesloc>,<origem>)" //EXPLICADO DE OUTRA FORMA
- Move a posi????o corrente de leitura/escrita para a posi????o calculada como origem+numbytesdesloc
- Os valores poss??veis, definidos, para origem s??o:
  - SEEK_SET ou 0 = In??cio do arquivo
  - SEEK_CUR ou 1 = Ponto corrente no arquivo
  - SEEK_END ou 2 = Fim do arquivo

- Fun????o rewind (<FILE *>)" 
  - Reposiciona o cursor no in??cio do arquivo." 
  - Seta a posi????o corrente do arquivo para o in??cio.

- Fun????o ftell (<FILE *>)
  - Indica, em bytes, a posi????o corrente do arquivo.

- Fun????o rename (nomeantigo, novonome) 
  - Renomeia um arquivo ou o move para um diret??rio destino.
  - Obs.: o arquivo deve estar fechado!
  - ex rename('a.dat','b.dat');

- Fun????o remove (nomedoarquivo)  
  - Apaga arquivo.

#### Ex.: binary Files

~~~c
#include <stdio.h>
#include <string.h>

// Estrutura para armazenar um atleta
typedef struct atleta
{
  char nome[50];
  int idade;
  float altura;
}ATLETA;

// L?? uma estrutura "atleta
void leAtleta (ATLETA *a)
{
  printf ("Digite o nome do atleta:\n");
  scanf ("%s", a->nome);  // a->nome == (*a).nome

  printf ("Digite a idade do atleta:\n");
  scanf ("%d", &a->idade);

  printf ("Digite a altura do atleta:\n");
  scanf ("%f", &a->altura);
}

// Imprime um atleta na tela
void imprimeAtleta (ATLETA *a)
{
  printf ("\nNome:\t%s \nIdade:\t%d \nAltura:\t%.2f\n\n", a->nome, a->idade, a->altura);
}

// Grava um atleta em um arquivo bin??rio
void gravaArquivoAtleta (ATLETA *a)
{

  FILE *arq;  // declara????o de um arquivo: "ponteiro de arquivo
  arq = fopen ("atletas.bin", "ab"); // fopen retorna um ponteiro para FILE. Se houver erro retorna NULL

  if (arq == NULL)          
    printf ("Erro ao tentar abrir o arquivo."); // aqui iria interagir com usu??rio para tratar o erro
  else
  {
    if  (fwrite (a, sizeof (ATLETA), 1, arq) != 1) // se 'a' n??o fosse ponteiro seria &a no primeiro argumento de fwrite!
      printf ("Erro na escrita.\n");
    fclose (arq);  // fecha um stream de arquivo. Todos dados que ainda estavam em buffer ser??o salvos em disco.              
  }
}

void leArquivoAtleta()
{
  ATLETA buffer;

  FILE *arq;
  arq = fopen ("atletas.bin", "rb");

  if (arq == NULL)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {
    while (!feof (arq)
      if (fread (&buffer, sizeof (ATLETA), 1, arq) == 1)  
        printf ("\n\nNome do atleta: %s \nIdade: %d \nAltura: %.2f\n", buffer.nome, buffer.idade, buffer.altura);
    fclose (arq);
  }
}

// Altera a idade de um atleta
void alteraIdade()
{
  ATLETA buffer;
  char procurado[30];
  int atletasContados = 0, encontrado = 0;;

  FILE *arq;
  arq = fopen ("atletas.bin", "r+b");  // leitura e escrita

  if (arq == NULL)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {
    printf ("Digite o nome do atleta procurado: \n");
    scanf ("%s", procurado);

    while (!feof (arq)
    {
      if (fread (&buffer, sizeof (ATLETA), 1, arq) == 1)
        if (!strcmp (buffer.nome, procurado)  // se atleta lido == atleta procurado
        {
          printf ("\n\nAtleta encontrado.\n");
          printf ("Idade cadastrada: %d\n", buffer.idade);
          printf ("\nDigite a nova idade:\n");  
          scanf ("%d", &buffer.idade);

          // posiciona cursor no lugar anterior ?? leitura, a partir do in??cio do arquivo
          // outra forma: fseek (arq, -sizeof (ATLETA),SEEK_CUR); // posiciona no lugar anterior ?? leitura, usando deslocamento negativo
          fseek (arq, atletasContados * sizeof (ATLETA), SEEK_SET);   

          fwrite (&buffer, sizeof (ATLETA), 1, arq);  // substitui
          fflush (arq);  // descarrega stream para o disco
          encontrado = 1;
        }
        atletasContados++;
    } // fim do while
    if (!encontrado)
      printf ("Nenhum atleta foi encontrado com esse nome.\n");
    fclose (arq);    
  } // fim do else
}


// L?? somente o ??ltimo atleta inserido
void lerUltimo()
{
  ATLETA buffer;

  FILE *arq;
  arq = fopen ("atletas.bin", "rb")  ;
  
  if (!arq)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {

    fseek (arq, -1 * sizeof (ATLETA), SEEK_END);  // posiciona cursor no final do arquivo e volta uma posi????o
  
    if (fread (&buffer, sizeof (ATLETA), 1, arq) == 1)
      printf ("\n\nNome do atleta: %s \nIdade: %d \nAltura: %.2f\n", buffer.nome, buffer.idade, buffer.altura);    
    fclose (arq);
  }
}

int main()
{

  ATLETA a;
  int i, numAtletas, op;

  printf ("\nDigite a op????o escolhida: \n1 - Inserir um atleta \n2 - Listar todos atletas \n3 - Modificar idade \n4 - Ler ultimo atleta da lista\n");
  scanf ("%d", &op);

  switch (op)
  {
    case 1: 
      puts ("Quantos atletas desejas ler?");
      scanf ("%d", &numAtletas);

      for (i = 0; i < numAtletas; i++)    
      {
        leAtleta (&a);
        gravaArquivoAtleta (&a);
      }  

    break;
    case 2: 
      printf ("\nAtletas lidos do arquivo: \n");
      leArquivoAtleta();
    break;
    case 3: 
      alteraIdade();
    break;
    case 4
      lerUltimo();
    break;
    default: 
      printf ("Op????o invalida.\n"); 
    break;
  }

  return 0;
}
~~~

### Text Files

- Organizados em linhas, de tamanho vari??vel.
- Cada caractere ocupa 1 byte  (8 bits).
  - Ex.:: 
  - pegando-se um n??mero inteiro (de 32 bits), com 8 d??gitos...
  - No arquivo texto ter??:
    - sizeof(char)*8 = 64 bits
  - No arquivo bin??rio ter??:
    - sizeof(int) = 32 bits  (do mesmo jeito que est?? na mem??ria!).

- Compara????o com arquivos bin??rios:
  - Facilidade para a cria????o, visualiza????o de conte??do e de edi????o de arquivos texto, com qualquer editor de textos.
  - O processamento ?? lento porque os dados, ao serem gravados, devem ser convertidos para a representa????o de caracteres em ASCII.
  - Consomem bem mais ??rea para armazenamento.
  - Caracteres num??ricos precisam ser convertidos para permitir opera????es.

- marcador de final de arquivo: caractere EOF => ?? inserida pelo sistema.
- Caractere de final de linha:
- No linux: '\n'
- No windows: '\r\n'

- A leitura ou grava????o em um arquivo texto pode ser feita: linha a linha ou caractere a caractere.

- Uma linha em um arquivo texto ?? o conjunto dos caracteres que se encontram no arquivo entre
  - o in??cio do arquivo e a primeira marca de fim de linha.
  - o in??cio do arquivo e a marca de fim de arquivo (no caso de arquivos com uma s?? linha).
  - duas marcas de fim de linha.

- Internamente ao programa, names de arquivos que incluam \ devem ser escritos com duas \\

- Algumas fun????es usadas tamb??m em arquivos bin??rios:
  -  fopen (<nome do arquivo>, <modo de abertura>) 
  -  fclose (<apontador para FILE>) 
  -  fflush (<apontador para FILE>) 
  -  feof (<FILE *>) 
  -  ferror (<FILE *>) 
  -  rewind (<FILE *>) 
  -  fseek (<FILE *>, <numbytesdesloc>, <origem>) 
  -  rename (<NomeAntigo>, <NovoNome>) 
  -  remove (<NomeDoArquivo>) 

- Fun????es espec??ficas para arquivos de texto:

- putc (<caractere>,<FILE *>)
  - Escreve um caractere no arquivo

- getc (<FILE *>)
  - Retorna um caracter lido do arquivo

- fgets (<&strbuffer>,<tamanho>,<FILE*>)
  - L?? uma string/linha de um arquivo  Obs.: a fun????o inclui um '\0' ao fim da string, 
  - logo a fun????o l?? at?? tamanho-1 ou at?? um caractere de nova linha (\n) ser lido, adicionando-o ?? string.
  - Retorna null se n??o leu nada
  - vetorchar: onde conte??do da linha ser?? armazenado ??? at?? o \n
  - sizevetor : n??mero m??ximo de bytes em vetorchar
  - point_arq : arquivo de onde ser?? feito a leitura

- fputs (<&strbuffer>,<FILE*>)
  - Escreve uma string/linha num arquivo

- fprintf (<FILE *>,<???txtE%cods???>,<var1,var2,...>)
  - Escreve caracteres em um arquivo *similar a printf()

- fscanf (<FILE *>,<???%cods???>,<&var1,&var2,...>)
  - L?? caracteres de um arquivo *similar a scanf()

- Fun????o atoi(vetorchar);
  - Transforma o conte??do de um vetor de caracteres em inteiro.

- Fun????o atof(vetorchar);
   - Transforma o conte??do de um vetor de caracteres em real.
  
- strtok(vetorchar, ???s??mbolo_separador???);
  - Extrai substrings (tokens) sucessivos de uma string, desde que separados por um separador.
  - O nome do vetor ?? usado na fun????o strtok apenas para extrair a primeira substring." 
  - Para a extra????o das demais substrings de uma mesma string , deve-se usar a constante NULL como primeiro
  - par??metro das chamadas subsequentes de strtok  (enquanto a string base for a mesma, strtok segue avan??ando pelas posi????es da string).
  - // Ex.:
  - char buffertxt[50] = "batinha#quando#nasce#se#esparrama";
  - printf ("%s\n", strtok (buffertxt, "#");  // printa "batatinha
  - printf ("%s\n", strtok (NULL, "#");    // printa "quando

- Modos de abertura:
  -  'r' - abre um arquivo texto para leitura
  -  'w' - cria/recria um arquivo texto para escrita
  -  'a' - acrescenta ao fim de um arquivo texto existente, se n??o existe cria
  -  'r+' - abre um arquivo texto para leitura/escrita
  -  'w+' - cria/recria um arquivo texto para leitura/ escrita
  -  'a+' - acrescenta em/cria um arquivo texto para leitura/escrita

#### Ex.: getc function 

~~~c
void le_texto (char nomeArq[]) { 
  char caract = 'a';
   FILE *arq;
   arq = fopen (nomeArq, "r");
   if (arq == NULL)
      printf ("Erro ao tentar abrir arquivo");
   else
   { 
  while (caract != EOF)
      { 
      caract = getc (arq);
        printf ("%c", caract);
     }
      fclose (arq);
  }
}
~~~

#### Ex.: putc function
~~~c
void insereLinhNoFim()
{
  FILE *arq;
  arq = fopen ("saida.txt", "a");

  if (!arq)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {
    putc ('\n', arq);
    fclose (arq);
  }
}
~~~

#### Ex.: fgets

~~~c
void le_texto()
{
  FILE *arq;
  char buffer[255 + 1];
  
  arq = fopen ("arquivo.txt", "r");
  if (!arq)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {
    while (fgets (buffer, sizeof (buffer), arq) ) //outra forma: while (!feof(arq)) {if (fgets(linha, sizeof(linha), arq) != NULL) ...}  
      printf ("%s", buffer);      
    fclose (arq);
  }
}
~~~

#### Ex.: fputs

~~~c
void insereStringNoFim()
{
  FILE *arq;
  char buffer[] = "Texto inserido na ultima linha.\n";
  
  arq = fopen ("arquivo.txt", "a");
  if (!arq)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {
    fputs (buffer, arq);
    fclose (arq);
  }
}
~~~

#### Ex.: fscanf

~~~c
void leLinha()
{
  char nome[255];
  FILE *arq;
  arq = fopen ("arquivo.txt", "r");
  if (arq == NULL)
    printf ("Erro ao tentar abrir / criar o arquivo.\n");
  else
  {
    while (!feof (arq)
    {
      fscanf (arq, "O nome do cara ??: %s\n", nome);
      printf ("%s\n", nome);
    }
  }
  fclose (arq);
}
~~~

#### Ex.: fprintf

~~~c
void escreveLinha()
{
  char nome[30] = "Mauricio Rocha";
  FILE *arq;
  arq = fopen ("arquivo.txt", "a");
  if (arq == NULL)
    printf ("Erro ao tentar abrir / criar o arquivo.\n");
  else
  {
    fprintf (arq, "O nome do cara ??: %s\n", nome);    
  }
  fclose (arq);
}
~~~

#### Ex.: putc and getc

- Substitui num arquivo um caractere por outro. Nome do arquivo, caractere substitu??do e caractere substituto
- s??o passados como argumento utilizando argv
- uso: programa.exe <arquivotexto> <caractere> <substituto>

~~~c
#include <stdio.h>

int main (int argc, char *argv[]) // ou **argv
{

  FILE *arq;
  char caractere; // caractere que ser?? substitu??do
  char temp;

  arq = fopen (argv[1], "r+");

  if (!arq)
    printf ("Erro ao tentar abrir arquivo");
  else
  {  
    caractere = * (argv[2]); // caractere que ser?? substitu??do ?? o conte??do apontado por argv[2] 

    while (!feof (arq)
    {
      temp = getc (arq);
      if (temp == caractere)
      {
        fseek (arq, -1*sizeof (char), SEEK_CUR); // volta a posi????o do caractere procurado
        putc (* (argv[3]), arq);
        fflush (stdin);  // escreve mudan??as
      }
    }
    fclose (arq);
  }

  return 0;
}
~~~

#### Ex.: fgets

~~~c
// Programa Ex.: - arquivos de texto - usando o fgets - l?? linha inteira
// Copia o conte??do de um arquivo de texto para outro. Ambos devem existir e seus names devem ser passados por argv
#include <stdio.h>

int main (int argc, char *argv[]) // ou **argv
{

  FILE *entrada, *saida;
  char buffer[255 + 1];


  entrada = fopen (argv[1], "r");
  if (entrada == NULL)
    printf("Erro ao tentar abrir o arquivo: %s.\n", argv[1]);
  else
  {
    saida = fopen (argv[2], "w");
    if (saida == NULL)
    {
      printf ("Erro ao tentar abrir o arquivo: %s.\n", argv[2]);
      fclose (entrada);
    }
    else
    {
      //copia uma linha ou 255 (256-1) caracteres e fecha "buffer" com o caractere nulo ('\0')
      while (fgets (buffer, sizeof (buffer), entrada) //outra forma: while (!feof(arq1)) {if (fgets(linha, sizeof(linha), arq1) != NULL) ...}
        fputs (buffer, saida); //escreve no arquivo de saida
      
      fclose (entrada);
      fclose (saida);
    }
  }

  return 0;
}
~~~

## Output

- printf and scanf formats: %d, %f, %ld, %lf, %e, %c, %s, %x, %p
  - %4d   // int with 4 spaces
  - %03d  // if var == 2 print 002
  - %.2f   // 2 decimal places
  - %c    // scanf(" %c", &myChar); or fflush - (stdin)
  - %x    // pointer in hexa
  - %p     // pointer
  - %ld    // long int
  - %lf    // long float

~~~c

~~~

### Special Characters

- \n - line break
- \0 - end of string - null character

## Input

~~~c
/* Input string - without spaces */
char name[15];
scanf ("%s", name);  // without character '&'.
~~~

## How To

### How To: Random numbers

~~~c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main() {
  int dice;
  srand (time (NULL);    
  dice = rand() % 6 + 1;  
  printf ("Dice face = %d\n", dice);
  return 0;
}
~~~

### How To: Argc and Argv parameters

- Argc is an int
- Argv is a pointer: **argv
- Arg 0 == nameBin, Arg 1 == arg1, ...
- Call: ./nameBin arg1 arg2 arg3

~~~c
#include <stdio.h>
int main (int argc, char *argv[]) {
  int i;
  for (i = 0; i < argc; i++)
    printf ("Parameter %d = %s\n", i, argv[ i ]); 
  return 0;
}
~~~

### How To: Build directives 

~~~c
//S??o commands que n??o s??o compilados. 
//S??o dirigidos ao pr??-processador, executado pelo compilador antes da execu????o do processo de compila????o propriamente dito. Veja mais em https://pt.wikibooks.org/wiki/Programar_em_C/Pr%C3%A9-processador
//S??o elas

#include<>
#define
  //#define nome_do_s??mbolo
  //#define nome_da_constante valor_da_constante
  //#define nome_da_macro(par??metros) express??o_de_substitui????o

  //Ex.: de macro
  //#define max(A, B) ((A > B) ? (A) : (B))
  //#define min(A, B) ((A < B) ? (A) : (B))
  //...
  //x = max(i, j);
  //y = min(t, r);
#undef

#ifdef
  //O c??digo entre as duas diretivas s?? ser?? compilado se o s??mbolo (ou constante) nome_do_s??mbolo j?? tiver sido definido

#ifndef
/*Um uso muito comum das diretivas de compila????o ?? em arquivos-cabe??alho, que s?? precisam/devem ser inclu??dos uma vez. Muitas vezes inclu??mos indiretamente um arquivo v??rias vezes, pois muitos cabe??alhos dependem de outros cabe??alhos. Para evitar problemas, costuma-se envolver o arquivo inteiro com um bloco condicional que s?? ser?? compilado se o arquivo j?? n??o tiver inclu??do. Para isso usamos um s??mbolo baseado no nome do arquivo. Por Ex.:, se nosso arquivo se chama "cabecalho.h", ?? comum usar um s??mbolo com o nome CABECALHO_H

#ifndef CABECALHO_H
#define CABECALHO_H
.
.
.
#endif

Se o arquivo ainda n??o tiver sido inclu??do, ao chegar na primeira linha do arquivo, o pr??-processador n??o encontrar?? o s??mbolo CABECALHO_H, e continuar?? a ler o arquivo, o que lhe far?? definir o s??mbolo. Se tentarmos incluir novamente o arquivo, o pr??-processador pular?? todo o conte??do pois o s??mbolo j?? foi definido. */

#if
#else
#elif
#endif

~~~

## GUI

- [Examples](#)

## Links

- [#](#)
- [#](#)
- [#](#)

## To be continued

- Translate this manual to english.