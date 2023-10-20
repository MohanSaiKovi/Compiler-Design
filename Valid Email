%{
#include<stdio.h>
%}
%%
[a-zA-Z0-9_]+(@[a-z]+)(.[a-z]+) {printf("%s is a valid email", yytext);}
.* {printf("It is not a valid email");}
%%
int main()
{
printf("\n Enter the input:");	
yylex();
}
int yywrap()
{
return 1;
}
