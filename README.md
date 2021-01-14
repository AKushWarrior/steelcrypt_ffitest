# Steel_crypt benchmark
#### FFI vs. Pure Dart

This repository is intended to test the speed of pure-Dart algorithms vs. that of optimized algorithms built in Rust.
I will be using it to inform my decisions about speeding up my [steel_crypt](https://pub.dev/packages/steel_crypt) 
package on various different platforms.

steel_crypt itself is a wrapper over pointycastle, which is by far the most-used cryptography package for Dart. Thus,
using steel_crypt as a representative for the Dart encryption landscape (since the only overhead present in steel_crypt
is encoding work). 

#### AES-CBC-PKCS7 (encrypt only, preliminary result)

| Length of Data | Time to encrypt using steel_crypt | Time to encrypt using Rust |
|----------------|-----------------------------------|----------------------------|
| 7 bytes        | 619 ms                            | 39 ms                      |
| 21 bytes       | 496 ms                            | 31 ms                      |
| 63 bytes       | 521 ms                            | 45 ms                      |
| 189 bytes      | 607 ms                            | 117 ms                     |
| 567 bytes      | 864 ms                            | 129 ms                     |
| 1701 bytes     | 1657 ms                           | 45 ms                      |
| 5103 bytes     | 4161 ms                           | 152 ms                     |
| 15309 bytes    | 12086 ms                          | 39 ms                      |
| 45927 bytes    | 34486 ms                          | 139 ms                     |