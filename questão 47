#include <stdio.h>
#include <locale.h>
#include <stdlib.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Algoritmo de Kruskal: Implemente o algoritmo de Kruskal para encontrar a árvore geradora mínima.

#define MAX 100 // Número máximo de arestas

// Estrutura para representar uma aresta
typedef struct {
    int origem, destino, peso;
} Aresta;

// Estrutura para representar um grafo
typedef struct {
    int V, E;
    Aresta arestas[MAX];
} Grafo;

// Estrutura para representar um subconjunto para o algoritmo de união-encontrar
typedef struct {
    int pai, rank;
} Subconjunto;

// Função para criar um novo grafo
Grafo* criarGrafo(int V, int E) {
    Grafo* grafo = (Grafo*)malloc(sizeof(Grafo));
    grafo->V = V;
    grafo->E = E;
    return grafo;
}

// Função para encontrar o conjunto a que um elemento pertence
int encontrar(Subconjunto subconjuntos[], int i) {
    if (subconjuntos[i].pai != i) {
        subconjuntos[i].pai = encontrar(subconjuntos, subconjuntos[i].pai);
    }
    return subconjuntos[i].pai;
}

// Função para unir dois subconjuntos
void unir(Subconjunto subconjuntos[], int x, int y) {
    int xroot = encontrar(subconjuntos, x);
    int yroot = encontrar(subconjuntos, y);

    if (subconjuntos[xroot].rank < subconjuntos[yroot].rank) {
        subconjuntos[xroot].pai = yroot;
    } else if (subconjuntos[xroot].rank > subconjuntos[yroot].rank) {
        subconjuntos[yroot].pai = xroot;
    } else {
        subconjuntos[yroot].pai = xroot;
        subconjuntos[xroot].rank++;
    }
}

// Função para comparar duas arestas com base no peso (para qsort)
int compararArestas(const void* a, const void* b) {
    return ((Aresta*)a)->peso - ((Aresta*)b)->peso;
}

// Função para encontrar a Árvore Geradora Mínima usando o algoritmo de Kruskal
void kruskal(Grafo* grafo) {
    int V = grafo->V;
    Aresta resultado[V];
    int e = 0; // Contador para o resultado
    int i = 0; // Contador para as arestas ordenadas

    // Passo 1: Ordenar todas as arestas em ordem crescente de peso
    qsort(grafo->arestas, grafo->E, sizeof(Aresta), compararArestas);

    // Criar V subconjuntos com um elemento cada
    Subconjunto subconjuntos[V];
    for (int v = 0; v < V; ++v) {
        subconjuntos[v].pai = v;
        subconjuntos[v].rank = 0;
    }

    // Processar as arestas ordenadas
    while (e < V - 1) {
        Aresta aresta = grafo->arestas[i++];
        int x = encontrar(subconjuntos, aresta.origem);
        int y = encontrar(subconjuntos, aresta.destino);

        // Se a aresta não criar um ciclo
        if (x != y) {
            resultado[e++] = aresta;
            unir(subconjuntos, x, y);
        }
    }

    // Imprimir a Árvore Geradora Mínima
    printf("Arestas da Árvore Geradora Mínima:\n");
    int custoTotal = 0;
    for (i = 0; i < e; ++i) {
        printf("%d -- %d: %d\n", resultado[i].origem, resultado[i].destino, resultado[i].peso);
        custoTotal += resultado[i].peso;
    }
    printf("Custo total da Árvore Geradora Mínima: %d\n", custoTotal);
}

int main() {
	   setlocale(LC_ALL, "");
	   
    int V = 4; // Número de vértices
    int E = 5; // Número de arestas

    Grafo* grafo = criarGrafo(V, E);

    // Adicionar arestas
    grafo->arestas[0] = (Aresta){0, 1, 10};
    grafo->arestas[1] = (Aresta){0, 2, 6};
    grafo->arestas[2] = (Aresta){0, 3, 5};
    grafo->arestas[3] = (Aresta){1, 3, 15};
    grafo->arestas[4] = (Aresta){2, 3, 4};

    // Encontrar a Árvore Geradora Mínima
    kruskal(grafo);

    // Liberar memória
    free(grafo);

    return 0;
}
