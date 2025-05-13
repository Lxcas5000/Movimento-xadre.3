#include <stdio.h>

// === Função recursiva para movimento da Torre ===
void moverTorreRecursivo(int passosRestantes) {
    if (passosRestantes <= 0) return;
    printf("Direita\n");
    moverTorreRecursivo(passosRestantes - 1);
}

// === Função recursiva para movimento da Rainha ===
void moverRainhaRecursivo(int passosRestantes) {
    if (passosRestantes <= 0) return;
    printf("Esquerda\n");
    moverRainhaRecursivo(passosRestantes - 1);
}

// === Função recursiva para controle geral do Bispo ===
void moverBispoRecursivo(int passosVerticais, int passosHorizontais) {
    if (passosVerticais <= 0) return;

    // Loop aninhado: cada linha simula um "nível" vertical
    printf("Passo diagonal:\n");
    for (int h = 0; h < passosHorizontais; h++) {
        printf("Cima Direita\n");
    }

    moverBispoRecursivo(passosVerticais - 1, passosHorizontais);
}

// === Função para movimento complexo do Cavalo ===
void moverCavaloL() {
    // Cavalo: 2 casas para cima e 1 para direita
    // Usaremos dois loops aninhados com múltiplas variáveis e controle de fluxo

    int cima = 0, direita = 0;
    int limiteCima = 2;
    int limiteDireita = 1;

    printf("Movimento do Cavalo:\n");

    for (cima = 1; cima <= limiteCima; cima++) {
        if (cima == 2) {
            // Quando atingir duas casas para cima, entrar no segundo movimento
            int i = 0;
            while (i < limiteDireita) {
                printf("Direita\n");
                i++;
            }
        }
        printf("Cima\n");
    }
}

int main() {
    // === Movimento da Torre ===
    printf("Movimento da Torre:\n");
    moverTorreRecursivo(5);  // 5 casas para a direita

    printf("\n");

    // === Movimento do Bispo ===
    printf("Movimento do Bispo:\n");
    moverBispoRecursivo(5, 1);  // 5 movimentos diagonais (1 horizontal por vertical)

    printf("\n");

    // === Movimento da Rainha ===
    printf("Movimento da Rainha:\n");
    moverRainhaRecursivo(8);  // 8 casas para a esquerda

    printf("\n");

    // === Movimento do Cavalo ===
    moverCavaloL();  // 2 para cima e 1 para direita (movimento em "L")

    return 0;
}
