# Day 15: On the 15th day of Christmas you got Encryption

Krispy the elf finds a hidden letter tucked away under some papers in Santas room. He thinks it is a bit supicious and decides to look into it. He also finds another file next to it that looks related. The letter seems to be encrypted, but this could be important. Krispy is a little worried that Santa would need to hide an encrypted letter. Help him find out what the message says.

Krispy recognizes the ecryption used as the xHoHoHo cipher. It is a simple rolling XOR cipher. For every byte in the message XOR it with a byte from the key. Often the key is shorter than the message, so when getting to the end of the key, wrap back around to the beginning.

The letter looks to also be encoded as hex numbers for portability.
