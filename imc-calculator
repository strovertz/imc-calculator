#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
#include <string.h>

#define TAM 25


/*

    GLEISON ANTONIO PIRES DA SILVA, SISTEMAS DE INFORMAÃ‡ÃƒO 2021.2 - 202120065
    LAB2.2022.1

*/

// o Magreza, quando o resultado do IMC Ã© menor que 18,5 kg/m2;
// o Normal, quando o resultado do IMC estÃ¡ entre 18,5 e 24,9 kg/m2;
// o Sobrepeso, quando o resultado do IMC estÃ¡ entre 24,9 e 30 kg/m2;
// o Obesidade, quando o resultado do IMC Ã© maior que 30 kg/m2.

typedef struct {
    int cod; // ï‚· cÃ³digo: nÃºmero inteiro (entrada do usuÃ¡rio);
    char nome[81]; // ï‚· nome: cadeia de caracteres (entrada do usuÃ¡rio);
    float peso; // ï‚· peso em quilos: nÃºmero real (entrada do usuÃ¡rio);
    int altura; // ï‚· altura em centÃ­metros: nÃºmero inteiro (entrada do usuÃ¡rio);
    float imc; // ï‚· IMC (Ã­ndice de massa corporal): nÃºmero real (calculado pelo programa);
    char faixa[15]; // Faixa: cadeia de caracteres. A faixa deve ser preenchida pelo programa, com base nos seguintes valores:
} pessoa_p;

void dados (pessoa_p* Pessoa, int i)
{
    for (int x = 0; x < i; x++)
    {
        printf("Pessoa: %x\n", x+1);
        printf ("COD: %d \n", Pessoa[x].cod);
        printf ("NOME: %s \n", Pessoa[x].nome); 
        printf ("PESO: %.1f Kg\n", Pessoa[x].peso);
        printf ("ALTURA: %d Cm\n", Pessoa[x].altura); 
        printf ("IMC: %f\n", Pessoa[x].imc);
        printf ("FAIXA: %s\n", Pessoa[x].faixa);
        printf ("\n \n");
    }
}
void Sobrepeso (pessoa_p* Pessoa, int i)
{
    printf ("Nome dos usuarios com sobrepeso: \n");
    for (int x = 0; x < i; x++)
    {
        if (!strcmp(Pessoa[x].faixa, "Sobrepeso"))
        {
            printf("%s\n", Pessoa[x].nome);
        }
    }
}

void Obesidade (pessoa_p* Pessoa, int i)
{
    printf ("Nome dos usuarios com Obesidade: \n");
    for (int x = 0; x < i; x++)
    {
        if (!strcmp(Pessoa[x].faixa, "Obesidade"))
        {
            printf("%s\n", Pessoa[x].nome);
        }
    }
    printf("\n");
}
float valor_pesos_media (pessoa_p* Pessoa, int i, float peso_m)
{
    printf ("Valor medio dos pesos: \n");
    float peso_t = 0;
    for (int x = 0; x < i; x++)
    {
        peso_t = peso_t + Pessoa[x].peso;
    }
    peso_m = (peso_t / i);
    return peso_m;
}

void peso_acima_media_p(pessoa_p* Pessoa, int i, float peso_m)
{
    int acima_media = 0;

    for (int x=0; x < i; x++)
    {
        if (Pessoa[x].peso > peso_m)
        {
            acima_media++;
        }
    }
    printf("Pessoas acima do peso medio: %d\n", acima_media);
}

void not_faixa_normal(pessoa_p* Pessoa, int i)
{
    int off_faixa_normal = 0;

    for (int x = 0; x < i; x++)
    {
        if(Pessoa[x].peso > 24.9 || Pessoa[x].peso < 18.5)
        {
            off_faixa_normal++;
        } else continue;
    }
    printf("%d Pessoas nÃ£o estÃ£o na faixa normal de peso.\n", off_faixa_normal);
}

void normal_e_menor_media(pessoa_p* Pessoa, int i, float peso_m)
{
    printf("Pessoas com peso normal e menor que a mÃ©dia dos pesos: \n");
    for (int x = 0; x < i; x++)
    {
        if (strcmp(Pessoa[x].faixa, "Normal"))
        {
            if(Pessoa[x].peso < peso_m) printf("%s\n", Pessoa[x].nome);
        }
    }
}

