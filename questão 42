#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

//Nível 3: Algoritmos Avançados (31-50)

//Gerador de Números Aleatórios: Implemente um gerador de números aleatórios entre 1 e 100

#define MAX_NUMEROS 100

int main() {
	  setlocale(LC_ALL, "");
	  
    int i, quantidade;

    // Inicializa o gerador de números aleatórios com a semente baseada no tempo atual
    srand(time(NULL));

    // Leitura da quantidade de números aleatórios a serem gerados
    printf("Digite a quantidade de números aleatórios a serem gerados (máximo %d): ", MAX_NUMEROS);
    scanf("%d", &quantidade);

    // Limita a quantidade a um máximo de 100
    if (quantidade > MAX_NUMEROS) {
        printf("Quantidade excede o limite de %d. Ajustando para %d.\n", MAX_NUMEROS, MAX_NUMEROS);
        quantidade = MAX_NUMEROS;
    } else if (quantidade < 1) {
        printf("Quantidade deve ser pelo menos 1. Ajustando para 1.\n");
        quantidade = 1;
    }

    // Gera e imprime os números aleatórios
    for (i = 0; i < quantidade; i++) {
        int numero = rand() % 100 + 1;  // Gera um número aleatório entre 1 e 100
        printf("%d\n", numero);
    }

    return 0;
}
