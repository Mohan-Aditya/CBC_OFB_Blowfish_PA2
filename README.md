# CBC_OFB_Blowfish_PA2

Blowfish is an encryption technique designed by Bruce Schneier in 1993 as an alternative to DES Encryption Technique. It is significantly faster than DES and provides a good encryption rate with no effective cryptanalysis technique found to date. It is one of the first, secure block cyphers not subject to any patents and hence freely available for anyone to use.
1.	Block Size:  64-bits
2.	Key Size:      32-bits to 448-bits variable size
3.	number of subkeys:   18 [P-array]
4.	number of rounds:     16
5.	number of substitution boxes: 4 [each having 512 entries of 32-bits each]

In Cipher Block Chaining (CBC) mode, each block of plaintext is XORed with the previous ciphertext block before being encrypted. This way, each ciphertext block depends on all plaintext blocks processed up to that point. To make each message unique, an initialization vector must be used in the first block.
CBC has been the most commonly used mode of operation. Its main drawbacks are that encryption is sequential (i.e., it cannot be parallelized), and that the message must be padded to a multiple of the cipher block size. One way to handle this last issue is through the method known as ciphertext stealing. Note that a one-bit change in a plaintext or initialization vector (IV) affects all following ciphertext blocks.

The Output Feedback (OFB) mode makes a block cipher into a synchronous stream cipher. It generates keystream blocks, which are then XORed with the plaintext blocks to get the ciphertext. Just as with other stream ciphers, flipping a bit in the ciphertext produces a flipped bit in the plaintext at the same location. This property allows many error-correcting codes to function normally even when applied before encryption.
Because of the symmetry of the XOR operation, encryption and decryption are exactly the same.



Code starts with initializing S-boxes and subkeys initialisation.
Then functions for decimal to binary, hexadecimal to binary, binary to hexadecimal conversions, xor of two hexadecimal strings, addition modulo 2^32 respectively can be found.
The function “f”, function for generating subkeys, round functions can be found thereafter.
Using the above functions encryption function using blowfish algorithm was made. (Decryption function can also be found for verification purpose)
Later, functions required for CBC mode with plain text as input were written which include functions like text to hexadecimal conversion, creating random numbers for sake of nonce, block-1 encryption function, subsequent block encryption function, function for padding the text.

Then, functions for OFB mode were written which include xor that has to be used for OFB mode and creating random numbers for sake of nonce.
