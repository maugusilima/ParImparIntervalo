# Documentação do programa ParImparIntervalo

## Descrição

O programa `ParImparIntervalo` é um aplicativo simples em Java que:

- Recebe dois números inteiros do usuário, sendo que o segundo número deve ser maior que o primeiro.
- Solicita ao usuário que escolha qual tipo de números quer listar: pares ou ímpares.
- Exibe todos os números pares ou ímpares, conforme escolhido, dentro do intervalo informado, incluindo os números digitados.
- Exibe os números em ordem decrescente.

---

## Código fonte explicado linha a linha

- Importa a classe `Scanner` necessária para ler as entradas que o usuário digita no console.

- Declara a classe pública chamada `ParImparIntervalo`. Toda aplicação Java precisa ter pelo menos uma classe.

public static void main(String[] args) {

- Método principal `main` que é o ponto de entrada do programa. Tudo que for colocado aqui será executado ao rodar o programa.

    Scanner scanner = new Scanner(System.in);


- Cria um objeto `scanner` para capturar os dados que o usuário digitar no console.


    int primeiroNumero, segundoNumero;

- Declara duas variáveis inteiras que armazenarão os números digitados pelo usuário.


    do {
        System.out.print("Digite o primeiro número: ");
        primeiroNumero = scanner.nextInt();

        System.out.print("Digite o segundo número (maior que o primeiro): ");
        segundoNumero = scanner.nextInt();

        if (segundoNumero <= primeiroNumero) {
            System.out.println("Erro: o segundo número deve ser maior que o primeiro. Tente novamente.");
        }
    } while (segundoNumero <= primeiroNumero);

- Laço `do-while` que repete a solicitação dos números até que o usuário digite um segundo número rigorosamente maior que o primeiro.
- Se o segundo número digitado for menor ou igual ao primeiro, exibe uma mensagem de erro e pede para tentar novamente.


    scanner.nextLine(); // Consumir o \n pendente

- Consome o caractere de nova linha pendente deixado pela leitura do `nextInt()` para evitar problemas na próxima leitura de texto com `nextLine()`.


    String opcao;

- Declara uma variável do tipo `String` chamada `opcao` que armazenará a escolha do usuário entre "par" ou "impar".

text
    do {
        System.out.print("Digite a opção (par/impar): ");
        opcao = scanner.nextLine().trim().toLowerCase();

        if (!opcao.equals("par") && !opcao.equals("impar")) {
            System.out.println("Opção inválida! Digite 'par' ou 'impar'.");
        }
    } while (!opcao.equals("par") && !opcao.equals("impar"));

- Outro laço `do-while` que solicita repetidamente ao usuário que digite uma opção válida ("par" ou "impar"), ignorando espaços em branco e diferença entre maiúsculas e minúsculas.
- Caso seja digitado algo diferente dessas opções, mostra uma mensagem de erro e solicita novamente.


    System.out.println("Números " + opcao + " no intervalo de " + primeiroNumero + " até " + segundoNumero + " em ordem decrescente:");

- Exibe uma mensagem informando o que vai mostrar a seguir, especificando o tipo de números (pares ou ímpares) e o intervalo definido.


    for (int i = segundoNumero; i >= primeiroNumero; i--) {
        if (opcao.equals("par") && i % 2 == 0) {
            System.out.println(i);
        } else if (opcao.equals("impar") && i % 2 != 0) {
            System.out.println(i);
        }
    }

- Um laço `for` que começa em `segundoNumero` e vai até `primeiroNumero`, decrementando 1 a cada passo (percorre o intervalo em ordem decrescente).
- Dentro do laço:
  - Se a opção for "par" e o número `i` for divisível por 2 (`i % 2 == 0`), imprime `i`.
  - Se a opção for "impar" e o número `i` não for divisível por 2 (`i % 2 != 0`), imprime `i`.


    scanner.close();

- Fecha o objeto `scanner` para liberar recursos associados à leitura do console.

---

## Como usar

1. Execute o programa.
2. Digite o primeiro número (inteiro).
3. Digite o segundo número (deve ser maior que o primeiro).
4. Escolha entre digitar "par" para listar números pares ou "impar" para listar números ímpares no intervalo.
5. O programa irá mostrar todos os números selecionados dentro do intervalo, em ordem decrescente.

---

## Exemplo de execução

Digite o primeiro número: 5
Digite o segundo número (maior que o primeiro): 12
Digite a opção (par/impar): par
Números par no intervalo de 5 até 12 em ordem decrescente:
12
10
8
6
---

Se tiver dúvidas ou quiser modificar o programa, sinta-se à vontade para editar este documento ou entrar em contato!

---

*Projeto criado para fins educacionais.*
