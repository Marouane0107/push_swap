# Push Swap 🔄

A highly efficient sorting algorithm implementation using two stacks and a limited set of operations. This project challenges you to sort integers with the minimum number of moves possible.

## 📋 Table of Contents

- [About](#about)
- [Algorithm Overview](#algorithm-overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Operations](#operations)
- [Sorting Strategies](#sorting-strategies)
- [Complexity Analysis](#complexity-analysis)
- [Checker Program](#checker-program)
- [Project Structure](#project-structure)
- [Testing](#testing)
- [Author](#author)

## 🎯 About

Push Swap is a 42 School project that involves sorting data on a stack using a limited set of instructions while aiming for the lowest possible number of actions. The challenge is to find the most efficient sorting algorithm for different data sizes.

### Project Goals:
- Implement efficient sorting algorithms
- Minimize the number of operations
- Handle different data sizes optimally
- Learn algorithm optimization techniques
- Master stack data structures

## 🧠 Algorithm Overview

The program uses different sorting strategies based on input size:

- **2-3 elements**: Direct sorting with minimal operations
- **4 elements**: Strategic use of auxiliary stack
- **5 elements**: Optimized small-set algorithm
- **6-100 elements**: Chunk-based sorting with indexing
- **101+ elements**: Advanced chunking algorithm for large datasets

## ✨ Features

- **Multiple Sorting Algorithms**: Adaptive approach based on input size
- **Optimal Move Count**: Minimized operations for each data size
- **Input Validation**: Comprehensive error checking
- **Duplicate Detection**: Prevents invalid input
- **Memory Management**: Proper allocation and deallocation
- **Bonus Checker**: Program to verify sorting correctness

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Marouane0107/push_swap.git
   cd push_swap
   ```

2. **Compile the project**
   ```bash
   make
   ```

3. **Compile with bonus (checker)**
   ```bash
   make bonus
   ```

4. **Clean object files**
   ```bash
   make clean
   ```

5. **Full clean**
   ```bash
   make fclean
   ```

6. **Recompile**
   ```bash
   make re
   ```

## 🎮 Usage

### Basic Usage
```bash
./push_swap [numbers...]
```

### Examples
```bash
# Sort 5 random numbers
./push_swap 4 67 3 87 23

# Sort numbers from arguments
./push_swap "4 67 3 87 23"

# Large dataset
./push_swap 1 5 2 4 3 6 8 7 10 9
```

### Using the Checker
```bash
# Generate operations and verify with checker
./push_swap 4 67 3 87 23 | ./checker 4 67 3 87 23
```

## 🔧 Operations

The program can perform these stack operations:

| Operation | Description |
|-----------|-------------|
| `sa` | Swap first 2 elements of stack A |
| `sb` | Swap first 2 elements of stack B |
| `ss` | Swap first 2 elements of both stacks |
| `pa` | Push top element from B to A |
| `pb` | Push top element from A to B |
| `ra` | Rotate stack A up |
| `rb` | Rotate stack B up |
| `rr` | Rotate both stacks up |
| `rra` | Rotate stack A down |
| `rrb` | Rotate stack B down |
| `rrr` | Rotate both stacks down |

## 📊 Sorting Strategies

### Small Arrays (2-5 elements)
- **Direct sorting**: Hardcoded optimal solutions
- **Minimal operations**: Hand-optimized for each case

### Medium Arrays (6-100 elements)
- **Chunk-based sorting**: Divide into manageable chunks
- **Index mapping**: Assign relative positions for efficient sorting
- **Strategic pushing**: Move elements to stack B in optimal order

### Large Arrays (100+ elements)
- **Advanced chunking**: Larger, more efficient chunks
- **Optimized back-tracking**: Smart reconstruction of sorted stack
- **Position analysis**: Calculate optimal rotation directions

## 📈 Complexity Analysis

### Performance Targets:
- **3 elements**: ≤ 2 operations
- **5 elements**: ≤ 12 operations
- **100 elements**: ≤ 700 operations
- **500 elements**: ≤ 5500 operations

### Time Complexity:
- Small arrays (≤5): O(1)
- Medium arrays (6-100): O(n²)
- Large arrays (100+): O(n log n)

### Space Complexity: O(n)

## 🔍 Checker Program

The bonus checker program validates the correctness of sorting operations:

```bash
# Manual input
./checker 4 67 3 87 23
sa
pb
rrr
pa
^D

# Pipe from push_swap
./push_swap 4 67 3 87 23 | ./checker 4 67 3 87 23
```

**Output:**
- `OK`: Numbers are sorted correctly
- `KO`: Numbers are not sorted or invalid operations
- `Error`: Invalid input or operations

## 📁 Project Structure

```
push_swap/
├── push_swap.c          # Main program logic
├── push_swap.h          # Header with structures and prototypes
├── parsing.c            # Input validation and parsing
├── utils.c              # Utility functions
├── linked_list.c        # Stack implementation
├── operations_push.c    # Push operations (pa, pb)
├── operations_rotat.c   # Rotation operations (ra, rb, rr)
├── operations_rev_rotat.c # Reverse rotation (rra, rrb, rrr)
├── operations_swap.c    # Swap operations (sa, sb, ss)
├── small_sort.c         # Algorithms for small arrays
├── big_sort.c           # Algorithms for large arrays
├── sort_assist.c        # Helper sorting functions
├── functions.c          # General utility functions
├── ft_split.c           # String splitting utility
├── get_max.c            # Maximum value operations
├── push_max_a.c         # Optimal pushing strategies
├── checker_bonus/       # Bonus checker program files
└── Makefile             # Build configuration
```

## 🧪 Testing

### Test Different Sizes
```bash
# Generate random numbers for testing
./push_swap $(seq 1 100 | shuf | tr '\n' ' ')

# Test with specific challenging cases
./push_swap 1 5 2 4 3
./push_swap $(seq 1 5 | sort -R)
```

### Performance Testing
```bash
# Count operations for 100 numbers
./push_swap $(seq 1 100 | shuf) | wc -l

# Verify correctness
./push_swap $(seq 1 100 | shuf) | ./checker $(seq 1 100 | shuf)
```

### Edge Cases
```bash
# Already sorted
./push_swap 1 2 3 4 5

# Reverse sorted
./push_swap 5 4 3 2 1

# Single element
./push_swap 42

# Invalid input
./push_swap 1 2 3 2  # Duplicates
./push_swap abc      # Non-numeric
```

## ⚠️ Error Handling

The program handles various error cases:
- **Invalid arguments**: Non-numeric input
- **Duplicates**: Same number appears twice
- **Integer overflow**: Numbers outside INT range
- **Empty input**: No arguments provided
- **Memory allocation**: Failed malloc operations

## 🛠️ Key Features

- **Adaptive Algorithm**: Different strategies for different input sizes
- **Memory Efficient**: Minimal memory usage with proper cleanup
- **Error Resistant**: Comprehensive input validation
- **Performance Optimized**: Meets all efficiency requirements
- **Bonus Integration**: Checker program for verification

## 👨‍💻 Author

**Marouane Aouzal** (maouzal)
- GitHub: [@Marouane0107](https://github.com/Marouane0107)
- 1337 School Student

## 📝 Notes

- This project is part of the 42 School curriculum
- Focus on algorithm optimization and efficiency
- Memory leaks are strictly forbidden
- All edge cases must be handled properly
- Performance benchmarks must be met for evaluation

---

*Created as part of the 42 School Push Swap project - April 2023*
