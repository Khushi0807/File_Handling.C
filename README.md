# File_Handling.C

#include<stdio.h>
#include<conio.h>
main()
{


FILE *S,*D;                                                 
char c;
int i=0,count;
S= fopen("first.txt","w");
D= fopen("Second.txt","w");
fprintf(S,"My captain \n");


fclose(S);
fclose(D);

S = fopen("first.txt","a+");                                     //reverse the file
fseek(S,0,SEEK_END);
count = ftell(S);
while(i< count)
{
i++;
fseek(S,-i,SEEK_END);
printf("%c",fgetc(S));

}
fprintf(S ,"%s");

fclose(S);


S = fopen("first.txt" , "r");                                          //to copy the content of the file from one file to anther
D = fopen("second.txt", "w");


if(S == NULL || D == NULL)
{
	printf("\nPlease check if file exist or not");
	
}

while ( (c = fgetc(S))!= EOF)
{
	fputc(c,D);
	c =fgetc(S);
}
fclose(S);
fclose(D);

}
