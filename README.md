# Coding Literacy Experiments with GPT-4
This repository contains a number of experiments to evaluate GPT-4's ability to generate code from short natural language prompts, and to read and interpret Python code. We have used the term "coding literacy" here to recognize both reading and writing skills. 

The repository contains two files: 

1. Create-Program.md: Describes experiments on writing Python code from short natural language prompts.
2. Read-Program.md: Describes experiments on reading and interpreting Python code.

## Sierpinski Triangles
The first set of experiments focus on generating Sierpinski triangles on the terminal using asterisk characters. Output from the author's implementation for the first three fractal levels follows:

### n = 1
![Sierpinski-rwb-1](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/ee07c5f2-3838-448b-899d-589fe9d1fa8e)

### n = 2
![Sierpinski-rwb-2](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/c98649c5-b35e-4a0f-a30f-0f0f16210aa5)

### n = 3
![Sierpinski-rwb-3](https://github.com/rwbrennan/GPT4-Coding-Experiments/assets/19438964/76a0a51f-438c-4e30-95fc-619039ffc65f)

### Python program generation results
GPT-4 was able to generate a successful solution, however the program had to be refined by providing GPT-4 with a series of prompts to lead it to the desired solution. 

### Python program interpretation results
GPT-4 was able to correctly describe the behaviour of the author's program. As well, GPT-4 provided an example output that was visually correct for a triangle with height = 7 and fractal level = 4. However, the output differed from the author's in the number of asterisks used: the author's used 18, while GPT-4 used 14. 
