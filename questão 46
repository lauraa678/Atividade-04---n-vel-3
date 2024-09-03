#include <stdio.h>
#include <locale.h>
#include <stdbool.h>
#include <limits.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Algoritmo de Dijkstra: Implemente o algoritmo de Dijkstra para encontrar o caminho mais curto em um grafo. 

#define V 9 

// Função para encontrar o vértice com a menor distância
int minDistancia(int dist[], int sptSet[]) {
    int min = INT_MAX, min_index;

    for (int v = 0; v < V; v++) {
        if (sptSet[v] == 0 && dist[v] <= min) {
            min = dist[v];
            min_index = v;
        }
    }

    return min_index;
}

// Função para imprimir o vetor de distâncias
void imprimirDistancias(int dist[], int n) {
    printf("Vértice \t Distância da Fonte\n");
    for (int i = 0; i < n; i++) {
        printf("%d \t\t %d\n", i, dist[i]);
    }
}

// Implementação do algoritmo de Dijkstra
void dijkstra(int grafo[V][V], int origem) {
    int dist[V];
    int sptSet[V]; // Conjunto de vértices para os quais o menor caminho é conhecido

    // Inicializa as distâncias com infinito e o conjunto de vértices com falso
    for (int i = 0; i < V; i++) {
        dist[i] = INT_MAX;
        sptSet[i] = 0;
    }

    // A distância do vértice de origem para ele mesmo é 0
    dist[origem] = 0;

    // Calcula a distância mais curta para todos os vértices
    for (int count = 0; count < V - 1; count++) {
        int u = minDistancia(dist, sptSet);

        sptSet[u] = 1;

        for (int v = 0; v < V; v++) {
            if (!sptSet[v] && grafo[u][v] && dist[u] != INT_MAX &&
                dist[u] + grafo[u][v] < dist[v]) {
                dist[v] = dist[u] + grafo[u][v];
            }
        }
    }

    imprimirDistancias(dist, V);
}

int main() {
	    setlocale(LC_ALL, "");
	    
    // Matriz de adjacência representando o grafo
    int grafo[V][V] = {
        {0, 4, 0, 0, 0, 0, 0, 8, 0},
        {4, 0, 8, 0, 0, 0, 0, 11, 0},
        {0, 8, 0, 7, 0, 4, 0, 0, 2},
        {0, 0, 7, 0, 9, 14, 0, 0, 0},
        {0, 0, 0, 9, 0, 10, 0, 0, 0},
        {0, 0, 4, 14, 10, 0, 2, 0, 0},
        {0, 0, 0, 0, 0, 2, 0, 1, 6},
        {8, 11, 0, 0, 0, 0, 1, 0, 7},
        {0, 0, 2, 0, 0, 0, 6, 7, 0}
    };

    int origem = 0; // Vértice de origem

    dijkstra(grafo, origem);

    return 0;
}
