#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h> 
#include <string.h>

//Nível 3: Algoritmos Avançados (31-50)

//Conversão de Infixa para Pós-fixa: Converta um expressão aritmética infixa para pós-fixa.

#define MAX 100

// Estrutura da pilha para operadores
typedef struct {
    char itens[MAX];
    int topo;
} Pilha;

// Função para inicializar a pilha
void inicializarPilha(Pilha* p) {
    p->topo = -1;
}

// Função para empilhar um item
void empilhar(Pilha* p, char item) {
    if (p->topo >= MAX - 1) {
        printf("Pilha cheia!\n");
        return;
    }
    p->itens[++p->topo] = item;
}

// Função para desempilhar um item
char desempilhar(Pilha* p) {
    if (p->topo < 0) {
        printf("Pilha vazia!\n");
        return '\0'; // Valor de erro
    }
    return p->itens[p->topo--];
}

// Função para obter o item no topo da pilha
char topoPilha(Pilha* p) {
    if (p->topo < 0) {
        return '\0'; // Valor de erro
    }
    return p->itens[p->topo];
}

// Função para verificar se um caractere é um operador
int ehOperador(char c) {
    return c == '+' || c == '-' || c == '*' || c == '/';
}

// Função para verificar a precedência dos operadores
int precedencia(char op) {
    switch (op) {
        case '+':
        case '-': return 1;
        case '*':
        case '/': return 2;
        default: return 0;
    }
}

// Função para converter infixa para pós-fixa
void infixaParaPosfixa(const char* infixa, char* posfixa) {
    Pilha p;
    inicializarPilha(&p);

    int j = 0; // Índice para a expressão pós-fixa

    for (int i = 0; infixa[i] != '\0'; i++) {
        char c = infixa[i];

        if (isspace(c)) {
            continue; // Ignora espaços
        }

        if (isalnum(c)) {
            posfixa[j++] = c; // Adiciona operandos diretamente à saída
        } else if (c == '(') {
            empilhar(&p, c); // Empilha parênteses de abertura
        } else if (c == ')') {
            while (!ehOperador(topoPilha(&p)) && topoPilha(&p) != '(') {
                posfixa[j++] = desempilhar(&p); // Desempilha até encontrar '('
            }
            desempilhar(&p); // Remove '('
        } else if (ehOperador(c)) {
            while (ehOperador(topoPilha(&p)) && precedencia(topoPilha(&p)) >= precedencia(c)) {
                posfixa[j++] = desempilhar(&p); // Desempilha operadores com maior ou igual precedência
            }
            empilhar(&p, c); // Empilha o operador atual
        }
    }

    // Desempilha todos os operadores restantes
    while (p.topo != -1) {
        posfixa[j++] = desempilhar(&p);
    }

    posfixa[j] = '\0'; // Adiciona o terminador de string
}

int main() {
	  setlocale(LC_ALL, "");
	  
    char infixa[MAX], posfixa[MAX];

    printf("Digite a expressão infixa: ");
    fgets(infixa, sizeof(infixa), stdin);

    // Remove a nova linha do final da entrada, se existir
    size_t len = strlen(infixa);
    if (len > 0 && infixa[len - 1] == '\n') {
        infixa[len - 1] = '\0';
    }

    infixaParaPosfixa(infixa, posfixa);

    printf("Expressão pós-fixa: %s\n", posfixa);

    return 0;
}
