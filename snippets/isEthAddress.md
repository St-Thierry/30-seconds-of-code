---
title: String is an Ethereum address
tags: regex
expertise: intermediate
firstSeen: 2022-08-27T20:50:54
---

Checks if the given string is a valid ethereum address for both Eth and L2 chains using regex.

- Write the regex for testing the string
- The regex must check it starts with 0x
- It checks that it has 40 letters after the 0x
- To check for checksum, use keccak and follow this [example](https://github.com/miguelmota/ethereum-checksum-address/blob/master/index.js)

```js
const isEthereumAddress = str =>
  {
    const ethRegex = /^(0x)[0-9a-f]{40}$/i;
    return ethRegex.test(str);
  }
```

```js
isEthereumAddress('0xE0DF096d0D7467e5eb9A613fa5f87493695F471d'); // true
isEthereumAddress('DGrpf4sBThJu1r3goB2b8hAYzr1SNuobU3TMNHLzPugr'); // false
isEthereumAddress('0xrpf4sBThJu1r3goB2b8hAYzr1SNuobU3TMNHL'); // false
```
