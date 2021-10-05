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
char names[2][20] = {"Mauricio", "Maria"};  // ("nome = %s\n", names[0]);  -> Maurício
char y[2][2] = {'a', 'h'} , {'e', 'h'}};    // this is not a string
int x[2][3] = {1, 2, 3} , {4, 5, 6}}; 

/* Ex.: output */
int x[5][5] = {0};
for (int i = 0; i < 2; i++)
  for (int j = 0; j < 3; j++)
    printf ("%d ", x[i][j]);
~~~

## Pointers

- Ponteiros são variáveis que apontam para uma posição na memória.
- Um ponteiro contém o endereço da posição de memória.
- O asterisco indica que a variável armazena um endereço de memória, cujo conteúdo é do tipo especificado.
- '*' é um operador unário que devolve o valor da variável localizada no endereço que o segue.
- '&' é um operador unário que devolve o endereço de memória de seu operando.
- Se uma variável 'a' armazena o endereço de uma variável 'b', dizemos que 'a' aponta para 'b'.
- O endereço de uma variável é sempre o MENOR dos endereços de seus bytes, isto é, o endereço inicial.

- Alguns exemplos:
- **&p é o mesmo que *p

- Aritmética de Ponteiros:
- Ao serem incrementados, os ponteiros passam a apontar para a posição de memória do próximo elemento do seu tipo base.
- O quanto o valor do ponteiro irá aumentar ou diminuir depende do número de bytes que o tipo base ocupa.
- Quando um ponteiro é declarado o compilador aloca um ponteiro para apontar para a memória, sem que espaço seja reservado.

- Ponteiros e Vetores:
- Há uma estreita relação entre ponteiros e vetores.
- Vetores são SEMPRE passados por referência, pois são ponteiros que apontam para o primeiro elemento do vetor.
- O nome de um vetor é um ponteiro que aponta para a primeira posição do vetor.

 - *v é a mesma coisa que v[0]
 - v é a mesma coisa que &v[0]" // somente se v é um ponteiro
 - * (v + 1) é a mesma coisa que v[1]
 - * (v + i) é a mesma coisa que v[i]
 - v + i é a mesma coisa que &v[i]
 - **v é a mesma coisa que v[][]
 - * (*(v + i) + j) é a mesma coisa que v[i][j]

~~~c
// Ex.:
int *a, *b, *c;      // declaraçã de ponteiro
c = NULL;         // faz com que ponteiro não aponte para lixo.
a = &b;           // 'a' aponta para 'b' ('a' recebe o endereço de 'b')
c = a;          // 'c' recebe 'a' e também passa a apontar para 'b'
a = *b;         // 'a' recebe o conteúdo apontado por 'b' (a recebe o valor que está no endereço b)
printf ("%p\n", a);  // imprime o endereço contido no ponteiro 'a'

// Ex.:
int *a, b;
b = 10;
a = &b;
*a = 20;
printf("%d\n", b);  // imprime 20

//Ex.: aritmética de ponteiros
int *a, b;
a = &b;
printf ("%p\n", a);  // imprime o endereço de 'a'
a++;          // aritmética de ponteiros, incrementa 'a' em 4 (tamanho do int na minha arquitetura)
printf ("%p\n", a);  // imprime endereço de 'a' (incrementado em 4 unidades)

// Ex.: prototipo de função que recebe matriz como parâmetro por referência
void somaUm (int matriz[], int tam );  // Ex.: de chamada: somaUm (minhaMatriz, tamanho);

// Ex.: prototipo de função que recebe string como parâmetro por referência: protótipo de função que recebe uma string por referência como parâmetro, o tamanho pode ser obtido com a função strlen (namestring)
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

// função que troca os valores de x e y
void troca (int *x, int *y) {// chamar a função: troca(&a, &b); 
  int temp;
  temp = *x;
  *x = *y;
  *y = temp;  
} 

// função que soma 1 em todos os valores de uma matriz
void somaUm (int matriz[], int tam ) {  // chamar a função: somaUm (nomeMatriz, tamanho)
  int i;
  for (i = 0; i < tam; i++)
    matriz[i] += 1;
}

