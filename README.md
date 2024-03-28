# Hashing File Content with Node.js Crypto Module

**Note:** This code is an example taken from nodejs.org.

This code demonstrates how to hash the content of a file using the Node.js `crypto` module.

## Code Explanation

The code is contained in a file named `crypto.mjs`. Here's a breakdown of the code:

```javascript

**These lines import the createHash function from the Node.js crypto module and the readFile function from the fs/promises module, allowing for asynchronous file reading.**

import { createHash } from 'node:crypto';
import { readFile } from 'node:fs/promises';

**This line creates a hash object using the SHA-1 algorithm.**

const hasher = createHash('sha1');

**This line sets the encoding of the hash output to hexadecimal.**

hasher.setEncoding('hex');

**These lines read the content of the package.json file using readFile and write it to the hash object. await is used to ensure the file is read asynchronously before hashing.**

hasher.write(await readFile('package.json'));
hasher.end();

**This line reads the hashed content from the hash object and stores it in the fileHash variable.**

const fileHash = hasher.read();

**This line logs the hashed content to the console.**

console.log(fileHash);

**This comment indicates how to run the script using Node.js. You can execute node crypto.mjs in the terminal to run the code.**

// run with 'node crypto.mjs'

