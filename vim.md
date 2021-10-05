# Vim

- vi é um editor de textos, padrão nos sistemas Unix, criado na década de 70.
- Vim é uma versao melhorada do vi.
- O vi tem 2 modos de operaçao: 
  - modo de comando: recortar colar copiar
  - modo de inserção: digitar os textos
- Uma linha, no vi, é o que está entre duas newlines (\n)

## Atalhos

~~~markdown
- vi fileName    == abre/cria arquivo
- vi +3 fileName == abre arquivo com cursor na linha 3

**Modo de inserção:**

- i === entra no modo de inserção no ponto onde esta o cursor
- a === entra no modo de inserção um caractere à direita
- o === entra no modo de inserção na linha de baixo


**Modo de comando:**

- ESC === vai para modo de comando

- /            === inicia comando de busca   
- ?            === inicia comando de busca
- :            === inicia um ex comando
- :w           === salvar
- :w newFile   === salvar
- :w!          === salvar sobrescrevendo
- :q           === sair
- :q!          === sair sem salvar 
- :wq          === sair e salvar
- ZZ           === sair e salvar
- :e           === escapa alterações e volta ao arq original

- u === desfazer

- h ou setaEsq   === esquerda 
- l ou setaDir   === direita
- j ou setaBaixo === baixo
- k ou setaCima  === cima
- 0 ou home      === vai pro inicio da linha
- $ ou end       === vai pro fim da linha
- G === fim do arquivo
- 1G === primeira linha
- w === move cursor palavra a frente
- b === move cursor palavra atras

- yy === copia linha inteira
- yw === copia palavra
- y2TeclaBaixo === copia 2 linhas
- p === cola
- dd == deleta e recorta linha inteira

- / + enter == busca palavra onde cursor esta - cima para baixo
- ? + enter == busca palavra onde cursor esta - baixo para cima

- :set nu      === mostrar num linhas
~~~

