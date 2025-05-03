#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0, isNumber = 1;

    printf("Enter input: ");
    scanf("%s", str);

    if (str[0] == '0' && str[1] == '\0') {
        printf("Zero\n");
    }
    else if (str[0] == '-' && isdigit(str[1])) {
        for (i = 1; str[i]; i++)
            if (!isdigit(str[i])) isNumber = 0;

        if (isNumber) printf("Negative number\n");
        else printf("Invalid identifier\n");
    }
    else if (isdigit(str[0])) {
        for (i = 0; str[i]; i++)
            if (!isdigit(str[i])) isNumber = 0;

        if (isNumber) printf("Integer number\n");
        else printf("Invalid identifier\n");
    }
    else if (isalpha(str[0]) || str[0] == '_') {
        for (i = 1; str[i]; i++)
            if (!(isalnum(str[i]) || str[i] == '_')) {
                printf("Invalid identifier\n");
                return 0;
            }
        printf("Valid identifier\n");
    }
    else {
        printf("Invalid identifier\n");
    }

    return 0;
}
