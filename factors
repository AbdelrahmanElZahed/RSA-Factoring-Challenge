#!/usr/bin/python3
"""Script to factorize numbers from a file into a product of two smaller numbers"""

import sys

def factorize(n):
    """Finds two factors of a number n, where p * q = n and p, q are not necessarily prime"""
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return i, n // i
    return n, 1  # This handles prime numbers by returning the number itself and 1

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: factors <file>")
        sys.exit(1)
    
    file_path = sys.argv[1]
    
    try:
        with open(file_path, 'r') as f:
            numbers = f.read().splitlines()
        
        for number in numbers:
            n = int(number)
            p, q = factorize(n)
            print(f"{n}={p}*{q}")
    
    except FileNotFoundError:
        print(f"Error: {file_path} not found.")
        sys.exit(1)
    except ValueError:
        print(f"Error: Invalid number found in the file.")
        sys.exit(1)

