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
| 7 bytes        | 647 ms                            | 45 ms                      |
| 21 bytes       | 555 ms                            | 44 ms                      |
| 63 bytes       | 601 ms                            | 81 ms                      |
| 189 bytes      | 686 ms                            | 174 ms                     |
| 567 bytes      | 971 ms                            | 462 ms                     |
| 1701 bytes     | 1794 ms                           | 1322 ms                    |
| 5103 bytes     | 4425 ms                           | 3864 ms                    |
| 15309 bytes    | 12622 ms                          | 11750 ms                   |
| 45927 bytes    | 36596 ms                          | 35082 ms                   |