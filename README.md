# Enhanced Node-SymSpell

An enhanced and optimized version of **node-symspell**, a JavaScript port of **SymSpell 6.6**, originally developed by [Mathieu Loutre](https://github.com/MathieuLoutre/node-symspell), based on the [C# version by Wolf Garbe](https://github.com/wolfgarbe/SymSpell) and the [Python version by mammothb](https://github.com/mammothb/symspellpy).

This project improves upon the original by adding new features, optimizing the codebase, and ensuring compatibility with modern environments.

---

## Features

### Key Enhancements:
1. **Node.js 22 Compatibility**:  
   - Updated the code to run seamlessly in Node.js 22 and newer.

2. **Modular Imports**:  
   - Refactored to support ES module imports, enabling cleaner, modern usage patterns.

3. **Updated Helper Methods**:  
   - Improved and streamlined helper methods for easier integration.

4. **New Dependency Versions**:  
   - Replaced older dependencies with newer, more efficient, and secure libraries.

5. **Thorough Testing**:  
   - Validated with local test cases to ensure stability and correctness.

---

## Installation

You can install this package using npm:

```bash
npm install node-symspell-new
```

---

## Basic Example

```javascript
import SymSpell, { Verbosity } from 'enhanced-node-symspell'

const maxEditDistance = 2
const prefixLength = 7
const symSpell = new SymSpell(maxEditDistance, prefixLength)

const dictionaryPath = './dictionaries/frequency_dictionary_en_82_765.txt'
const bigramPath = './dictionaries/frequency_bigramdictionary_en_243_342.txt'

// Load dictionaries
await symSpell.loadDictionary(dictionaryPath, 0, 1)
await symSpell.loadBigramDictionary(bigramPath, 0, 2)

// Input text with typos
const typo = 'Can yu readthis messa ge despite thehorible sppelingmsitakes'
const results = symSpell.lookupCompound(typo, maxEditDistance)

// Output the corrected sentence
console.log(results[0])
```

---

## API Overview

### Constructor

```javascript
new SymSpell(maxDictionaryEditDistance = 2, prefixLength = 7, countThreshold = 1)
```
- Initializes the SymSpell object.

### Methods

1. **Load Dictionaries**:
   - `async loadDictionary(dictFile, termIndex, countIndex, separator = ' ')`
   - `async loadBigramDictionary(dictFile, termIndex, countIndex, separator = ' ')`

2. **Lookup Functions**:
   - `lookup(input, verbosity, maxEditDistance = null, options = {})`
   - `lookupCompound(input, maxEditDistance = null, options = {})`
   - `wordSegmentation(input, options = {})`

---

## Testing

Run the included test cases to ensure the library is functioning correctly:

```bash
npm run test
```

---

## Credits

This library is built upon the work of:
- [Mathieu Loutre](https://github.com/MathieuLoutre/node-symspell) (Original Node.js port).
- [Wolf Garbe](https://github.com/wolfgarbe/SymSpell) (C# SymSpell).
- [Mammothb](https://github.com/mammothb/symspellpy) (Python SymSpell).

---

## License

MIT License
