#include <stdio.h> //biblioteca de comunicação com usúario
#include <stdlib.h> //biblioteca de alocação de espaço por memória 
#include <locale.h> //biblioteca de alocação de texto por região
#include <string.h> //biblioteca responsável por cuidar das string

int registro()
    {
    //inicio de criação das variavéis string	
     char arquivo[40];	
     char cpf[40];	
     char nome[40];
     char sobrenome[40];
	 char cargo[40];
	 //final da criação de variavéis string
	 
	 printf("Digite o cpf a ser cadastrado:");//coletando informação do usuário
	 scanf("%s", cpf);
	 
	 strcpy(arquivo, cpf); //reponsável por copiar os valores das string
	 
	 FILE *file;//cria o arquivo
	 file = fopen(arquivo,"w"); //cria o arquivo "w" siguinifica escrever
	 fprintf(file, cpf); //salvo o valor da variavél
	 fclose(file); //fecha o arquivo
	 
	 file = fopen(arquivo, "a");
	 fprintf(file,",");
	 fclose(file);
	 
	 printf("Digite o nome a ser cadastrado:");//coletanto informaçãoes do usário
	 scanf("%s",nome);//%s referi-se a string
	 
	 file = fopen(arquivo, "a");//responsável por copiar os valores das string
	 fprintf(file,nome);
	 fclose(file);
	 
	 file = fopen(arquivo, "a");
	 fprintf(file,",");
	 fclose(file);
	
	 printf("Digite o sobrenome a ser cadastrado:");
	 scanf("%s",sobrenome);
	
     file = fopen(arquivo, "a");
	 fprintf(file,sobrenome);
	 fclose(file);
	
	 file = fopen(arquivo, "a");
	 fprintf(file,",");
	 fclose(file);
	 
	 printf("Digite o cargo a ser cadastrado:");
	 scanf("%s",cargo);
	  
	 file = fopen(arquivo, "a");
	 fprintf(file,cargo);
	 fclose(file);
	 
	 system("pause");
     
	}
	
int consulta()
{
	setlocale(LC_ALL, "portuguese"); //Definindo a linguagem
	
	char cpf[40];
	char conteudo[200];
	
	printf("Digite o cpf a ser consultado:");
	scanf("%s", cpf);
	
	FILE *file;
	file = fopen(cpf,"r");
	
	if(file==NULL)
	{
		printf("Não foi possivel abrir o arquivo, não localizado!\n");
	}
	
	
	while(fgets(conteudo, 200, file) != NULL)
	{
		printf("\nEssas são as informações do usário:");
		printf("%s",conteudo);
		printf("\n\n");	
	}
	
	system("pause");
	}
	
int deletar()
{
    char cpf [40];
    printf("Digite o CPF do usuário a ser deletado:");
    scanf("$s", cpf);
    
    remove(cpf);
    
    FILE *file;
    file = fopen(cpf,"r");
    
    if(file == NULL)
    {
    printf("O usuário não se encontra no sistema! .\n");
    system("pause");
    
    
		
    	
    	
	}
    
    
    
    
	}
	
int main()
    {
    int opcao=0; //Definindo variavéis
	int laco=1;	
    	
	for(laco=1;laco=1;) 
	{
	
    system("cls");
	
	setlocale(LC_ALL, "portuguese"); //Definindo a linguagem
	    
	printf("### Cartório da EBAC ###\n\n"); //Início do menú
	printf("Escolha a opção desejada do menu\n\n"); 
	printf("\t1 - Registrar nomes\n");
	printf("\t2 - Consultar nomes\n");
	printf("\t3 - Deletar nomes\n");
	printf("\t4 - Sair do sistema\n\n");
	printf("Opção: "); //Fim do menu
	
	scanf("%d", &opcao); //armazenamento e a escolha do usuário
	
    system("cls");//responsável por limpar a tela
    
	switch(opcao)//inicio da seleção do menu
 	{
	
	case 1:
	registro();//chamadas de funções
	break;
	
	case 2:
	consulta();
	break;
	
	case 3:
	deletar();
	break;
	
	case 4:
	printf("Obrigado por utilizar o sistema!\n");
	return 0;
	break;	
	
	default:	
	printf("essa opção não está disponivel!\n");
	system("pause");
	break;
    }//fim da seleção		
   
	
}
}
