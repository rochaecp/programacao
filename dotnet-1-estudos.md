# .NET

## Histórico

- Ambiente de desenvolvimento ou plataforma lançada no ano 2000;
- CLR - Common Language Runtime;
  - C#, VB.NET, J# - cada uma com um compilador -> vai para CLR que gera linguagem de máquina;
- Xamarin - rodar em Android e iOS apps criados com C#;
- 2014 - é criada a .NET Foundation para gestão de projetos open source;
- 2015 - é lançado o C# 6.0 e o Visual Studio Code;
- .NET Framework é passado!
- 2016 - .NET Core 1.0 (.NET 5)- totalmente novo, open source e multiplataforma;

## O que é .NET?

- É uma infraestrutura para desenvolvimento de software criada pela Microsoft.
- É multiplataforma e open source.
- Uma aplicação .NET é desenvolvida e roda em uma das seguintes implementações do .NET:
  - .NET Core (mais atual)
  - .NET Framework (obsoleto)
  - Mono
  - Universal Windows Plataform (UWP) - Xbox
- .NET Standard Library - "contrato" para cada implementação.
- Cada implementação contém um ou mais .NET Runtimes (ambientes de execução):
  - .NET Core: CoreCLR e CoreRT
  - .NET Framework: CLR (Common Language Runtime)
  - Mono: Mono Runtime
  - Universal Windows Plataform (UWP): .NET Native
- Atualmente a Microsoft desenvolve e suporta 3 linguagens para .NET:
  - C# - foco em OOP
  - F# - foco em prog funcional
  - VB  

## O que é o C#

- É uma linguagem fortemente tipada, orientada a objetos de sintaxe similar à do Java e do C++;
- Os programas em C# são executados no .NET, que inclui:
  1. CLR (Common Language Runtime);
    - CLR é uma máquina virtual que fornece um ambiente de tempo de execução para o .NET framework.
  2. Conjunto Unificado de bibliotecas e classes;
    - Úteis para, por ex, ler um arquivo, data e hora ...
- Atualmente o compilador do C# é o Roslyn, que é open source;

- O código fonte escrito em C# é compilado em uma linguagem intermediária (IL).
- O código e os recursos de IL são armazenados no disco em um executável (.exe ou .dll) chamado assembly
- Ao executarmos o programa em C# o assembly é carregado no CLR.
- O CLR executará a compilação just-in-time (JIT) para converter o código IL em intruções de máquina nativas (dotnet run faz isso).

- O CLR fornece outros serviços tais como:
  - Garbage Collector
  - Exception Handler
  - Resources Manager

## Principais conceitos organizacionais em C#

- Programas - arquivos .cs
- namespaces - tipos contem membros que podem ser organizados em namespaces
- tipos - classes, interfaces
- membros - campos, metodos, propriedades e eventos por ex
- assemblies - programas compilados sao empacotados em assemblies (.exe ou .dll)

- O C# permite a criação de classes e métodos aninhados. 

### namespace

- Geralmente usamos o nome do projeto como namespace de cada uma das classes.
- Havendo uma estrutura de diretórios ela também influenciará no namespace.
- Ex.: namespace NomeDoProjeto.MeuDiretorio
	- para usar uma classe de dentro do dir MeuDiretorio: var s = new MeuDiretorio.Nomeclasse() ou cláusula using;
	- no vscode clica na classe, ctrl + . para incluir a clausa de using
- Funciona como um pacote. Dentro dele pode existir classes, membros etc

### debug

- abra o projeto com: ctrl + k,  ctrl + o
- marque um breakpoint numa linha de código e pressione F5.
- pula para a próxima linha com F10
- para entrar dentro do metodo executado na linha corrente pressione F11
- para executar sem para até o fim: F5
- passando o mouse sobre as variáveis conseguimos saber seus valores durante a execução

## POO no .NET

- Tudo no .NET são objetos, até os tipos de dados são objetos pois contém métodos e propriedades.
- Diagrama de classes, UML
- Tipos em C#:
  - Por valor: mem gerenciada pelo C#
  - Por referência
- Métodos
  - Getters - métodos acessores
  - Setters - métodos modificadores
  - Construct - sem retorno, é executado 1 só vez, deve ser public
- Propriedades
  - São um par de metodos get e set
- Eventos  
  - Mensagens que a classe dispara
  - Estrutura Delegate - delega variavel que guarda endereço da função que é disparada com o evento

### Projetos de exemplo

- [Repositorio com exemplos de POO utilizando o Console](#)


## Estudar

- repetir treino curso Ralf - API
- tutoriais ricardo uso do entity framework <https://github.com/rvlampert/entity-framework/blob/main/TUTORIAL.md>
- Instalar o Beaver
- Ver dotnet-csharp-old.md
- Herança, Base()
- interfaces e Repositorios - exemplos
- Classes Context, DBContext
- Classes Service
- Entity Framework
- Fluent Validation
- Coleções
- Exceções
- Curso dio asp
- appsettings.json: <https://docs.microsoft.com/pt-br/aspnet/core/fundamentals/configuration/?view=aspnetcore-5.0>

- [colab ricardo](https://colab.research.google.com/drive/13HG5I2KLNUvDvziBpzWJMvxCyY5TpB3k?usp=sharing)
- [colab ricardo2](https://colab.research.google.com/drive/1agvs4efXPZdohXcKjkJCXqXejqSV0HEs?usp=sharing)

## Links

- [Documentação Oficial](https://docs.microsoft.com/pt-br/dotnet/)
- [W3schools](https://www.w3schools.com/cs/)