# 42_fillit

A Tetris piece arrangement solver that finds the smallest square to fit all given tetromino pieces, created as part of the 42 School curriculum.

## 📖 About

**Fillit** reads tetromino pieces from a file and uses backtracking algorithms to arrange them in the smallest possible square, solving a classic algorithmic optimization problem.

## 🚀 Features

- **Tetromino Validation**: Validates input tetromino pieces
- **Backtracking Algorithm**: Efficiently finds optimal arrangements
- **Smallest Square Solution**: Minimizes the final square size
- **Multiple Piece Support**: Handles up to 26 different pieces
- **Error Handling**: Comprehensive input validation
- **Optimized Placement**: Smart piece positioning strategies

## 🔧 Build Instructions

### Prerequisites

- GCC compiler, Make
- libft library (included)

### Compilation

```bash
make                # Build the project
make clean         # Clean object files
make fclean        # Clean everything
make re            # Rebuild everything
```

## 📝 Usage

```bash
# Solve tetromino arrangement
./fillit tests/valid_maps/sample.fillit

# Test with different piece configurations
./fillit tests/valid_maps/subject.fillit
./fillit tests/valid_maps/hard.fillit
```

### Input Format

Each tetromino piece is represented as a 4x4 grid:

```
....
.##.
.##.
....
```

Multiple pieces separated by empty lines in the input file.

### Output

The program outputs the smallest square arrangement:

```
ABC
ABC
C..
```

## 🔍 Implementation Details

### Algorithm Strategy

- **Validation**: Check each piece is a valid tetromino
- **Normalization**: Position pieces at origin (0,0)
- **Square Sizing**: Start with minimum possible square size
- **Backtracking**: Try placing pieces recursively
- **Optimization**: Increment square size if no solution found

### Piece Validation

- **Connection Check**: All blocks must be connected
- **Block Count**: Exactly 4 blocks per piece
- **Shape Validation**: Must form valid tetromino shapes
- **Character Check**: Only '.', '#', and newlines allowed

### Backtracking Process

1. Try placing current piece at each position
2. Check for overlaps with existing pieces
3. Recursively place remaining pieces
4. Backtrack if no valid placement found
5. Return solution when all pieces placed

## 🧪 Testing

```bash
# Test valid configurations
./fillit tests/valid_maps/sample.fillit
./fillit tests/valid_maps/subject.fillit

# Test error handling
./fillit tests/invalid_maps/bad_tetromino.fillit
./fillit tests/invalid_maps/too_many_pieces.fillit

# Test edge cases
./fillit tests/valid_maps/one_piece.fillit
./fillit tests/valid_maps/max_pieces.fillit
```

### Sample Input Files

- **sample.fillit**: Basic 2-piece example
- **subject.fillit**: Subject example with 3 pieces
- **hard.fillit**: Complex arrangement with many pieces

## 🎯 Algorithm Complexity

- **Time Complexity**: O(n! × s²) where n is pieces and s is square size
- **Space Complexity**: O(s²) for the solution grid
- **Optimization**: Early termination and smart placement order

## 🔗 Dependencies

- **libft**: Custom C library for basic functions
- **Standard C Library**: Memory management and I/O operations

---

_Algorithmic problem-solving project demonstrating backtracking algorithms, optimization techniques, and geometric puzzle solving._
