
## NAME: S.KOWSHIK RAM

## REG.NO: 212225230143


# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm
  
## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:

```PY
#include <stdio.h>
#include <math.h>

int power(int base, int exp, int mod)
{
    int result = 1;

    while(exp > 0)
    {
        result = (result * base) % mod;
        exp--;
    }
    return result;
}

int main()
{
    int p, g;
    int a, b;
    int A, B;
    int keyA, keyB;

    printf("Enter prime number (p): ");
    scanf("%d", &p);

    printf("Enter primitive root (g): ");
    scanf("%d", &g);

    printf("Enter private key of User A: ");
    scanf("%d", &a);

    printf("Enter private key of User B: ");
    scanf("%d", &b);

    A = power(g, a, p);
    B = power(g, b, p);

    printf("\nPublic Key of User A = %d", A);
    printf("\nPublic Key of User B = %d", B);

    keyA = power(B, a, p);
    keyB = power(A, b, p);

    printf("\n\nSecret Key computed by User A = %d", keyA);
    printf("\nSecret Key computed by User B = %d", keyB);

    return 0;
}
```

## Output:

<img width="487" height="424" alt="Screenshot 2026-08-21 112059" src="https://github.com/user-attachments/assets/a150528b-135a-4506-ba11-ec0202363a3d" />

## Result:
  The program is executed successfully

