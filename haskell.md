# Haskell

## Introdução

- Haskell é uma linguagem de programação puramente funcional.
- Prelude: prompt

**Instalando no Ubuntu**
- sudo apt-get install haskell-platform

**Utilizando o ghci**
- Jeito 1:
  - Digite: ghci
  - Rode os comandos no proprio terminal
- Jeito 2:
  - Salve os comandos no arquivo file.hs
  - Digite: ghci file.hs
  - Para sair: ctrl + d ou :q

**Algumas funções existentes**:
- abs
- sqrt
- ceiling
- cos
- div
- exp
- sin
- tan
- truncate

**Algumas constantes existentes**:
- pi

**Operadores relacionais**:
- == /= > >= < <=

## Exemplo básico diretamente no console

- Para executar cada exemplo basta digitar **ghci** no terminal.

~~~sql
-- quadrado
\x -> x * x -- é o mesmo que λx . x*x
(\x -> x * x) 2 -- quadrado aplicação é o mesmo que: (λx . x*x)2

-- quadrado - associando nomes para funções anonimas
let quadrado = \x -> x * x  
quadrado 2 -- aplicação 

-- soma 2 numeros
\x -> \y -> x + y
(\x -> \y -> x + y)2 3    
~~~

## Exemplo básico a partir de arquivos

Para executar cada exemplo basta digitar:
    
    ghci exemplos.hs

Arquivo exemplos.hs
- executar com o interpretador GHCI, exemplo: ghci exemplos.hs
- apos isso, para rodar execute por exemplo: polinomio 2 (isso ira retornar 26)

~~~haskell
doubleMe x = x + x  
doubleUs x y = x*2 + y*2 
doubleUs x y = doubleMe x + doubleMe y   -- outra forma
~~~

## Exemplo básico - modificando o nome do módulo

Arquivo olamundo.hs:

~~~haskell
-- Ola mundo em Haskell, Para rodar: ghci olamundo.hs
-- apos abrir digite mainm ctrl d to quit
module HelloWorld where
main :: IO()
main = putStrLn "Ola Mundo"
~~~


## Exemplos básicos gerais

~~~haskell
-- definindo valor dentro do ghci
let a = 1

-- funcao polinomio - resolve um polinomio
polinomio :: Int -> Int -- Int: tipo do parametro e tipo da saida
polinomio x = x * x + 10 * x + 2

-- funcao quadrado
quadrado :: Int -> Int
quadrado n = n * n

-- soma
soma :: Float -> Float -> Float -- parametro -> parametro -> retorno
soma a b = a + b

-- triplo de valor
triplo :: Int -> Int
triplo var = var * 3

-- area circulo
areaCirculo :: Float -> Float
areaCirculo raio = raio * raio * pi

-- diferenca area de 2 circulos (usa funcao areaCirculo)
diferencaAreaCirculo r1 r2 = areaCirculo r1 - areaCirculo r2

-- hipotenusa
hipotenusa :: Float -> Float -> Float
hipotenusa a b = sqrt (a * a + b * b)

-- Função Fatorial (recursiva):
fac 0 = 1 -- critério de parada
fac n = n * fac(n-1) -- recursão

-- obter tipo
:t 'a'  -- 'a' :: Char 

-- funcao
sayMe :: (Integral a) => a -> String  
sayMe 1 = "Um!"  
sayMe 2 = "Dois!"  
sayMe 3 = "Três!"  
sayMe 4 = "Quatro!"  
sayMe 5 = "Cinco!"  
sayMe x = "Não está entre 1 e 5"  

charName :: Char -> String  
charName 'a' = "Albert"  
charName 'b' = "Broseph"  
charName 'c' = "Cecil"  

addVectors :: (Num a) => (a, a) -> (a, a) -> (a, a)  
addVectors (x1, y1) (x2, y2) = (x1 + x2, y1 + y2) 

capital :: String -> String  
capital "" = "String vazia, oops!"  
capital all@(x:xs) = "A primeira letra de " ++ all ++ " é " ++ [x] -- capital "Dracula"  "A primeira letra de Dracula é D"
~~~

## Funcoes de ordem superior

~~~haskell
foo1 x = x * x -- aplicacao map foo1 [1, 2, 3]
foo2 x = x + 3

ghci> foldr (+) 0 foldr (+) 0 [1, 2, 3]

-- soma todos elem de lista
somatorio :: [Float] -> Float
somatorio [] = 0
somatorio list = foldr (+) 0 list

-- norma de vetor - melhorar
sqrtList :: [Float] -> [Float]
sqrtList [] = []
sqrtList (a:x) = (a * a) : sqrtList x
norma :: [Float] -> Float
norma [] = 0
norma list = foldl (+) 0 (sqrtList list) ** 0.5

-- produto interno entre 2 vetores
prod_int :: [Float] -> [Float] -> Float
prod_int [] [] = 0
prod_int l1 l2 = foldr (+) 0 (zipWith (*) l1 l2)
~~~


## Listas

- O operador (:) é o operador de construção de listas.

~~~haskell
-- Listas
[1, 2, 3] -- ou :t [1,2,3]

-- Listas concatenação
[1, 2] ++ [3, 4] ++ [5, 6]
let lst1 = 1:2:3:[4]
let lst2 = [4,2,1]++[0]

-- Listas separando em cabeça/cauda
let h:t = [1,2,3] -- `h` com cabeça e `t` com a cauda
let h = head [1,2,3] -- retorna cabeça de uma lista: 1
let e1:e2:t = [50, 10, 20, 30];
let t = tail [1,2,3] -- retorna cauda: 2, 3

-- último elemento
last [1,2,3]

-- Listas indexação
[10, 5, 20, 30] !! 1

-- Listas contagem de elementos
lenght [1,2,3,4]