// função que troca os espaços de uma string por asteríscos
void trocaEspaco (char nome[]) {    // chamar a função: trocaEspaco (namestring);
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

- Técnica de programação, na qual um subprograma (função) chama a si mesmo.
- Importante: todas as funções recursivas devem encerrar a recursão a partir de um teste de valor ou condição!
- sempre pode ser substituído por programação com commands iterativos
- Vantagens da Recursividade
  - código mais compacto;
  - especialmente conveniente para estruturas de dados definidas recursivamente, tais como árvores;
  - código pode ser mais fácil de entender.
  - implementação mais imediata de funções matemáticas que já são definidas recursivamente.
- Desvantagens da Recursividade
  - maior ocupação de memória;
  - maior tempo de processamento

~~~c
// Fatorial sem recursão
int fatorial (int n)
{ 
  int fat = 1, i;
  for (i = n; i > 1; i--)
    fat = fat * i;
  return fat;
}

// Fatorial com recursão
// Regra de recursão: se n=0 fat=1,  se n>0 fat de n=  n * (fat de n-1)
int fatorial (int n)
{ 
  int fat = 1;
  if (n == 0)
    fat = 1;
  else
    fat = n * fatorial (n - 1);
  return fat;
}

// Sequencia de Fibonacci com recursão 
unsigned int fib_rec (unsigned int n)
{ 
  if (n < 2)
    return n;
  else 
    return  (fib_rec (n - 1) + fib_rec (n - 2);
}

// Função recursiva se passar num=0 imprime 4 3 2 1 0
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
- typedef permite ao usuário criar tipos personalizados. Usar sempre visibilidade global para typedef.
- Ex.:: typedef unsigned int NATURAL;
- Novos tipos são declarados como globais. Dados heterogêneos.
- Obs: atribuições com estrutura: p1 = p2;
- usamos (*p).nome pois o operador Ponto tem maior precedência do que o * do Ponteiro.
- Operador seta: Para funções com parâmetro do tipo estrutura, onde ponteiros devem ser utilizados.
  - "p->nome é o mesmo que (*p).nome

~~~c
// Declaração de uma estrutura
typedef struct pessoa {
  int idade;
  char nome[60];
} PESSOA;  // nome da estrutura

// Inicializações de uma estrutura
PESSOA p1 = {25, "Maurício"};    // outra forma: struct pessoa p1 = {25, "Maurício"};   

// Acesso aos dados da estrutura
p1.idade = 25;
scanf ("%d", &p1.idade); 
scanf ("%s", p1.nome);  //string não recebe &

// Vetores de estruturas
PESSOA p[2] = {25, "Mauricio Rocha"} , {30, "Mauricio Fera"}};  
printf ("%d\n%s\n", p[0].idade, p[0].nome);

// Recebendo estrutura como parâmetro por referência - Ex.: 1
void printaPessoa (PESSOA *p) {  // chamanda printaPessoa (&p1);
  printf ("%d\n", p->idade);    // outra forma printf ("%d\n", (*p).idade);
  printf ("%s\n", p->nome);    // outra forma printf ("%s\n", (*p).nome);
}

// Recebendo estrutura como parâmetro por referência - Ex.: 2
void lePessoa (PESSOA *p) {  // chamanda printaPessoa (&p1);
  scanf ("%d", &p->idade);  // Lê-se "p seta idade" é o mesmo que scanf ("%d", &(*p).idade);
  scanf ("%s", p->nome);    // é o mesmo que scanf ("%s", (*p).nome);
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
  scanf ("%d", &p->idade);  // Lê-se "p seta idade" é o mesmo que scanf ("%d", &(*p).idade);
  scanf ("%s", p->nome);    // é o mesmo que scanf ("%s", (*p).nome);
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

- Arquivo é um conjunto de dados armazenados em memória secundária.
- Arquivos em C: Binário (estruturado) ou Texto (caracteres).
- O sistema de E/S do C utiliza o conceito de streams.
- Um stream é um dispositivo lógico (um canal de manipulação) que representa um arquivo ou um dispositivo qualquer (monitor, teclado,etc).
- Por Ex.:: stdin (que já usamos).
- Operações sobre streams são 'bufferizadas', ou seja, trabalham com uma área de memória intermediária (buffer) e não propriamente sobre o disco.
- Os streams arquivos são representados por uma estrutura chamada FILE, definida em stdio.h.
- Os programas que manipulam estas streams usam então um apontador para esta estrutura (FILE *)
- Cada leitura/gravação em um arquivo causa um deslocamento da posição corrente do arquivo

### Binary Files

- É um agregado de bytes.
- Dados estruturados e dados simples (cada elemento pode conter mais de 1 byte)
- Organizado em blocos, em bytes...

- Comparação com arquivos de texto:
  - O processamento é mais rápido, pois os dados não precisam de qualquer conversão.
  - Consomem menos espaço em bytes, o que os torna mais adequados para grandes volumes da dados.
  - Conteúdo não pode ser entendido sem a 'máscara' correspondente (struct utilizada).
  - Só pode ser lido pelo programa que o criou.

- Modos de abertura:
  -  'rb' - abre um arquivo binário para leitura
  -  'wb' - cria/recria um arquivo binário para escrita
  -  'ab' - acrescenta dados ao fim de um arquivo binário existente
  -  'r+b' - abre um arquivo binário para leitura/escrita
  -  'w+b'- cria/recria um arquivo binário para leitura/escrita
  -  'a+b' - acrescenta em/cria um arquivo binário para leitura/escrita

- Função fread (<&varbuffer>,<numbytes>,<quant>,<FILE *>)
  - Lê dados do arquivo para a memória principal.
  - Retorna a quantidade efetivamente lida que poderá ser menor que o solicitado se o final do arquivo for alcançado previamente.
  - varbuffer armazena o dado lido corretamente. Pode ser do mesmo tamanho que numbytes.
  - numbytes é o tamanho da unidade a ser lida
  - quant indica quantas unidades daquela serão lidas, Logo o número total de bytes que poderão ser lidos é igual a numbytes*quant;
  - FILE * é o apontador para o arquivo" 
 
- Função fwrite (<&varbuffer>,<numbytes>,<quant>,<FILE *>)
  - O funcionamento é similar a anterior, só que para escrita.
  - Retorna a quantidade efetivamente escrita se não houver erros.

- Função feof (<FILE *>)
  - Indica se um arquivo chegou ao fim.
  - Retorna verdadeiro (não-zero) caso o final foi atingido, falso (zero) caso contrário.
  - Ex.: while (!feof (arq){...} 

- Função fflush (<FILE *>)
  - Descarrega o conteúdo em buffer para o arquivo sem fechar o stream.

- Função ferror(<FILE *>)
  - Indica se a última operação com um arquivo produziu um erro
  - Cada nova operação com o arquivo modifica a condição de erro.
  - Ex.: de uso:
    if (ferror (arq) printf ('Erro na Leitura!');

- Acesso Randômico
  - Acesso a pontos de um arquivo, sem percorrer o conteúdo que antecede o conteúdo desejado.

- Função fseek (<FILE *>, numbytesdesloc, origem)
  - Move a posição corrente de leitura/escrita para a posição calculada."  
  - Só posiciona. Não lê nem grava!
  - posição calculada: origem + numbytesdesloc

  - numbytesdesloc: 1 * sizeof (struct estrutura)
  - Valores para origem:
    - SEEK_SET ou 0 = início do arquivo
    - SEEK_CUR ou 1 = ponto corrente no arquivo
    - SEEK_END ou 2 = fim do arquivo

    - Ex.: que Volta uma posição

    fseek (arq, -sizeof(struct atleta), SEEK_CUR);

- Função fseek(<FILE *>,<numbytesdesloc>,<origem>)" //EXPLICADO DE OUTRA FORMA
- Move a posição corrente de leitura/escrita para a posição calculada como origem+numbytesdesloc
- Os valores possíveis, definidos, para origem são:
  - SEEK_SET ou 0 = Início do arquivo
  - SEEK_CUR ou 1 = Ponto corrente no arquivo
  - SEEK_END ou 2 = Fim do arquivo

- Função rewind (<FILE *>)" 
  - Reposiciona o cursor no início do arquivo." 
  - Seta a posição corrente do arquivo para o início.

- Função ftell (<FILE *>)
  - Indica, em bytes, a posição corrente do arquivo.

- Função rename (nomeantigo, novonome) 
  - Renomeia um arquivo ou o move para um diretório destino.
  - Obs.: o arquivo deve estar fechado!
  - ex rename('a.dat','b.dat');

- Função remove (nomedoarquivo)  
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

// Lê uma estrutura "atleta
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

// Grava um atleta em um arquivo binário
void gravaArquivoAtleta (ATLETA *a)
{

  FILE *arq;  // declaração de um arquivo: "ponteiro de arquivo
  arq = fopen ("atletas.bin", "ab"); // fopen retorna um ponteiro para FILE. Se houver erro retorna NULL

  if (arq == NULL)          
    printf ("Erro ao tentar abrir o arquivo."); // aqui iria interagir com usuário para tratar o erro
  else
  {
    if  (fwrite (a, sizeof (ATLETA), 1, arq) != 1) // se 'a' não fosse ponteiro seria &a no primeiro argumento de fwrite!
      printf ("Erro na escrita.\n");
    fclose (arq);  // fecha um stream de arquivo. Todos dados que ainda estavam em buffer serão salvos em disco.              
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

          // posiciona cursor no lugar anterior à leitura, a partir do início do arquivo
          // outra forma: fseek (arq, -sizeof (ATLETA),SEEK_CUR); // posiciona no lugar anterior à leitura, usando deslocamento negativo
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


// Lê somente o último atleta inserido
void lerUltimo()
{
  ATLETA buffer;

  FILE *arq;
  arq = fopen ("atletas.bin", "rb")  ;
  
  if (!arq)
    printf ("Erro ao tentar abrir o arquivo.\n");
  else
  {

    fseek (arq, -1 * sizeof (ATLETA), SEEK_END);  // posiciona cursor no final do arquivo e volta uma posição
  
    if (fread (&buffer, sizeof (ATLETA), 1, arq) == 1)
      printf ("\n\nNome do atleta: %s \nIdade: %d \nAltura: %.2f\n", buffer.nome, buffer.idade, buffer.altura);    
    fclose (arq);
  }
}

int main()
{

  ATLETA a;
  int i, numAtletas, op;

  printf ("\nDigite a opção escolhida: \n1 - Inserir um atleta \n2 - Listar todos atletas \n3 - Modificar idade \n4 - Ler ultimo atleta da lista\n");
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
      printf ("Opção invalida.\n"); 
    break;
  }

  return 0;
}
~~~

### Text Files

- Organizados em linhas, de tamanho variável.
- Cada caractere ocupa 1 byte  (8 bits).
  - Ex.:: 
  - pegando-se um número inteiro (de 32 bits), com 8 dígitos...
  - No arquivo texto terá:
    - sizeof(char)*8 = 64 bits
  - No arquivo binário terá:
    - sizeof(int) = 32 bits  (do mesmo jeito que está na memória!).

- Comparação com arquivos binários:
  - Facilidade para a criação, visualização de conteúdo e de edição de arquivos texto, com qualquer editor de textos.
  - O processamento é lento porque os dados, ao serem gravados, devem ser convertidos para a representação de caracteres em ASCII.
  - Consomem bem mais área para armazenamento.
  - Caracteres numéricos precisam ser convertidos para permitir operações.

- marcador de final de arquivo: caractere EOF => é inserida pelo sistema.
- Caractere de final de linha:
- No linux: '\n'
- No windows: '\r\n'

- A leitura ou gravação em um arquivo texto pode ser feita: linha a linha ou caractere a caractere.

- Uma linha em um arquivo texto é o conjunto dos caracteres que se encontram no arquivo entre
  - o início do arquivo e a primeira marca de fim de linha.
  - o início do arquivo e a marca de fim de arquivo (no caso de arquivos com uma só linha).
  - duas marcas de fim de linha.

- Internamente ao programa, names de arquivos que incluam \ devem ser escritos com duas \\

- Algumas funções usadas também em arquivos binários:
  -  fopen (<nome do arquivo>, <modo de abertura>) 
  -  fclose (<apontador para FILE>) 
  -  fflush (<apontador para FILE>) 
  -  feof (<FILE *>) 
  -  ferror (<FILE *>) 
  -  rewind (<FILE *>) 
  -  fseek (<FILE *>, <numbytesdesloc>, <origem>) 
  -  rename (<NomeAntigo>, <NovoNome>) 
  -  remove (<NomeDoArquivo>) 

- Funções específicas para arquivos de texto:

- putc (<caractere>,<FILE *>)
  - Escreve um caractere no arquivo

- getc (<FILE *>)
  - Retorna um caracter lido do arquivo

- fgets (<&strbuffer>,<tamanho>,<FILE*>)
  - Lê uma string/linha de um arquivo  Obs.: a função inclui um '\0' ao fim da string, 
  - logo a função lê até tamanho-1 ou até um caractere de nova linha (\n) ser lido, adicionando-o à string.
  - Retorna null se não leu nada
  - vetorchar: onde conteúdo da linha será armazenado – até o \n
  - sizevetor : número máximo de bytes em vetorchar
  - point_arq : arquivo de onde será feito a leitura

- fputs (<&strbuffer>,<FILE*>)
  - Escreve uma string/linha num arquivo

- fprintf (<FILE *>,<“txtE%cods”>,<var1,var2,...>)
  - Escreve caracteres em um arquivo *similar a printf()

- fscanf (<FILE *>,<“%cods”>,<&var1,&var2,...>)
  - Lê caracteres de um arquivo *similar a scanf()

- Função atoi(vetorchar);
  - Transforma o conteúdo de um vetor de caracteres em inteiro.

- Função atof(vetorchar);
   - Transforma o conteúdo de um vetor de caracteres em real.
  
- strtok(vetorchar, ”símbolo_separador”);
  - Extrai substrings (tokens) sucessivos de uma string, desde que separados por um separador.
  - O nome do vetor é usado na função strtok apenas para extrair a primeira substring." 
  - Para a extração das demais substrings de uma mesma string , deve-se usar a constante NULL como primeiro
  - parâmetro das chamadas subsequentes de strtok  (enquanto a string base for a mesma, strtok segue avançando pelas posições da string).
  - // Ex.:
  - char buffertxt[50] = "batinha#quando#nasce#se#esparrama";
  - printf ("%s\n", strtok (buffertxt, "#");  // printa "batatinha
  - printf ("%s\n", strtok (NULL, "#");    // printa "quando

- Modos de abertura:
  -  'r' - abre um arquivo texto para leitura
  -  'w' - cria/recria um arquivo texto para escrita
  -  'a' - acrescenta ao fim de um arquivo texto existente, se não existe cria
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
      fscanf (arq, "O nome do cara é: %s\n", nome);
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
    fprintf (arq, "O nome do cara é: %s\n", nome);    
  }
  fclose (arq);
}
~~~

#### Ex.: putc and getc

- Substitui num arquivo um caractere por outro. Nome do arquivo, caractere substituído e caractere substituto
- são passados como argumento utilizando argv
- uso: programa.exe <arquivotexto> <caractere> <substituto>

~~~c
#include <stdio.h>

int main (int argc, char *argv[]) // ou **argv
{

  FILE *arq;
  char caractere; // caractere que será substituído
  char temp;

  arq = fopen (argv[1], "r+");

  if (!arq)
    printf ("Erro ao tentar abrir arquivo");
  else
  {  
    caractere = * (argv[2]); // caractere que será substituído é o conteúdo apontado por argv[2] 

    while (!feof (arq)
    {
      temp = getc (arq);
      if (temp == caractere)
      {
        fseek (arq, -1*sizeof (char), SEEK_CUR); // volta a posição do caractere procurado
        putc (* (argv[3]), arq);
        fflush (stdin);  // escreve mudanças
      }
    }
    fclose (arq);
  }

  return 0;
}
~~~

#### Ex.: fgets

~~~c
// Programa Ex.: - arquivos de texto - usando o fgets - lê linha inteira
// Copia o conteúdo de um arquivo de texto para outro. Ambos devem existir e seus names devem ser passados por argv
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
//São commands que não são compilados. 
//São dirigidos ao pré-processador, executado pelo compilador antes da execução do processo de compilação propriamente dito. Veja mais em https://pt.wikibooks.org/wiki/Programar_em_C/Pr%C3%A9-processador
//São elas

#include<>
#define
  //#define nome_do_símbolo
  //#define nome_da_constante valor_da_constante
  //#define nome_da_macro(parâmetros) expressão_de_substituição

  //Ex.: de macro
  //#define max(A, B) ((A > B) ? (A) : (B))
  //#define min(A, B) ((A < B) ? (A) : (B))
  //...
  //x = max(i, j);
  //y = min(t, r);
#undef

#ifdef
  //O código entre as duas diretivas só será compilado se o símbolo (ou constante) nome_do_símbolo já tiver sido definido

#ifndef
/*Um uso muito comum das diretivas de compilação é em arquivos-cabeçalho, que só precisam/devem ser incluídos uma vez. Muitas vezes incluímos indiretamente um arquivo várias vezes, pois muitos cabeçalhos dependem de outros cabeçalhos. Para evitar problemas, costuma-se envolver o arquivo inteiro com um bloco condicional que só será compilado se o arquivo já não tiver incluído. Para isso usamos um símbolo baseado no nome do arquivo. Por Ex.:, se nosso arquivo se chama "cabecalho.h", é comum usar um símbolo com o nome CABECALHO_H

#ifndef CABECALHO_H
#define CABECALHO_H
.
.
.
#endif

Se o arquivo ainda não tiver sido incluído, ao chegar na primeira linha do arquivo, o pré-processador não encontrará o símbolo CABECALHO_H, e continuará a ler o arquivo, o que lhe fará definir o símbolo. Se tentarmos incluir novamente o arquivo, o pré-processador pulará todo o conteúdo pois o símbolo já foi definido. */

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