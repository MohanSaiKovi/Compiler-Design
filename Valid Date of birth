%{
#include<stdio.h>
%}

%% 

[0-9][0-9]\/[0-1][0-9]\/[1-2][0-9]{3} {printf("%s, is a Valid DOB", yytext);}
.+ {printf("DOB is Invalid");}
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
