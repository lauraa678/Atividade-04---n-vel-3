#include <locale.h>
#include <stdio.h>
#include <ctype.h>  
#include <string.h> 

//Nível 3: Algoritmos Avançados (31-50)

//Cifra de César: Implemente a Cifra de César para criptografia de mensagens.

#define ALFABETO_SIZE 26

void criptografar(char *mensagem, int deslocamento) {
    while (*mensagem) {
        if (isalpha(*mensagem)) {
            char base = isupper(*mensagem) ? 'A' : 'a';
            *mensagem = ((toupper(*mensagem) - base + deslocamento) % ALFABETO_SIZE + ALFABETO_SIZE) % ALFABETO_SIZE + base;
        }
        mensagem++;
    }
}

void descriptografar(char *mensagem, int deslocamento) {
    criptografar(mensagem, -deslocamento);
}

int main() {
	  setlocale(LC_ALL, "");
	  
    char mensagem[256];
    int deslocamento;
    int opcao;

    // Leitura da mensagem
    printf("Digite a mensagem (max 255 caracteres): ");
    fgets(mensagem, sizeof(mensagem), stdin);

    // Remove o caractere de nova linha no final da mensagem, se presente
    char *newline = strchr(mensagem, '\n');
    if (newline) *newline = '\0';

    // Leitura do deslocamento
    printf("Digite o deslocamento (número inteiro): ");
    scanf("%d", &deslocamento);

    // Menu de opções
    printf("Escolha uma opção:\n");
    printf("1. Criptografar\n");
    printf("2. Descriptografar\n");
    printf("Digite sua opção: ");
    scanf("%d", &opcao);

    // Processamento baseado na opção escolhida
    switch (opcao) {
        case 1:
            criptografar(mensagem, deslocamento);
            printf("Mensagem criptografada: %s\n", mensagem);
            break;
        case 2:
            descriptografar(mensagem, deslocamento);
            printf("Mensagem descriptografada: %s\n", mensagem);
            break;
        default:
            printf("Opção inválida.\n");
            break;
    }

    return 0;
}
