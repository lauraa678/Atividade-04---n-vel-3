#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

#define MAX 100 // Tamanho máximo da pilha

//Nível 3: Algoritmos Avançados (31-50)

//Implementar uma Pilha: Implemente uma pilha usando um vetor.

// Estrutura para a pilha
typedef struct {
    int top;
    int data[MAX];
} Stack;

// Função para inicializar a pilha
void initStack(Stack *s) {
    s->top = -1; // Pilha vazia
}

// Função para verificar se a pilha está cheia
int isFull(Stack *s) {
    return s->top == MAX - 1;
}

// Função para verificar se a pilha está vazia
int isEmpty(Stack *s) {
    return s->top == -1;
}

// Função para adicionar um elemento à pilha
void push(Stack *s, int value) {
    if (isFull(s)) {
        printf("Pilha cheia!\n");
        return;
    }
    s->data[++(s->top)] = value;
    printf("%d inserido na pilha.\n", value);
}

// Função para remover um elemento da pilha
int pop(Stack *s) {
    if (isEmpty(s)) {
        printf("Pilha vazia!\n");
        return -1; // Retorna -1 se a pilha estiver vazia
    }
    return s->data[(s->top)--];
}

// Função para obter o topo da pilha sem remover
int peek(Stack *s) {
    if (isEmpty(s)) {
        printf("Pilha vazia!\n");
        return -1; // Retorna -1 se a pilha estiver vazia
    }
    return s->data[s->top];
}

// Função para imprimir a pilha
void printStack(Stack *s) {
    if (isEmpty(s)) {
        printf("Pilha vazia!\n");
        return;
    }
    printf("Elementos na pilha: ");
    for (int i = s->top; i >= 0; i--) {
        printf("%d ", s->data[i]);
    }
    printf("\n");
}

int main() {
    Stack s;
    initStack(&s);

    push(&s, 10);
    push(&s, 20);
    push(&s, 30);

    printf("Topo da pilha: %d\n", peek(&s));

    printStack(&s);

    printf("%d removido da pilha.\n", pop(&s));
    printf("%d removido da pilha.\n", pop(&s));
    printf("%d removido da pilha.\n", pop(&s));

    printStack(&s);

    return 0;
}
