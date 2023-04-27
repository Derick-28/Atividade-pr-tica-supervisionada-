# Atividade-pr-tica-supervisionada-

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

#define MAX 1000

/*
#####################################
ESTRUTURA DE DADOS I
STRUCTS

EVERTON - DEIMERSON - DERICK
#####################################
*/

typedef struct {
    char nome[50];
    char CNPJ[20];
    char email[50];
    char contato[15];
}FORNECEDOR;

typedef struct{
    FORNECEDOR fornecedor;

    char rua[20];
    char bairro[20];
    char numero[10];
    char cidade[20];
    char estado[10];
    char CEP[10];
}LOCACAO;

typedef struct{
    int ID;
    char descricao[MAX];
    char classe[MAX];
    char dados_adicionais[MAX];
    char responsavel[MAX];
    int dia, mes, ano;
}MATERIAL;

int main(){

    LOCACAO local;
    MATERIAL mat;

    int choice;

    printf("\n--------------FORNECEDORES E CADASTRO DE MATERIAIS--------------");

    printf("\n\nINFORMACOES PRINCIPAIS");
    //Nome FORNECEDOR
    printf("\nInforme o nome do fornecedor: ");
    fflush(stdin);
    fgets(local.fornecedor.nome, 50, stdin);
    //CNPJ
    printf("\nCNPJ: ");
    fflush(stdin);
    fgets(local.fornecedor.CNPJ, 20, stdin);
    //@ email
    printf("\nEmail: ");
    fflush(stdin);
    fgets(local.fornecedor.email, 50, stdin);
    //telefone para contato
    printf("\nDigite o telefone para contato: ");
    fflush(stdin);
    fgets(local.fornecedor.contato, 15, stdin);

    printf("\n\nINFORMACOES DE LOCALIDADE");
    //RUA
    printf("\nRUA: ");
    fflush(stdin);
    fgets(local.rua, 20, stdin);
    //BAIRRO
    printf("\nBAIRO: ");
    fflush(stdin);
    fgets(local.bairro, 20, stdin);
    //NUMERO
    printf("\nNUMERO: ");
    fflush(stdin);
    fgets(local.numero, 10, stdin);
    //CIDADE
    printf("\nCIDADE: ");
    fflush(stdin);
    fgets(local.cidade, 20, stdin);
    //ESTADO
    printf("\nESTADO: ");
    fflush(stdin);
    fgets(local.estado, 10, stdin);
    //CEP
    printf("\nCEP: ");
    fflush(stdin);
    fgets(local.CEP, 10, stdin);

    
    printf("\n\nDeseja efetuar um cadastro de material ?   1 - [SIM]  2 - [NAO]");
    scanf("%d", &choice);

    if(choice == 1){
        printf("INFORMACOES DO MATERIAL");
        //ID
        printf("\nEXEMPLO: 1234");
        printf("\nID: ");
        scanf("%d", &mat.ID);
        //DESCRICAO
        printf("\nDESCRICAO: ");
        fflush(stdin);
        fgets(mat.descricao, MAX, stdin);
        //CLASSE
        printf("EXEMPLO: NOTEBOOK ---- DESKTOP ---- BIOS ----");
        printf("\nCLASSE: ");
        fflush(stdin);
        fgets(mat.classe, 20, stdin);
        //DADOS ADICIONAIS
        printf("\nDADOS ADICIONAIS: ");
        fflush(stdin);
        fgets(mat.dados_adicionais, MAX, stdin);
        //RESPONSAVEL
        printf("\nRESPONSAVEL: ");
        fflush(stdin);
        fgets(mat.responsavel, 20, stdin);
        //DATA
        printf("\nINFORME A DATA PADRAO dd mm aaaa: ");
        printf("\nDIA: ");
        scanf("%d", &mat.dia);
        printf("\nMES: ");
        scanf("%d", &mat.mes);
        printf("\nANO: ");
        scanf("%d", &mat.ano);
    }
    else{
        printf("\nadastro realizado com sucesso.");
    }

    printf("\nFIM DA COLETA DE DADOS.");

    printf("\nDADOS CADASTRADOS: ");
    printf("\n------------------------------------------------------------------");
    printf("\nFORNECEDOR");
    printf("\n\nNOME: %s", local.fornecedor.nome);
    printf("\nCNPJ: %s", local.fornecedor.CNPJ);
    printf("\nEMAIL: %s", local.fornecedor.email);
    printf("\nTELEFONE: %s", local.fornecedor.contato);
    printf("\nRUA: %s", local.rua);
    printf("\nBAIRRO: %s", local.bairro);
    printf("\nNUMERO: %s", local.numero);
    printf("\nCIDADE: %s", local.cidade);
    printf("\nESTADO: %s", local.estado);
    printf("\nCEP: %s", local.CEP);

    if(choice == 1){
        printf("\n------------------------------------------------------------------");
        printf("\n\nMATERIAL");
        printf("\nID: %s", mat.ID);
        printf("\nDESCRICAO: %s", mat.descricao);
        printf("\nCLASSE: %s", mat.classe);
        printf("\nDADOS ADICIONAIS: %s", mat.dados_adicionais);
        printf("DATA: %d/%d/%d ", mat.dia, mat.mes, mat.ano);
    }
    else printf("\n------------------------------------------------------------------\n");

    return 0;
}
