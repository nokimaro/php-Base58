Base 58 is a close to the same as the more commonly known Base64, the main difference in Base64 and Base58 is that Base58 is used for crypto currencies, eg, encoding a public key or transactions.

Lets take a look at an example, by encoding the text "0testingWorks=" (decided on this string as its a good representation of the differences):

In base64 we get

```
MHRlc3RpbmdXb3Jrcz0=
```

and in base58

```
JpBuDCbgWiyS4HkVihS
``` 

One thing that should be noticeable about these two is that the Base58 is easier to read. this is because Base58 is made for reading. Base58 is not using the `0` character, in fact, it doesn't use "0" (zero), "O" (uppercase letter O), "l" (lowercase letter L), and I (uppercase letter i) as they visually conflict with each other. Depending on the font "0" looks like "O" and "1" looks like "l" the same goes for "I" can look like either "1" or "l". Further more the letters "+" (plus) and "/" (slash) are not used at there is a small risk of the to be wrongly interpreted, and makes the reading harder.

I have created a Base58 Library for PHP that can be found here; <https://git.ryuu.technology/KryuuCommon/Base58>

## Usage

### encoding

```PHP
<?php

use KryuuCommon\Base58\Base58;

$b58 = new Base58();
$encoded = $b58->encode('0testingWorks='); 
```

result

```
JpBuDCbgWiyS4HkVihS
```
    

### decoding

```PHP
<?php

use KryuuCommon\Base58\Base58;

$b58 = new Base58();
$decoded= $b58->decode('JpBuDCbgWiyS4HkVihS');
```

result

```
0testingWorks=
```
    

Further information will be available in the repository