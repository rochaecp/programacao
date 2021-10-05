# Markdown:

## Convertendo arquivos .md em .pdf com o pandoc:

~~~shell
    pandoc -o markdown.pdf markdown.md
~~~

## Headers:

~~~markdown
# header 1
## header 2
### header 3
#### header 4
##### header 5
###### header 6
~~~

## Bold e Italic:

~~~markdown
**bold text**
*italic text*
~~~

## Linha horizontal:

~~~markdown
- - - 
~~~

## Links:

~~~markdown
[link para um tutorial](https://www.markdownguide.org/basic-syntax/)
~~~

## Âncoras:

~~~markdown
[`umaAncora`](#umaAncora).
~~~

## Listas não ordenadas:

~~~markdown
- lista não ordenada
- lista não ordenada
    - lista não ordenada
        - lista não ordenada
- lista não ordenada
~~~

## listas ordenadas: 

~~~markdown
1. lista ordenada
1. lista ordenada
1. lista ordenada
~~~

## Texto destacado:

~~~markdown
    Um texto em 
    destaque aqui
~~~

## Citação em bloco:

~~~markdown
> uma citação 
~~~

## Código numa linguagem - jeito 1:

~~~c
    // um código em C
    int main() {
        x = 2;
    }
~~~

## Código numa linguagem - jeito 2:
```javascript
    // um código em JavaScript
    console.log("legal");
```

## Imagens:

~~~markdown
![descricao da imagem](https://github.com/rochamauricio/e6/blob/master/markdown/img/tux.png)
~~~

## Tabelas:

~~~markdown
| Nome | Curso | Formatura |
| :--- | --- | --- |
|Maurício Rocha| ECP | 2022|
~~~

## Tabelas alinhamento:

~~~markdown
| Nomeeeeeee | Cursooooooo | Formaturaaaaaaa |
| :--- | ---: | :---: |
|esquerda| direita | centro|
~~~