-- Contando os elementos de uma lista 1
tamanho [] = 0 -- critério de parada
tamanho lst = 1+(tamanho (tail lst))

-- Contando os elementos de uma lista 2
tamanho2 [] = 0
tamanho2 (h:t) = 1+(tamanho2 t)

-- Contando os elementos de uma lista 3
tamanho3 [] = 0
tamanho3 (_:t) = 1+(tamanho3 t)

-- Somando lista
somaLista [] = 0
somaLista (a:x) = a + somaLista x -- chamada: somaLista ([1, 2, 3, 4])

-- Dobrando lista
dobraLista :: [Int] -> [Int]
dobraLista [] = []
dobraLista (a:x) = 2 * a : dobraLista x

-- inverte lista
invertelst :: [t] -> [t]
invertelst [] = [] -- critério de parada
invertelst (x:xs) = (invertelst xs)++[x] -- aplicação: invertelst ([1, 2, 3, 4, 5])

-- Varios tipos
baseDeDados :: [(Int, String, Float)]
baseDeDados = [ (1, "André", 10.0), (2, "Carlos", 6.8), (3,"Maurício", 7.0)]

-- concatena listas
['w','o'] ++ ['o','t'] 

-- colocar rapidamente algo no inicio da lista
5:[1,2,3,4,5]

-- obtendo elemento da lista
"Steve Buscemi" !! 6 -- retorna B

-- diversos exemplos
head [5,4,3,2,1] -- cabeça 5
tail [5,4,3,2,1] -- cauda [4,3,2,1]   
last [5,4,3,2,1] -- 1   
init [5,4,3,2,1] -- todos menos ultimo [5,4,3,2]
length [5,4,3,2,1] -- 5  
null [1,2,3]  -- False  
null []  -- True  
reverse [5,4,3,2,1] -- [1,2,3,4,5]
take 3 [5,4,3,2,1]  -- extrai 3 elemen [5,4,3]
drop 1 [7,6,5,4]  -- extrai todos a partir da pos 1 [6,5,4]
minimum [8,4,2,1,5,6]  -- 1  
maximum [1,9,2,3,4] -- 9   
sum [5,2,1,6,3,2,5,7]  -- 31
product [6,2,1,2] -- 24  
4 `elem` [3,4,5,6] -- diz se 4 pertence a lista true 
[1..20] -- [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20] 
['a'..'z'] -- "abcdefghijklmnopqrstuvwxyz"
['K'..'Z'] -- "KLMNOPQRSTUVWXYZ"
[2,4..20]  -- [2,4,6,8,10,12,14,16,18,20]
[3,6..20] -- [3,6,9,12,15,18]
[20,19..1]
take 10 (cycle [1,2,3])  -- [1,2,3,1,2,3,1,2,3,1]
take 10 (repeat 5)  -- [5,5,5,5,5,5,5,5,5,5] 
replicate 3 10 --- [10,10,10]
[x*2 | x <- [1..10]]  -- dobro dos 10 primeiros nums [2,4,6,8,10,12,14,16,18,20]
[x*2 | x <- [1..10], x*2 >= 12] -- [12,14,16,18,20]
[ x | x <- [50..100], x `mod` 7 == 3] -- numeros entre 50 e 100 cujo resto div por 7 é 3

-- guardas
meuImc :: (RealFloat a) => a -> String
meuImc imc
	| imc <= 18.5 = "Abaixo do peso"
	| imc <= 25.0 = "Normal"
	| otherwise = "Acima do peso"

-- guardas
replica :: Int -> Int -> [Int]
replica e n
	| e <= 0 = [0]
	| n <= 0 = [0]
	| otherwise = [e | i <- [1..n]]

-- guardas e where
meuIMC :: (RealFloat a) => a -> a -> String  
meuIMC weight height  
    | imc <= 18.5 = "abaixo do peso"  
    | imc <= 25.0 = "normal"  
    | otherwise   = "acima do peso"  
    where imc = weight / height ^ 2  

-- expressão case
head' :: [a] -> a  
head' xs = case xs of [] -> error "Não existe head em listas vazias!"  
  (x:_) -> x 

-- expressao cae
describeList :: [a] -> String  
describeList xs = "A lista é " ++ what xs  
  where what [] = "vazia."  
        what [x] = "uma lista unitária."  
        what xs = "uma lista grande."  

-- compreensao de lista
ghci> [x*2 | x <- [1..10]]  -- [2,4,6,8,10,12,14,16,18,20]  
ghci> [x*2 | x <- [1..10], x*2 >= 12]  -- [12,14,16,18,20]  
ghci> [ x | x <- [10..20], x /= 13, x /= 15, x /= 19]  -- [10,11,12,14,16,17,18,20]
ghci> [ x*y | x <- [2,5,10], y <- [8,10,11]]  -- [16,20,22,40,50,55,80,100,110] 
ghci> [ x*y | x <- [2,5,10], y <- [8,10,11], x*y > 50]  -- [55,80,100,110]

-- filtragem
boomBangs xs = [ if x < 10 then "BOOM!" else "BANG!" | x <- xs, odd x] -- boomBangs [7..13]  retorna ["BOOM!","BOOM!","BANG!","BANG!"] 

-- listas infinitas
sequencia :: Int -> [Int]
sequencia n
	| n == 0 = [2]
	| otherwise = [ 2 ^ (2 ^ i) | i <-[0..n-1]] 

sequencia :: Int -> [Int]
sequencia n
	| n == 0 = [0]
	| otherwise = [ 2 ^ i | i <-[1..n]] 


~~~

## Outros exemplos

~~~haskell

~~~

## Links

- [aprender Haskell](http://haskell.tailorfontela.com.br/)
- [livro](http://book.realworldhaskell.org/)