void pessoa_maior_imc(pessoa_p* Pessoa, int i)
{
    printf("Nome da(s) pessoa(s) com o(s) maior(es) IMC(s): \n");
    float stimc = 0;
    char nome[30];
    int x = 0;
    stimc = Pessoa[x].imc;

    for (x = 0; x < i-1; x++)
    {
        if (stimc < Pessoa[x+1].imc)
        {
            stimc = Pessoa[x+1].imc;
        }
    }
    for (x=0; x < i; x++)
    {
        if (Pessoa[x].imc == stimc)
        {
            printf("%s\n", Pessoa[x].nome);
        }
    }
}
void pessoa_menor_imc(pessoa_p* Pessoa, int i)
{
    printf("Nome da(s) pessoa(s) com o(s) menor(es) IMC(s): \n");
    float stimc = 0;
    char nome[30];
    int x = 0;
    stimc = Pessoa[x].imc;
    for (x = 0; x < i-1; x++)
    {
        if (stimc > Pessoa[x+1].imc)
        {
            stimc = Pessoa[x+1].imc;
        }
    }
    for (x=0; x < i; x++)
    {
        if (Pessoa[x].imc == stimc)
        {
            printf("%s\n", Pessoa[x].nome);
        }
    }
}

void preenche (pessoa_p* Pessoa, int i, int cod, char* nome, float peso, int altura)
{
    Pessoa[i].cod = cod;
    strcpy (Pessoa[i].nome, nome);
    Pessoa[i].peso = peso;
    Pessoa[i].altura = altura;

    float altura_comma = (float)altura / 100;

    Pessoa[i].imc = peso / (altura_comma * altura_comma);
    float imc;
    imc = Pessoa[i].imc;
    
    if (imc < 18.5) strcpy (Pessoa[i].faixa, "Magreza");
    else if (imc > 18.5 && imc < 24.9) strcpy (Pessoa[i].faixa, "Normal");
    else if (imc > 24.9 && imc < 30) strcpy (Pessoa[i].faixa, "Sobrepeso");
    else if(imc > 30)strcpy (Pessoa[i].faixa, "Obesidade");
    else printf("#Error#");

    printf ("COD: %d \n", Pessoa[i].cod);
    printf ("NOME: %s \n", Pessoa[i].nome); 
    printf ("PESO: %.1f Kg\n", Pessoa[i].peso);
    printf ("ALTURA: %.2f M\n", altura_comma);   
    
}

int main (void)
{
    pessoa_p Pessoa[TAM];
    int cod;
    char nome[81];
    float peso;
    int altura;
    float imc;
    int i=0;
    int x=0;
    float peso_m = 0;

    while(true)
    {

    printf ("Insira nos proximos campos os seus dados, COD Identificador, Nome, Peso (KG), Altura (CM):  ");

    scanf ("%d", &cod);
    scanf ("%s", nome);
    scanf ("%f", &peso);
    scanf ("%d", &altura);
    printf("\n");
    
    preenche (Pessoa, i, cod, nome, peso, altura);

    printf("\n deseja prosseguir? 1 - SIM, 2 - NAO:  ");
    printf("\n");
    scanf("%d", &x);
    printf("\n"); 

    if (x == 2)
    {
        break;
    }
    i++;
    }

    dados (Pessoa, i);
    printf ("\n \n");
    Sobrepeso (Pessoa, i);
    printf("\n \n");
    Obesidade (Pessoa, i);
    printf("\n");
    peso_m = valor_pesos_media(Pessoa, i, peso_m);
    printf("%.2f\n", peso_m);
    printf("\n");
    peso_acima_media_p(Pessoa, i, peso_m);
    printf("\n \n");
    not_faixa_normal(Pessoa, i);
    printf("\n \n");
    normal_e_menor_media(Pessoa, i, peso_m);
    printf("\n \n");
    pessoa_maior_imc(Pessoa, i);
    printf("\n \n");
    pessoa_menor_imc(Pessoa, i);

    return 0;
}
