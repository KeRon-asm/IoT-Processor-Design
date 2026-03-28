# Processor Design — Combinational Logic

## Overview
This project currently implements two components of a processor datapath:
- `Processor_Parser.py` — A 32-bit signed integer parser with two's complement encoding, overflow detection, and saturation handling
- `combinational_logic.py` — A combinational logic processor that converts truth tables into simplified Boolean expressions using Karnaugh Maps

---

## Files
| File | Description |
|------|-------------|
| `Processor_Parser.py` | 32-bit signed integer datapath component |
| `combinational_logic.py` | Truth table input, SOP/POS generation, K-Map simplification, and validation |

---

## Requirements
- Python 3.x
- No external libraries required

---

## How to Run

### Processor Parser
```bash
python3 Processor_Parser.py
```
- Enter a decimal integer when prompted
- Select output format: `DEC`, `BIN`, or `HEX`

### Combinational Logic
```bash
python3 combinational_logic.py
```
Follow the prompts:
1. Enter number of input variables (2–4)
2. Enter truth table row by row (inputs followed by output, space separated)
3. Select `SOP` or `POS`
4. View the canonical equation, K-Map, simplified expression, and validation result

---

## Example (n=2, SOP)
```
How many input variables? Must be >=2
2
Row 0: 0 0 0
Row 1: 0 1 1
Row 2: 1 0 1
Row 3: 1 1 1

Canonical SOP: F = A'B + AB' + AB
Minterms: m[1, 2, 3]

K-Map (AB):
         B = 0       B = 1
A = 0      0           1
A = 1      1           1

Simplified Expression: F = A + B
Validation passed!
```

---

## Features
- Supports 2–4 input variables
- Truth table validation (binary values, no duplicates, complete combinations)
- Canonical SOP and POS generation with minterms/maxterms
- K-Map construction using Gray code ordering
- Automatic grouping and simplification
- Validation of simplified expression against original truth table
