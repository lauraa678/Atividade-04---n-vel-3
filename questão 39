#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h> 
#include <string.h>

//Nível 3: Algoritmos Avançados (31-50)

//Avaliação de Expressão Pós-fixa: Avalie o valor de uma expressão pós-fixa.

#define MAX 100

// Estrutura da pilha para operandos
typedef struct {
    int itens[MAX];
    int topo;
} Pilha;

// Função para inicializar a pilha
void inicializarPilha(Pilha* p) {
    p->topo = -1;
}

// Função para empilhar um item
void empilhar(Pilha* p, int item) {
    if (p->topo >= MAX - 1) {
        printf("Pilha cheia!\n");
        return;
    }
    p->itens[++p->topo] = item;
}

// Função para desempilhar um item
int desempilhar(Pilha* p) {
    if (p->topo < 0) {
        printf("Pilha vazia!\n");
        return -1; // Valor de erro
    }
    return p->itens[p->topo--];
}

// Função para avaliar a expressão pós-fixa
int avaliarPosfixa(const char* posfixa) {
    Pilha p;
    inicializarPilha(&p);

    for (int i = 0; posfixa[i] != '\0'; i++) {
        char c = posfixa[i];

        if (isspace(c)) {
            continue; // Ignora espaços
        }

        if (isdigit(c)) {
            // Se o caractere for um dígito, converte para inteiro e empilha
            int num = 0;
            while (isdigit(posfixa[i])) {
                num = num * 10 + (posfixa[i] - '0');
                i++;
            }
            i--; // Ajusta o índice após o loop
            empilhar(&p, num);
        } else if (c == '+' || c == '-' || c == '*' || c == '/') {
            // Se o caractere for um operador, desempilha dois operandos
            int operando2 = desempilhar(&p);
            int operando1 = desempilhar(&p);
            int resultado;

            switch (c) {
                case '+': resultado = operando1 + operando2; break;
                case '-': resultado = operando1 - operando2; break;
                case '*': resultado = operando1 * operando2; break;
                case '/': 
                    if (operando2 == 0) {
                        printf("Erro: Divisão por zero!\n");
                        return -1; // Valor de erro
                    }
                    resultado = operando1 / operando2; 
                    break;
                default: 
                    printf("Operador inválido!\n");
                    return -1; // Valor de erro
            }
            empilhar(&p, resultado);
        }
    }

    // O resultado final deve estar no topo da pilha
    return desempilhar(&p);
}

int main() {
	   setlocale(LC_ALL, "");
	   
    char posfixa[MAX];

    printf("Digite a expressão pós-fixa: ");
    fgets(posfixa, sizeof(posfixa), stdin);

    // Remove a nova linha do final da entrada, se existir
    size_t len = strlen(posfixa);
    if (len > 0 && posfixa[len - 1] == '\n') {
        posfixa[len - 1] = '\0';
    }

    int resultado = avaliarPosfixa(posfixa);

    if (resultado != -1) {
        printf("Resultado: %d\n", resultado);
    }

    return 0;
}
