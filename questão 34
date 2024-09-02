#include <stdio.h>
#include <locale.h>
#include <stdlib.h>

//Nível 3: Algoritmos Avançados (31-50)

//Merge Sort: Implemente o algoritmo de ordenação Merge Sort.

// Função para mesclar duas sublistas ordenadas
void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1; // Tamanho da primeira sublista
    int n2 = r - m;     // Tamanho da segunda sublista

    // Criar arrays temporários
    int *L = (int *)malloc(n1 * sizeof(int));
    int *R = (int *)malloc(n2 * sizeof(int));

    // Verificar se a alocação de memória foi bem-sucedida
    if (L == NULL || R == NULL) {
        printf("Erro na alocação de memória.\n");
        exit(1);
    }

    // Copiar dados para os arrays temporários L[] e R[]
    for (int i = 0; i < n1; i++) L[i] = arr[l + i];
    for (int j = 0; j < n2; j++) R[j] = arr[m + 1 + j];

    // Mesclar os arrays temporários de volta no array original
    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k++] = L[i++];
        } else {
            arr[k++] = R[j++];
        }
    }

    // Copiar os elementos restantes de L[], se houver
    while (i < n1) arr[k++] = L[i++];

    // Copiar os elementos restantes de R[], se houver
    while (j < n2) arr[k++] = R[j++];

    // Liberar memória dos arrays temporários
    free(L);
    free(R);
}

// Função para implementar o Merge Sort
void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        // Encontrar o ponto médio
        int m = l + (r - l) / 2;

        // Ordenar as duas metades
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);

        // Mesclar as duas metades ordenadas
        merge(arr, l, m, r);
    }
}

// Função para imprimir o array
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int main() {
    int arr[] = {12, 11, 13, 5, 6, 7};
    int arr_size = sizeof(arr) / sizeof(arr[0]);

    printf("Array original:\n");
    printArray(arr, arr_size);

    mergeSort(arr, 0, arr_size - 1);

    printf("Array ordenado:\n");
    printArray(arr, arr_size);

    return 0;
}
