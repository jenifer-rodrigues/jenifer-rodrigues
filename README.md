// Função para verificar se um número é primo
function fVerificaPrimo(num) {
    // Verifica se o número é menor que 2, que não é primo
    if (num < 2)
        return false;

    // Loop para verificar se o número é divisível por algum número até a raiz quadrada dele
    for (let i = 2; i <= Math.sqrt(num); i++) {
        // Se o número for divisível por outro além de 1 e ele mesmo, não é primo
        if (num % i === 0) {
            return false;
        }
    }
    // Se passar por todos os testes, o número é primo
    return true;
}

// Função para imprimir os 10 maiores números primos a partir de um número fornecido
function fImprimir_10_Maiores_Numeros_Primos(num) {
    // Inicializa um contador para contar os números primos encontrados
    let contador = 0;
    // Inicializa um contador para começar do número fornecido pelo usuário
    let k = num;
  
    // Loop para encontrar e imprimir os 10 maiores números primos
    while (contador < 10) {
        // Verifica se o número atual é primo usando a função fVerificaPrimo
        if (fVerificaPrimo(k)) {
            // Se for primo, imprime o número e incrementa o contador de primos encontrados
            console.log("O número [" + k + "] é primo!");
            contador++;
        }
        // Decrementa o número atual para verificar o próximo número
        k--;
    }
    // Após encontrar os 10 maiores números primos, exibe a mensagem de sucesso
    console.log("O programa foi executado com sucesso!");
}

// Solicita ao usuário que digite um número
let numero = parseInt(prompt("Digite um número: "));
// Chama a função para imprimir os 10 maiores números primos a partir do número fornecido
fImprimir_10_Maiores_Numeros_Primos(numero);
