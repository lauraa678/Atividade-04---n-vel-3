#include <stdio.h>
#include <locale.h>
#include <stdbool.h>

//Nível 3: Algoritmos Avançados (31-50) 

//Solucionador de Sudoku: Implemente um solucionador de Sudoku. 

#define N 9

// Função para imprimir o tabuleiro de Sudoku
void imprimirTabuleiro(int tabuleiro[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", tabuleiro[i][j]);
        }
        printf("\n");
    }
}

// Função para verificar se o número pode ser colocado na posição (linha, coluna)
bool podeColocar(int tabuleiro[N][N], int linha, int coluna, int num) {
    // Verifica se o número já está na linha
    for (int x = 0; x < N; x++) {
        if (tabuleiro[linha][x] == num) {
            return false;
        }
    }

    // Verifica se o número já está na coluna
    for (int x = 0; x < N; x++) {
        if (tabuleiro[x][coluna] == num) {
            return false;
        }
    }

    // Verifica se o número já está na subgrade 3x3
    int inicioLinha = linha - linha % 3;
    int inicioColuna = coluna - coluna % 3;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (tabuleiro[i + inicioLinha][j + inicioColuna] == num) {
                return false;
            }
        }
    }

    return true;
}

// Função para resolver o Sudoku usando backtracking
bool resolverSudoku(int tabuleiro[N][N]) {
    int linha, coluna;
    bool vazio = false;

    // Encontra uma célula vazia
    for (linha = 0; linha < N; linha++) {
        for (coluna = 0; coluna < N; coluna++) {
            if (tabuleiro[linha][coluna] == 0) {
                vazio = true;
                break;
            }
        }
        if (vazio) {
            break;
        }
    }

    // Se não há células vazias, o Sudoku está resolvido
    if (!vazio) {
        return true;
    }

    // Tenta colocar números de 1 a 9 na célula vazia
    for (int num = 1; num <= 9; num++) {
        if (podeColocar(tabuleiro, linha, coluna, num)) {
            tabuleiro[linha][coluna] = num;

            // Recursivamente tenta resolver o Sudoku
            if (resolverSudoku(tabuleiro)) {
                return true;
            }

            // Se o número não leva a uma solução, desfaz a colocação
            tabuleiro[linha][coluna] = 0;
        }
    }

    return false;
}

int main() {
	    setlocale(LC_ALL, "");
	    
    // Exemplo de tabuleiro de Sudoku (0 representa células vazias)
    int tabuleiro[N][N] = {
        {5, 3, 0, 0, 7, 0, 0, 0, 0},
        {6, 0, 0, 1, 9, 5, 0, 0, 0},
        {0, 9, 8, 0, 0, 0, 0, 6, 0},
        {8, 0, 0, 0, 6, 0, 0, 0, 3},
        {4, 0, 0, 8, 0, 3, 0, 0, 1},
        {7, 0, 0, 0, 2, 0, 0, 0, 6},
        {0, 6, 0, 0, 0, 0, 2, 8, 0},
        {0, 0, 0, 4, 1, 9, 0, 0, 5},
        {0, 0, 0, 0, 8, 0, 0, 7, 9}
    };

    if (resolverSudoku(tabuleiro)) {
        printf("Sudoku resolvido:\n");
        imprimirTabuleiro(tabuleiro);
    } else {
        printf("Não foi possível resolver o Sudoku.\n");
    }

    return 0;
}
