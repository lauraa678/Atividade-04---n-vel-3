#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <string.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Reconhecimento de Padrões: Implemente um algoritmo básico de reconhecimento de padrões usando um vetor.

// Função para buscar o padrão na string principal
void buscarPadrao(const char* texto, const char* padrao) {
    int tamanhoTexto = strlen(texto);
    int tamanhoPadrao = strlen(padrao);

    // Itera sobre todas as possíveis posições onde o padrão pode começar
    for (int i = 0; i <= tamanhoTexto - tamanhoPadrao; i++) {
        int j;

        // Verifica se o padrão corresponde à substring a partir da posição i
        for (j = 0; j < tamanhoPadrao; j++) {
            if (texto[i + j] != padrao[j]) {
                break; // O padrão não corresponde
            }
        }

        // Se j é igual ao tamanho do padrão, então o padrão foi encontrado
        if (j == tamanhoPadrao) {
            printf("Padrão encontrado na posição %d\n", i);
        }
    }
}

int main() {
	  setlocale(LC_ALL, "");
	  
    char texto[100];
    char padrao[100];

    printf("Digite o texto: ");
    fgets(texto, sizeof(texto), stdin);
    // Remove o newline do final se estiver presente
    texto[strcspn(texto, "\n")] = 0;

    printf("Digite o padrão: ");
    fgets(padrao, sizeof(padrao), stdin);
    // Remove o newline do final se estiver presente
    padrao[strcspn(padrao, "\n")] = 0;

    buscarPadrao(texto, padrao);

    return 0;
}
