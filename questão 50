#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <string.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Compressão de Dados RLE: Implemente o algoritmo de compressão de dados RLE (Run-Length Encoding).

#define MAX_SIZE 1000

// Função para compressão usando RLE
void compressaoRLE(const char* entrada, char* saida) {
    int i, j = 0;
    int n = strlen(entrada);

    for (i = 0; i < n; i++) {
        // Contar o número de ocorrências consecutivas do caractere atual
        int cont = 1;
        while (i < n - 1 && entrada[i] == entrada[i + 1]) {
            cont++;
            i++;
        }
        // Armazenar o caractere e a contagem no buffer de saída
        saida[j++] = entrada[i];
        saida[j++] = cont + '0';  // Convertendo número para caractere
    }
    saida[j] = '\0';  // Null-terminator para a string de saída
}

// Função para descompressão usando RLE
void descompressaoRLE(const char* entrada, char* saida) {
    int i, j = 0;
    int n = strlen(entrada);

    for (i = 0; i < n; i += 2) {
        char caractere = entrada[i];
        int cont = entrada[i + 1] - '0';  // Convertendo caractere para número

        // Repetir o caractere 'cont' vezes
        for (int k = 0; k < cont; k++) {
            saida[j++] = caractere;
        }
    }
    saida[j] = '\0';  // Null-terminator para a string de saída
}

int main() {
	    setlocale(LC_ALL, "");
	    
    char texto[MAX_SIZE];
    char compressado[MAX_SIZE];
    char descompressado[MAX_SIZE];

    printf("Digite o texto para compressão: ");
    fgets(texto, sizeof(texto), stdin);
    texto[strcspn(texto, "\n")] = 0;  // Remove o newline no final

    compressaoRLE(texto, compressado);
    printf("Texto comprimido: %s\n", compressado);

    descompressaoRLE(compressado, descompressado);
    printf("Texto descomprimido: %s\n", descompressado);

    return 0;
}
