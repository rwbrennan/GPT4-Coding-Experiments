# Sierpinski Triangle Program in Python
The following experiments were performed using the OpenAI GPT-4 engine set at T = 0.7 and p = 1.
## Prompt 1:
```
Can you print a Sierpinski triangle using asterisk characters using Python?
```
## Response 1:

Yes, you can print a Sierpinski triangle using asterisk characters in Python. Here's a simple example using recursion:
```
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
```
This code defines a function 'sierpinski_triangle' that generates the points of a Sierpinski triangle of order 'n'. The 'print_triangle' function is used to print the asterisk characters at the positions of the generated points. Finally, the script calls these functions to generate and print a Sierpinski triangle of order 4. You can change the value of 'n' to generate a larger or smaller triangle.

## Program Output 1:
The Prompt 1 completion ran with no errors, but produced triangles of varying height. The output for n = 1 is shown below:

![Sierpinski-GPT4-T1-n4](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/46af4b54-17ef-4f6e-838a-c3c6f9f7a108)


## Prompt 2:
```
Can you modify this program to keep the height constant while allowing different orders?
```
## Response 2:

Sure, I can modify the program to keep the height constant while allowing different orders. Here's the modified code:
```
def sierpinski_triangle(height, order, x=0, y=0):
    if order == 1:
        return [(x, y)]

    points = []
    half_height = height // 2

    if order > 1:
        points.extend(sierpinski_triangle(half_height, order - 1, x, y))
        points.extend(sierpinski_triangle(half_height, order - 1, x + half_height, y))
        points.extend(sierpinski_triangle(half_height, order - 1, x + half_height // 2, y + half_height))

    return points

def print_triangle(points, size):
    for y in range(size):
        for x in range(2 * size - 1):
            if (x, y) in points:
                print('*', end='')
            else:
                print(' ', end='')
        print()

if __name__ == "__main__":
    height = 16
    order = 4
    points = sierpinski_triangle(height, order)
    print_triangle(points, height)
```
This code defines a function 'sierpinski_triangle' that generates the points of a Sierpinski triangle of a given `height` and `order`. The 'print_triangle' function is used to print the asterisk characters at the positions of the generated points. Finally, the script calls these functions to generate and print a Sierpinski triangle.

You can change the 'height' and 'order' variables to generate a Sierpinski triangle of the desired size and order. Note that the height should be a power of 2 for the triangle to be displayed correctly.

## Program Output 2:
The Prompt 2 completion ran with no errors and generated the output shown below:
### n = 1
![Sierpinski-GPT4-T2-n1](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/02d37da9-08a2-403a-9c72-e98a3a5a4a0e)

### n = 2
![Sierpinski-GPT4-T2-n2](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/3d0bca2f-7c65-44f0-b029-38d62476d140)

### n = 3
![Sierpinski-GPT4-T2-n3](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/2cffd83f-7d6a-43fa-8efb-e459206cb4fc)

## Prompt 3:
```
Can you fill in the triangles with asterisks to make the orders clearer?
```
## Response 3:
Sure, I can modify the program to fill in the triangles with asterisks to make the orders clearer. Here's the modified code:
```
def filled_triangle(height, x, y):
    points = []
    for i in range(height):
        for j in range(i + 1):
            points.append((x + j, y + i))
    return points

def sierpinski_triangle(height, order, x=0, y=0):
    if order == 1:
        return filled_triangle(height, x, y)

    points = []
    half_height = height // 2

    if order > 1:
        points.extend(sierpinski_triangle(half_height, order - 1, x, y))
        points.extend(sierpinski_triangle(half_height, order - 1, x + half_height, y))
        points.extend(sierpinski_triangle(half_height, order - 1, x + half_height // 2, y + half_height))

    return points

def print_triangle(points, size):
    for y in range(size):
        for x in range(2 * size - 1):
            if (x, y) in points:
                print('*', end='')
            else:
                print(' ', end='')
        print()

if __name__ == "__main__":
    height = 16
    order = 4
    points = sierpinski_triangle(height, order)
    print_triangle(points, height)
```
This code defines a function 'filled_triangle' that generates the points of a filled triangle of a given 'height' with the top point at position '(x, y)'. The 'sierpinski_triangle' function is modified to use the 'filled_triangle' function when the order is 1. The other parts of the code remain the same.

You can change the 'height' and 'order' variables to generate a Sierpinski triangle of the desired size and order. Note that the height should be a power of 2 for the triangle to be displayed correctly.

## Program Output 3:
The Prompt 3 completion ran with no errors and generated the output shown below:

### n = 1
![Sierpinski-GPT4-T3-n1](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/33aefcdf-604d-41b1-a63c-ca898697ae76)

### n = 2
![Sierpinski-GPT4-T3-n2](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/9ef3ce96-7052-4f01-a089-947898bb5fc0)

### n = 3
![Sierpinski-GPT4-T3-n3](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/7534d206-0c7f-4b3a-8a29-bb8f806877b4)

## Prompt 4:
```
Can you make the triangles equilateral?
```
## Response 4:

To make the triangles equilateral, we need to adjust the x-spacing of the characters and the position of the triangles. Here's the modified code:
```
def filled_triangle(height, x, y):
    points = []
    for i in range(height):
        for j in range(-i, i + 1, 2):
            points.append((x + j, y + i))
    return points

def sierpinski_triangle(height, order, x=0, y=0):
    if order == 1:
        return filled_triangle(height, x, y)

    points = []
    half_height = height // 2
    quarter_height = height // 4

    if order > 1:
        points.extend(sierpinski_triangle(half_height, order - 1, x, y))
        points.extend(sierpinski_triangle(half_height, order - 1, x - 2 * quarter_height, y + half_height))
        points.extend(sierpinski_triangle(half_height, order - 1, x + 2 * quarter_height, y + half_height))

    return points

def print_triangle(points, size):
    for y in range(size):
        for x in range(-size + 1, size):
            if (x, y) in points:
                print('*', end='')
            else:
                print(' ', end='')
        print()

if __name__ == "__main__":
    height = 16
    order = 4
    points = sierpinski_triangle(height, order)
    print_triangle(points, height)
```
In this code, the 'filled_triangle' function is modified to create equilateral triangles by adjusting the x-spacing of the characters. The 'sierpinski_triangle' function is also modified to adjust the position of the triangles. The 'print_triangle' function is modified to adjust the x-range for printing the characters.

You can change the 'height' and 'order' variables to generate an equilateral Sierpinski triangle of the desired size and order. Note that the height should be a power of 2 for the triangle to be displayed correctly.

## Program Output 4:
The Prompt 3 completion ran with no errors and generated the output shown below:
### n = 1
![Sierpinski-GPT4-T4-n1](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/89016748-ca52-4cb1-bf99-00d3f5c4e08d)

### n = 2
![Sierpinski-GPT4-T4-n2](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/82c458f0-97ce-4747-97b8-54cabad2a23a)

### n = 3
![Sierpinski-GPT4-T4-n3](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/e51ee8b0-102b-4293-b0d7-eea2d7570aa0)

