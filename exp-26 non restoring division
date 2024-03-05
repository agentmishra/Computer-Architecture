#include <stdio.h>
#include <string.h>

void non_restoring_division(int dividend[], int divisor[], int quotient[]) {
    int partial_remainder[N+1];
    int borrow = 0;

    memset(partial_remainder, 0, sizeof(partial_remainder));

    for (int i = 0; i < N; i++) {
        for (int j = N; j > 0; j--)
            partial_remainder[j] = partial_remainder[j - 1];

        partial_remainder[0] = dividend[i];
        if (partial_remainder[0] == 0) {
            for (int j = 0; j < N+1; j++) {
                partial_remainder[j] -= divisor[j];
                if (partial_remainder[j] < 0) {
                    partial_remainder[j] += 2;
                    partial_remainder[j+1] -= 1;
                }
            }
        } else {
            for (int j = 0; j < N+1; j++) {
                partial_remainder[j] += divisor[j];
                if (partial_remainder[j] >= 2) {
                    partial_remainder[j] -= 2;
                    partial_remainder[j+1] += 1;
                }
            }
        }
        quotient[i] = (partial_remainder[0] >= 0) ? 1 : 0;
        if (partial_remainder[0] < 0) {
            for (int j = 0; j < N+1; j++) {
                partial_remainder[j] += divisor[j];
            }
        }
    }
}

int main() {
    int dividend[N] = {1, 1, 0, 1, 0, 1, 0, 1}; 
    int divisor[N] = {1, 0, 1, 1, 0, 0, 1, 0};  
    int quotient[N]; 
    non_restoring_division(dividend, divisor, quotient);
    printf("Quotient: ");
    for (int i = 0; i < N; i++) {
        printf("%d", quotient[i]);
    }
    printf("\n");

    return 0;
}
