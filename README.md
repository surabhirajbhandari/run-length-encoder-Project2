# Run-Length Encoder Project in C

This project implements a simple file compressor and decompressor using the **Run-Length Encoding (RLE)** algorithm in C. It supports four modes: compression, expansion, hexdump debugging, and test file generation.

## What is Run-Length Encoding?

Run-Length Encoding is a basic data compression technique that encodes sequences of repeating bytes as a count followed by a single value, reducing the size of data with long repeated patterns.

---

## Features

- **Compression** (`-c`)  
  Compress a file using RLE and output a `.rle` encoded version.

- **Expansion** (`-x`)  
  Decompress a `.rle` file back to its original form.

- **Debug** (`-d`)  
  Print a hex dump of the file for inspection.

- **Generate** (`-g`)  
  Create a test file (`test.bin`) with known contents to verify encoding/decoding behavior.

---

## How to Compile

Make sure you have `gcc` installed. Then run:

```bash
gcc -o rle main.c

Or use the provided `Makefile`:

```bash
make
```

This will create an executable called `rle`.

---

## Usage

```bash
./rle MODE filename
```

### Available Modes:
| Mode | Description |
|------|-------------|
| `-c` | Compress a file to `.rle` |
| `-x` | Expand a `.rle` file |
| `-d` | Show hex dump of file |
| `-g` | Generate a test file |

---

## Example Workflow

```bash
# Generate a test file
./rle -g test.bin

# Compress the test file
./rle -c test.bin

# Expand the compressed file
./rle -x test.bin.rle

# Confirm the result matches the original
diff test.bin test.bin   # Should return nothing if identical

# Debug: view bytes of the compressed file
./rle -d test.bin.rle
```

---

## File Structure

```
main.c         - Core implementation
Makefile       - Optional build automation
replit.nix     - Replit environment configuration
```

