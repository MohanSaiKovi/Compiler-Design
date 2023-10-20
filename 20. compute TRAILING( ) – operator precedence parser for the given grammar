#include <stdio.h>
#include <string.h>

#define MAX_RULES 6

char productions[MAX_RULES][10] = {
    "E->E+T",
    "E->T",
    "T->T*F",
    "T->F",
    "F->(E)",
    "F->i"
};

char leading[6][10] = {};

void add_to_set(char set[], char element) {
    if (strchr(set, element) == NULL) {
        strcat(set, &element);
    }
}

void compute_leading(int index) {
    char rule[10];
    strcpy(rule, productions[index]);

    char non_terminal = rule[0];
    char beta[10];

    int i, j;
    for (i = 3, j = 0; rule[i] != '\0'; i++, j++) {
        beta[j] = rule[i];
    }
    beta[j] = '\0';

    if (strchr("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ", beta[0])) {
        add_to_set(leading[index], beta[0]);
    }

    if (strchr("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ", beta[0]) && strlen(beta) > 1) {
        add_to_set(leading[index], beta[1]);
    }

    if (strchr("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ", beta[0]) && strchr("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ", beta[1])) {
        add_to_set(leading[index], beta[2]);
    }
}

int main() {
    int i;
    for (i = 0; i < 6; i++) {
        compute_leading(i);
        printf("LEADING(%c): {%s}\n", productions[i][0], leading[i]);
    }

    return 0;
}
