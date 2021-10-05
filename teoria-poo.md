# Orientação a Objetos

- Os 4 pilares da POO são: Abstração, Encapsulamento, Herança e Polimorfismo.

- **Classes**
    - Nomes de classe iniciam com letra maiúscula.

- **Objetos**

- **Membros de uma classe**

- **Propriedades de uma classe**

- **Encapsulamento**
    - Restringir o acesso aos membros da classe.

- **Modificadores de acesso**
    - public:     atributo/metodo visivel em qualquer classe  
    - private:    atributo/metodo visivel apenas na classe onde foi criado  
    - protected:  atributo/metodo visivel em classes onde são criados ou herdados

- **Métodos**
    - Métodos são blocos de códigos que só são executados quando chamados.

- **Métodos Construtores**
    - São métodos que são executados assim que instanciamos um objeto de uma classe.
    - São sempre public.
    - Possuem sempre o nome da classe.

- **Métodos Getters e Setters**
    - São utilizados para obtermos e modificarmos atributos privados.
    - São sempre public.
    - Pode-se utilizar um ou outro ou ambos.

- **Comando this**
    - Utilizado para referenciar atributos de uma classe. Ex.: this.nomeAtributo = 10;
    - Em C# utilizamos o caractere '_' antes do nome do atributo.

- **Sobrecarga de Métodos**

- **Herança**
    - Em C# não existe herança múltipla: uma classe só pode extender uma única classe por vez.

- **Polimorfismo**

- **Sobrescrita de Métodos**
    - Em C# para um método poder ser sobrescrito ele precisa da palavra reservada *virtual*.
    - Em C# para um método poder sobrescrever outro precisamos adicionar a palavra reservada *override*.

- **Atributos Estáticos**
    - Podemos ter acesso a atributos Static sem a necessidade de instanciar um objeto a partir de uma classe.

- **Métodos Estáticos**
    - Podemos ter acesso a métodos Static sem a necessidade de instanciar um objeto a partir de uma classe.

- **Abstração**
    - **Classes abstratas**
        - Classe que pode conter métodos obrigatórios para todas as classes que a herdarem.
        - Métodos obrigatórios podem ser públicos ou protegidos.
        - Podem conter também métodos convencionais (não obrigatórios) para que as classes que a herdam possam utilizar.
        - Não se pode instanciar um objeto a partir de uma classe abstrata.
        - Garante uma estrutura pré moldada de métodos que devem ser implementados.
        - É uma forma de criar um padrão para os projetos.
        - Cada classe pode herdar apenas de uma classe abstrata.
    - **Métodos abstratos**
        - É um método obrigatório de uma classe abstrata.
        - Precisa obrigatóriamente ser sobrescrito na classe que herdar da classe abstrata que o contém.

- **Interfaces**
    - Utilizada para criarmos exclusivamente métodos obrigatórios.
    - Uma classe pode implementar várias interfaces.
    - Os métodos da interface não possuem implementação na interface.
    - A implementação dos métodos da interface fica na classe que implementa a mesma.
    - No C# um método criado na interface é por padrão público e abstrato.
    - No C# por convenção iniciamos o nome de interfaces com a letra 'I', ex.: IProductService.

- **Interfaces Múltiplas**

- **Enums**

- **Exceções**

- Ver anotações papel - Java: Composição, 



