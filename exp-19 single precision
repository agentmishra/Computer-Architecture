#include <stdio.h>
#include <stdint.h>

void printBinary(uint32_t num) {
    for (int i = 31; i >= 0; i--) {
        printf("%d", (num >> i) & 1);
        if (i == 31 || i == 23) 
            printf(" ");
    }
    printf("\n");
}

int main() {
    float num;
    printf("Enter a single-precision floating-point number: ");
    scanf("%f", &num);
    uint32_t* binaryRep = (uint32_t*)&num;
    printf("Binary representation: ");
    printBinary(*binaryRep);

    return 0;
}
