# Day 9: Operation Decrypt

Santa has noticed some strange behaviour around the workshop recently. The elves seem to be avoiding him more that usual. When Santa goes to use the computer he notices some emails that he can't open because they are encrypted. Help him decrypt the emails to find out what's going on.

The elves are very savvy and when they heard about [ChaCha20](https://en.wikipedia.org/wiki/Salsa20#ChaCha_variant) encryption they just had to go and make a spin off for their own in-house North Pole approved encryption. It is very similar to ChaCha20, but it only uses a 64bit key and has simplified scrambling functions.

They call it HoHoHo4. Here's how it works (it's actually quite remarkebly similar to ChaCha20 so go check that out, here's a relatively low lines of code implementation: [ChaCha20.h](https://github.com/marcizhu/ChaCha20/blob/master/ChaCha20.h)):

- There is a 16 byte internal state which you can think of as a 4x4 matrix
- Those values need to get scrambled during use to make it secure
- Since the internal state is 16 bytes, that means you can encrypt or decrypt up to 16 bytes at a time before needing to scramble everything again
- There is a base operation of `stir`ring the values around
- When you stir 4 times you have `mix`ed the values once
- Since this is HoHoHo**4**, you need to mix the values 4 times to get them sufficiently scrambled
- After you've scrambled the state you can use it for encrypting/decrypting
- The same process is used for encryption as it is for decryption, just pass in the ciphertext instead of the plaintext

You will need to initialize the state once each time you want to encrypt or decrypt a file. To initialze the state you need to have two pieces of information, the fixed constant and the cipher key. Initialize the state as follows:

|     |  0  |  1  |  2  |  3  |
|:---:|:---:|:---:|:---:|:---:|
|  0  | `H` | `o` | ` ` | `H` |
|  4  | `o` | ` ` | `H` | `o` |
|  8  |  k0 |  k1 |  k2 |  k3 |
|  12 |  k4 |  k5 |  k6 |  k7 |

The constant is the 8 bytes: `Ho Ho Ho`. The first 8 bytes of the state are this constant. The next 8 bytes are the cipher key.

Great! Now that you have the state initialized you will need to `stir` it up. In order to `stir`, you will take 4 of the values and jumble them up. If you take any 4 indices (let's call them A, B, C, and D) this is what you need to do:

1. Increment the value at A by the XOR of values at D and C
2. Increment the value at B by the XOR of values at A and D
3. Increment the value at C by the XOR of values at B and A
4. Increment the value at D by the XOR of values at C and B

Since that only jumbles 4 values, we need to `mix` it more by `stir`ring 4 times with different values each time. We will be `stir`ring each of the 4 columns in the state. In order to `mix` you will need to do the following (pay attention to the order! These are in A, B, C, D order):

1. `stir` the values at positions 0, 4, 8, 12
2. `stir` the values at positions 1, 5, 9, 13
3. `stir` the values at positions 2, 6, 10, 14
4. `stir` the values at positions 3, 7, 11, 15

Excellent! Now we know how to do a `mix` operation. Let's dig into the `cipher` operation, which is the same for both encryption and decryption. You will take an input buffer and return an output buffen that has gone through the `cipher` process.

1. The output buffer is the same size as the input buffer
2. Reset the internal state (See above! Only do this once for each input)
3. Chunk the input into 16 byte blocks (the same size as the internal state)
   1. Do 4 `mix` operations, this is HoHoHo4 after all
   2. For each byte in the internal state XOR it with the next input byte and save that in the output buffer.
   3. Repeat for the next 16 bytes, doing another round of 4 `mix`es each time
   4. Essentially we are slidding the internal state across the input and XORing it, then advancing 16 bytes and mixing again
4. There is no padding on the input, so at any time if you run out of input, stop

Congratulation! You have now either encrypted or decrypted your input.

Now of course the elves are smart and know that since this is such a simple cipher there is no way to know if it fails for a given key. It's just math after all, there is always an answer at the end, but it's not always useful. For that, they came up with their own [HMAC](https://en.wikipedia.org/wiki/HMAC) called HoMAC that used the HoHash function.

The HoHash function is very simple:

1. Set a prime number equal to 31
2. Set the hash output equal to 0
3. For every byte of the input do the following:
   1. Multiply the last hash output by the prime number then add the current byte value
   2. Modulo all that by 2^32
   3. Set that as the new hash output
4. You will end up with a single 32 bit number as the hash value

The HoMAC function is also simple:

1. Concatenate the ciper key and the message (in that order)
2. Run the HoHash function on that
3. Concatenate the cipher key again and with the previous HoHash result (4 bytes)
4. Run the HoHash function on _that_
5. This results in the HoMAC output which is another 32 bit number

There is still one problem tho. You don't know the key! Luckily you know the elves would have a pretty simple key. You know they use only words from a [wordlist](./wordlist.txt), but they could be either capitalized like in the wordlist file already or all lowercase. The key has to be exactly 8 characters long since it is part of the internal state of the cipher. Try mixing and matching the words in the wordlist until you find something that works.

## Something to get you started

Here is an example input. The first line is the HoMAC of the key and the ciphertext. You can run the HoMAC function youself with the key `XmasXmas` and the ciphertext on the next line as the message and compare it to see if you have it working.

As mentioned, the ciphertext (encrypted) is on the second line as bytes separated by commas.

```
475498776
228,110,253,23,183,57,193,12,36,27,109,73,105,184,28,158,203,7,50,193,68,174,36,131,156,59
```


Decrypt the rest of the files to figure out what the elves have been emailing about so you can get to the bottom of their odd behaviour.
