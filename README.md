# Desafio-Xadrez
trabalho da faculdade (ESTÁCIO)


#include <stdio.h>

#define TAMANHO 8

// Função para inicializar o tabuleiro com as peças iniciais do xadrez
void inicializarTabuleiro(char tabuleiro[TAMANHO][TAMANHO]) {
    char pecasIniciais[8] = {'T', 'C', 'B', 'D', 'R', 'B', 'C', 'T'}; // Torre, Cavalo, Bispo, Dama, Rei, etc.
    
    // Peças pretas
    for (int i = 0; i < TAMANHO; i++) {
        tabuleiro[0][i] = pecasIniciais[i];
        tabuleiro[1][i] = 'P'; // Peões
    }
    
    // Peças brancas
    for (int i = 0; i < TAMANHO; i++) {
        tabuleiro[6][i] = 'p'; // Peões
        tabuleiro[7][i] = pecasIniciais[i] + 32; // Letras minúsculas para as peças brancas
    }
    
    // Espaços vazios
    for (int i = 2; i < 6; i++) {
        for (int j = 0; j < TAMANHO; j++) {
            tabuleiro[i][j] = '.';
        }
    }
}

// Função para imprimir o tabuleiro
void imprimirTabuleiro(char tabuleiro[TAMANHO][TAMANHO]) {
    printf("  a b c d e f g h\n");
    for (int i = 0; i < TAMANHO; i++) {
        printf("%d ", 8 - i);
        for (int j = 0; j < TAMANHO; j++) {
            printf("%c ", tabuleiro[i][j]);
        }
        printf("\n");
    }
}

int main() {
    char tabuleiro[TAMANHO][TAMANHO];
    inicializarTabuleiro(tabuleiro);
    
    printf("Tabuleiro inicial do Xadrez:\n");
    imprimirTabuleiro(tabuleiro);
    
    return 0;
}
