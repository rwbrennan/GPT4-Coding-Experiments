# Sierpinski Triangle Program in Python
## Prompt 1:
```
Can you print a Sierpinski triangle using asterisk characters using Python?
```
## Response 1:
```
Yes, you can print a Sierpinski triangle using asterisk characters in Python. Here's a simple example using recursion:

def sierpinski_triangle(n, x=0, y=0):
    if n == 1:
        return [(x, y)]
    
    points = []
    half_size = 2 ** (n - 2)
    
    points.extend(sierpinski_triangle(n - 1, x, y))
    points.extend(sierpinski_triangle(n - 1, x + half_size, y))
    points.extend(sierpinski_triangle(n - 1, x + half_size // 2, y + half_size))
    
    return points

def print_triangle(points, size):
    for y in range(size):
        for x in range(size):
            if (x, y) in points:
                print('*', end='')
            else:
                print(' ', end='')
        print()

if __name__ == "__main__":
    n = 4
    size = 2 ** (n - 1)
    points = sierpinski_triangle(n)
    print_triangle(points, size)

This code defines a function `sierpinski_triangle' that generates the points of a Sierpinski triangle of order `n`. The `print_triangle`function is used to print the asterisk characters at the positions of the generated points. Finally, the script calls these functions to generate and print a Sierpinski triangle of order 4. You can change the value of `n` to generate a larger or smaller triangle.
```
