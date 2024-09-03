#include <stdio.h>
#include <locale.h>
#include <stdbool.h>

//Nível 3: Algoritmos Avançados (31-50)

//Implementar uma Fila: Implemente uma fila usando um vetor

#define MAX 100 // Define o tamanho máximo da fila

typedef struct {
    int itens[MAX];
    int frente, tras;
    int tamanho;
} Fila;

// Função para inicializar a fila
void inicializarFila(Fila* f) {
    f->frente = 0;
    f->tras = -1;
    f->tamanho = 0;
}

// Verifica se a fila está vazia
bool estaVazia(Fila* f) {
    return f->tamanho == 0;
}

// Verifica se a fila está cheia
bool estaCheia(Fila* f) {
    return f->tamanho == MAX;
}

// Adiciona um item à fila
void enfileirar(Fila* f, int item) {
    if (estaCheia(f)) {
        printf("Fila cheia!\n");
        return;
    }
    f->tras = (f->tras + 1) % MAX;
    f->itens[f->tras] = item;
    f->tamanho++;
}

// Remove um item da fila
int desenfileirar(Fila* f) {
    if (estaVazia(f)) {
        printf("Fila vazia!\n");
        return -1; // Valor de erro indicando que a fila está vazia
    }
    int item = f->itens[f->frente];
    f->frente = (f->frente + 1) % MAX;
    f->tamanho--;
    return item;
}

// Função para exibir o conteúdo da fila
void exibirFila(Fila* f) {
    if (estaVazia(f)) {
        printf("Fila vazia!\n");
        return;
    }
    printf("Conteúdo da fila: ");
    for (int i = 0; i < f->tamanho; i++) {
        int index = (f->frente + i) % MAX;
        printf("%d ", f->itens[index]);
    }
    printf("\n");
}

int main() {
	 setlocale(LC_ALL, "");
	 
    Fila f;
    inicializarFila(&f);

    enfileirar(&f, 10);
    enfileirar(&f, 20);
    enfileirar(&f, 30);

    exibirFila(&f);

    printf("Desenfileirado: %d\n", desenfileirar(&f));
    exibirFila(&f);

    return 0;
}
