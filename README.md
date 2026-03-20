# Alcu

Alcu is a terminal strategy game written in C, inspired by Misere Nim.

Two players take turns removing items from heaps, with one twist:
the player who takes the last item loses.

In this implementation, the game is played against an AI, and both the AI and the player can only remove items from the last non-empty heap.

## Features

- C project with a custom static library dependency (`libft`)
- Terminal visualization of heaps
- AI turn logic tailored for this ruleset
- Supports input from standard input or a map file argument

## Game Rules

- The game consists of multiple heaps of items.
- On each turn, the current player must remove between 1 and 3 items.
- Items are removed only from the last non-empty heap.
- AI always plays first.
- Misere condition: taking the last remaining item loses the game.

## Input Format

The map is a list of lines, one integer per line.
Each line is the number of items in one heap.

Example:

```text
3
5
2
```

Validation rules:

- Each line must be a valid integer string.
- Each heap value must be between 1 and 10000.
- Empty input is treated as invalid.

If parsing fails, the program prints `ERROR` and exits.

## Build

Requirements:

- `cc`
- `make`

Build the project:

```bash
make
```

This builds:

- `libft/libft.a`
- `alum1`

Useful targets:

```bash
make clean
make fclean
make re
```

## Usage

Run with standard input:

```bash
./alum1
```

Run with a map file:

```bash
./alum1 path/to/map.txt
```

If too many arguments are provided:

```text
Usage: ./alum1 [map file]
```

## Gameplay Notes

- During the player turn, the prompt is:

```text
Please choose between 1 and 3 items:
```

- Invalid player input is rejected and the prompt repeats.
- `Ctrl+D` during player input stops the game gracefully.
- Heap printing is centered based on the largest heap.
- For very large heaps, rendering is shortened with a suffix counter.

## Project Structure

```text
include/      # public headers
src/          # game source files
libft/        # custom C utility library
Makefile      # build entry point
```

## License

MIT License. See `LICENSE`.