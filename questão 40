#include <locale.h>
#include <stdio.h>

//Nível 3: Algoritmos Avançados (31-50)

//Jogo da Velha: Implemente o jogo da velha para dois jogadores.

#define TAM 3

void inicializarTabuleiro(char tabuleiro[TAM][TAM]) {
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            tabuleiro[i][j] = ' ';
        }
    }
}

void imprimirTabuleiro(char tabuleiro[TAM][TAM]) {
    printf("\n");
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            printf(" %c ", tabuleiro[i][j]);
            if (j < TAM - 1) printf("|");
        }
        printf("\n");
        if (i < TAM - 1) {
            for (int j = 0; j < TAM; j++) {
                printf("---");
                if (j < TAM - 1) printf("+");
            }
            printf("\n");
        }
    }
    printf("\n");
}

int verificarVitoria(char tabuleiro[TAM][TAM], char jogador) {
    // Verifica linhas e colunas
    for (int i = 0; i < TAM; i++) {
        if ((tabuleiro[i][0] == jogador && tabuleiro[i][1] == jogador && tabuleiro[i][2] == jogador) ||
            (tabuleiro[0][i] == jogador && tabuleiro[1][i] == jogador && tabuleiro[2][i] == jogador)) {
            return 1;
        }
    }

    // Verifica diagonais
    if ((tabuleiro[0][0] == jogador && tabuleiro[1][1] == jogador && tabuleiro[2][2] == jogador) ||
        (tabuleiro[0][2] == jogador && tabuleiro[1][1] == jogador && tabuleiro[2][0] == jogador)) {
        return 1;
    }

    return 0;
}

int verificarEmpate(char tabuleiro[TAM][TAM]) {
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            if (tabuleiro[i][j] == ' ') {
                return 0; // Ainda há jogadas disponíveis
            }
        }
    }
    return 1; // Sem jogadas disponíveis
}

int main() {
	  setlocale(LC_ALL, "");
	  
    char tabuleiro[TAM][TAM];
    int linha, coluna;
    char jogadorAtual = 'X';
    int jogoAtivo = 1;

    inicializarTabuleiro(tabuleiro);

    while (jogoAtivo) {
        imprimirTabuleiro(tabuleiro);

        printf("Jogador %c, insira a linha (0, 1, 2) e a coluna (0, 1, 2): ", jogadorAtual);
        scanf("%d %d", &linha, &coluna);

        if (linha < 0 || linha >= TAM || coluna < 0 || coluna >= TAM || tabuleiro[linha][coluna] != ' ') {
            printf("Movimento inválido. Tente novamente.\n");
            continue;
        }

        tabuleiro[linha][coluna] = jogadorAtual;

        if (verificarVitoria(tabuleiro, jogadorAtual)) {
            imprimirTabuleiro(tabuleiro);
            printf("Jogador %c venceu!\n", jogadorAtual);
            jogoAtivo = 0;
        } else if (verificarEmpate(tabuleiro)) {
            imprimirTabuleiro(tabuleiro);
            printf("Deu Velha!\n");
            jogoAtivo = 0;
        } else {
            jogadorAtual = (jogadorAtual == 'X') ? 'O' : 'X'; // Alterna entre 'X' e 'O'
        }
    }

    return 0;
}
