%{
int positive_no = 0, negative_no = 0;
%}
%%
[-][0-9]+ {negative_no++;
            printf("negative number = %s\n", yytext);}

[0-9]+ {positive_no++;
        printf("positive number = %s\n", yytext);}    
.|\n  /* Ignore any other characters or newlines */
%%
int yywrap(){}
int main()                                          
{
    yylex();
    printf("number of positive numbers = %d\n",positive_no);
    printf("number of negative numbers = %d\n",negative_no);
    return 0;
}
