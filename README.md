# Energy Histogram & Proportion Calculator DLL (PE1)

A Windows Dynamic Link Library (DLL) written in x86 Assembly (MASM) that processes energy consumption data by creating a histogram and calculating percentage proportions.

**Author:** DN MBOYI (MBOYI DN)  
**Student Number:** 222019179  
**Subject:** CSC03B3  
**Practical Exercise:** PE1  
**Year:** 2025  

---

## Problem Description

This DLL exports two functions for analyzing energy values (ranging from 0 to 15):

1. **`histogram(energyArray, count, binsArray)`**  
   - Takes an array of energy values and the number of elements.
   - Builds a histogram of 16 bins (0 to 15).
   - Values greater than 15 are capped at 15.
   - Increments the appropriate bin for each energy value.

2. **`proportion(binsArray, ratioArray)`**  
   - Takes the histogram bins array (16 elements).
   - Calculates the **percentage proportion** for each bin: `(bin_value * 100) / total_sum`.
   - Stores the results in the ratio array.
   - Handles the case where total sum is 0 (sets all ratios to 0 to avoid division by zero).

---

## Features

- Efficient histogram construction with range checking and capping
- Accurate percentage calculation using integer arithmetic (`bin * 100 / total`)
- Safe handling of zero total to prevent division by zero
- Proper stack frame management and register preservation
- Exported via `.def` file for easy use in C/C++ or other languages
- Fixed 16-bin structure suitable for energy level analysis (0-15)

---

## Technologies Used

- **x86 Assembly Language**
- **MASM** (Microsoft Macro Assembler)
- **DLL Development** with module definition (`.def`) file
- Array processing and integer division
- `LibMain` entry point for DLL initialization

---

## Files Included

- `PE1-template.asm` – Main assembly source with `histogram` and `proportion` functions
- `PE1.def` – Module definition file exporting the two functions
- `README.md`

---

## How to Build

Using the batch file (if available):
```batch
createdll.bat PE1-template PE1
