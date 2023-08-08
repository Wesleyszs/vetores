#include <iostream>
#include <stdlib.h>
#include <time.h>
using namespace std;

void popularVetor(int vetor[], int tamanho) {
    srand(time(0));

    for (int i = 0; i < tamanho; ++i) {
        vetor[i] = rand() % 100; 
    }
}

void Desconto10(int vetor[], int tamanho) {
    for (int i = 0; i < tamanho; ++i) {
        vetor[i] -= (vetor[i] * 10)/100; 
    }
}

void Desconto50(int vetor[], int tamanho) {
    for (int i = 0; i < tamanho; ++i) {
        vetor[i] = (vetor[i] * 50 ) / 100; 
    }
}

void imprimirVetor(int vetor[], int tamanho) {					
    for (int i = 0; i < tamanho; ++i) {
        cout << vetor[i] << " ";
    }
    cout << endl;
}

int main() {
    const int tamanhoVetor = 10;
    int vetor[tamanhoVetor];

    int opcao;

    do {
        cout << "------ MENU ------" << endl;
        cout << "1 - POPULAR O VETOR COM NUMEROS ALEATORIOS" << endl;
        cout << "2 - APLICAR DESCONTO DE 10%" << endl;
        cout << "3 - APLICAR DESCONTO DE 50%" << endl;
        cout << "4 - IMPRIMIR OS VALORES DO VETOR" << endl;
        cout << "5 - SAIR" << endl;
        cout << "Escolha uma Opcao: ";
        cin >> opcao;

        switch (opcao) {
            case 1:
                popularVetor(vetor, tamanhoVetor);
                cout << "Vetor populado com sucesso." << endl;
                break;
            case 2:
                Desconto10(vetor, tamanhoVetor);
                cout << "Desconto de 10% aplicado." << endl;
                break;
            case 3:
                Desconto50(vetor, tamanhoVetor);
                cout << "Desconto de 50% aplicado." << endl;
                break;
            case 4:
                cout << "Valores do vetor: ";
                imprimirVetor(vetor, tamanhoVetor);
                break;
            case 5:
                cout << "Saindo do programa..." << endl;
                break;
            default:
                cout << "saindo do programa " << endl;
        }
		
        cout << endl;

    } while (opcao != 5);
											
    return 0;
}				
																														
