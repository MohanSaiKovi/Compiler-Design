#include <stdio.h>
#include <string.h>

int temp_count = 0;

char* generate_temp() {
    static char temp[3];
    snprintf(temp, sizeof(temp), "t%d", temp_count++);
    return temp;
}

void generate_3addr_code(char op, char* arg1, char* arg2, char* result) {
    printf("%s = %s %c %s\n", result, arg1, op, arg2);
}

int main() {
    char expression[100];
    printf("Enter an arithmetic expression: ");
    scanf("%s", expression);

    char* tokens = strtok(expression, "+-*/");
    char operators[50];
    char operands[50][10];
    int operator_count = 0;
    int operand_count = 0;

    while (tokens != NULL) {
        if (strchr("+-*/", tokens[0]) != NULL) {
            operators[operator_count++] = tokens[0];
        } else {
            strcpy(operands[operand_count++], tokens);
        }
        tokens = strtok(NULL, "+-*/");
    }

    char* temp1 = generate_temp();
    char* temp2 = generate_temp();

    generate_3addr_code(operators[0], operands[0], operands[1], temp1);
    for (int i = 1; i < operator_count; i++) {
        generate_3addr_code(operators[i], temp1, operands[i + 1], temp2);
        strcpy(temp1, temp2);
    }

    return 0;
}
