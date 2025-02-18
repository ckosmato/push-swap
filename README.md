
# Push-Swap and Checker

## Overview

This repository contains two programs, **push-swap** and **checker**, designed to work together for sorting a list of numbers. The **push-swap** program uses a sorting algorithm to generate a series of operations to sort the list, while the **checker** program verifies if the list is correctly sorted when the operations are applied.

These programs were created by:

- Evaggelia Bourboura (ebourbou)
- Chris Kosmatos (ckosmato)
- Emiliano Kurra (ekurra)

## Prerequisites

Before running the programs, you will need to compile them. These programs are written in **Go**, so you will need to have Go installed on your system.

- [Install Go](https://golang.org/doc/install)

## Compilation

To compile the **push-swap** and **checker** programs, follow these steps:

1. Clone the repository (if not done already):

    ```bash
    git clone https://platform.zone01.gr/git/ebourmpo/push-swap.git
    cd push-swap
    ```

2. Build the programs:

    ```bash
    go build -o push-swap
    go build -o checker
    ```

3. This will create two executable files: `push-swap` and `checker`. Ensure both programs are in the same directory.

## Usage

### Using **push-swap**

To run the **push-swap** program, provide a list of numbers as input. For example:

```bash
./push-swap "5 3 6 2 1"
```

This will output a sequence of instructions that will sort the list of numbers.

### Using **checker**

To use the **checker** program, provide a list of instructions and a list of numbers. The checker will validate whether the given instructions correctly sort the list. For example:

```bash
echo -e "pb
ra
pb
ra
sa
ra
pa
pa
" | ./checker "0 9 1 8 2"
```

This will apply the instructions and verify if the list `0 9 1 8 2` is correctly sorted after the operations.

### Using **push-swap** and **checker** Together

You can use both programs together by piping the output of **push-swap** into **checker**. For example:

```bash
ARG="4 67 3 87 23"
./push-swap "$ARG" | ./checker "$ARG"
```

In this case, **push-swap** generates the sorting instructions for the list `4 67 3 87 23`, and **checker** verifies if the instructions result in a sorted list.

## Program Description

### **push-swap**

- The **push-swap** program generates a series of operations to sort the list of numbers.
- The program implements a sorting algorithm designed to use the least number of operations (known as "deterministic instructions").
- It outputs the necessary instructions to sort the input list.

### **checker**

- The **checker** program takes a list of numbers and a series of instructions.
- It checks if the instructions result in a sorted list.
- The program outputs whether the list is sorted (`OK`) or not (`KO`).
