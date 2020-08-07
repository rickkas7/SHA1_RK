# SHA1 Library

**SHA1 hash implementation for Particle Devices**

## API


### SHA1Init

```cpp
// PROTOTYPE
void SHA1Init(SHA1_CTX* context);
```

Initialize the context structure. Call this to initialize or reuse a `SHA1_CTX` structure.

### SHA1Update

```cpp
// PROTOTYPE
void SHA1Update(SHA1_CTX* context, const unsigned char* data, u_int32_t len);
```

Updates the hash with additional data. You can call this repeatedly with the same ctx to add more data to the hash if the data arrives in buffers.

### SHA1Final

```cpp
// PROTOTYPE
void SHA1Final(unsigned char digest[20], SHA1_CTX* context);
```

Finalizes the hash calculation and stores the SHA1 digest in `digest`. The `digest` variable must point to a buffer of 20 bytes to hold the hash. It's always 20 bytes (160 bits) for SHA1, other SHA hash algorithms have longer digests.

### SHA1\_CTX

```cpp
typedef struct {
    u_int32_t state[5];
    u_int32_t count[2];
    unsigned char buffer[64];
} SHA1_CTX;
```

This structure (72 bytes) stores the state of the SHA1 has. Initialize it with `SHA1Init`. 


## Original Library

```
SHA-1 in C
By Steve Reid <steve@edmweb.com>
100% Public Domain
```

Found here: https://gist.github.com/jrabbit/1042021

## Revision History

### 0.0.1 (2020-08-07)

- Initial version

