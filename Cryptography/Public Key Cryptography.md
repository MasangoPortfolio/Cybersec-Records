# Public Key Cryptography

## Asymmetric Cryptography

**Public Key Cryptography**, also known as **Asymmetric Cryptography**, uses two mathematically related keys:

* **Public key** — used for encryption or verification
* **Private key** — used for decryption or signing

---

## RSA

**RSA** is a public-key encryption algorithm based on the difficulty of factoring the product of two large prime numbers.

### Variables

```text
p = large prime number
q = large prime number
n = p × q

e = public exponent
d = private exponent

m = original message (plaintext)
c = encrypted message (ciphertext)
```

### Euler's Totient Function

```text
φ(n) = (p − 1)(q − 1)

     = pq − p − q + 1
```

### Keys

```text
Public key  = (n, e)
Private key = (n, d)
```

---

## Diffie-Hellman Key Exchange

**Diffie-Hellman (DH)** is a key-exchange method used to establish a **shared secret** between two parties over an insecure channel.

### Variables

```text
p = prime number
g = generator/base

a = Alice's private key
b = Bob's private key

A = Alice's public key
B = Bob's public key

K = shared secret
```

### Formulas

**Alice's public key:**

```text
A = gᵃ mod p
```

**Bob's public key:**

```text
B = gᵇ mod p
```

**Shared secret:**

```text
K = Aᵇ mod p
K = Bᵃ mod p
```

Both Alice and Bob independently calculate the same **K**, without directly transmitting the shared secret.
