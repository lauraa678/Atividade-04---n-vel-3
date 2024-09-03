#include <stdio.h>
#include <locale.h>

//Nível 3: Algoritmos Avançados (31-50)

//Maior Subsequência Crescente: Encontre a maior subsequência crescente em um vetor.

// Função para encontrar a maior subsequência crescente
int maiorSubsequenciaCrescente(int vetor[], int n) {
    if (n == 0) return 0;

    int dp[n];
    for (int i = 0; i < n; i++) {
        dp[i] = 1; // Inicializa o comprimento da subsequência crescente como 1
    }

    int maxLength = 1;

    // Preenche o array dp
    for (int i = 1; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (vetor[i] > vetor[j] && dp[i] < dp[j] + 1) {
                dp[i] = dp[j] + 1;
            }
        }
        if (dp[i] > maxLength) {
            maxLength = dp[i];
        }
    }

    return maxLength;
}

int main() {
	  setlocale(LC_ALL, "");
	  
    int vetor[] = {10, 22, 9, 33, 21, 50, 41, 60, 80};
    int n = sizeof(vetor) / sizeof(vetor[0]);

    int resultado = maiorSubsequenciaCrescente(vetor, n);
    printf("O comprimento da maior subsequência crescente é %d\n", resultado);

    return 0;
}
