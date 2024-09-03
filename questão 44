#include <stdio.h>
#include <locale.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Caminho de um Cavalo no Xadrez: Simule os movimentos de um cavalo em um tabuleiro de xadrez.

#define N 8

// Função para verificar se a posição está dentro dos limites do tabuleiro
int ehValida(int x, int y) {
    return (x >= 0 && x < N && y >= 0 && y < N);
}

// Função para imprimir o tabuleiro
void imprimirTabuleiro(int tabuleiro[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", tabuleiro[i][j]);
        }
        printf("\n");
    }
}

// Função para simular os movimentos do cavalo
void movimentosCavalo(int x, int y) {
    // Movimentos possíveis do cavalo
    int movimentos[8][2] = {
        {2, 1}, {2, -1}, {-2, 1}, {-2, -1},
        {1, 2}, {1, -2}, {-1, 2}, {-1, -2}
    };

    // Cria um tabuleiro vazio
    int tabuleiro[N][N] = {0};

    // Marca a posição atual do cavalo
    tabuleiro[x][y] = 1;

    printf("Tabuleiro com a posição do cavalo e seus movimentos possíveis:\n");
    imprimirTabuleiro(tabuleiro);

    printf("Movimentos possíveis do cavalo a partir da posição (%d, %d):\n", x, y);
    for (int i = 0; i < 8; i++) {
        int novoX = x + movimentos[i][0];
        int novoY = y + movimentos[i][1];
        if (ehValida(novoX, novoY)) {
            printf("(%d, %d)\n", novoX, novoY);
        }
    }
}

int main() {
	  setlocale(LC_ALL, "");
	  
    int x, y;

    printf("Digite a posição inicial do cavalo (linha e coluna entre 0 e 7): ");
    scanf("%d %d", &x, &y);

    if (!ehValida(x, y)) {
        printf("Posição inválida. A posição deve estar entre 0 e 7.\n");
        return 1;
    }

    movimentosCavalo(x, y);

    return 0;
}
