#include <stdio.h>
#include <locale.h>
#include <stdlib.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Simulação de um Elevador: Implemente uma simulação básica de um elevador em um prédio.

#define MAX_ANDARES 10

typedef struct {
    int andarAtual;
    int chamadas[MAX_ANDARES];
} Elevador;

// Função para inicializar o elevador
void inicializarElevador(Elevador *elevador) {
    elevador->andarAtual = 0; // Começa no térreo (andar 0)
    for (int i = 0; i < MAX_ANDARES; i++) {
        elevador->chamadas[i] = 0; // Nenhuma chamada inicial
    }
}

// Função para fazer uma chamada de andar
void chamarElevador(Elevador *elevador, int andar) {
    if (andar >= 0 && andar < MAX_ANDARES) {
        elevador->chamadas[andar] = 1;
    } else {
        printf("Número do andar inválido!\n");
    }
}

// Função para mover o elevador para o próximo andar
void moverElevador(Elevador *elevador) {
    for (int i = 0; i < MAX_ANDARES; i++) {
        if (elevador->chamadas[i] == 1) {
            if (i > elevador->andarAtual) {
                printf("Elevador subindo para o andar %d.\n", i);
                elevador->andarAtual = i;
                elevador->chamadas[i] = 0; // Atende a chamada
            } else if (i < elevador->andarAtual) {
                printf("Elevador descendo para o andar %d.\n", i);
                elevador->andarAtual = i;
                elevador->chamadas[i] = 0; // Atende a chamada
            } else {
                printf("Elevador já está no andar %d.\n", i);
                elevador->chamadas[i] = 0; // Atende a chamada
            }
            return;
        }
    }
    printf("Nenhuma chamada de andar.\n");
}

// Função para exibir o estado atual do elevador
void exibirEstado(Elevador *elevador) {
    printf("Elevador está atualmente no andar %d.\n", elevador->andarAtual);
}

int main() { 
         setlocale(LC_ALL, "");
         
    Elevador elevador;
    inicializarElevador(&elevador);

    int comando, andar;

    while (1) {
        printf("\nMenu:\n");
        printf("1. Fazer uma chamada de andar\n");
        printf("2. Mover o elevador\n");
        printf("3. Exibir estado do elevador\n");
        printf("4. Sair\n");
        printf("Escolha uma opção: ");
        scanf("%d", &comando);

        switch (comando) {
            case 1:
                printf("Digite o andar para chamar o elevador (0-%d): ", MAX_ANDARES - 1);
                scanf("%d", &andar);
                chamarElevador(&elevador, andar);
                break;
            case 2:
                moverElevador(&elevador);
                break;
            case 3:
                exibirEstado(&elevador);
                break;
            case 4:
                printf("Saindo...\n");
                exit(0);
            default:
                printf("Opção inválida!\n");
        }
    }

    return 0;
}
