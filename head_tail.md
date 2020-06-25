# Advanced Bash

Looking at some of the advanced bash command how they work and what they do.

## cat
- This can print out the content of a file, but that's all,
## Head
Head a useful tool to print out the content of a file.
- syntax
```Bash
head option name-of-file
```
You can look at more than one file at once.
```Bash
head name-of-file.txt name-of-file.txt
```

By default (with no option) head  is going to print out the top 1o lines but by add one more command you can choose the length.
- syntax
```Bash
head -n <number> name-of-file.txt
```
The command -n is an option.  
```bash
head -n <-number> name-of-file.txt
```
You can have negative numbers, which omits the last number lines from the file -1. This means if you say -n -3, it will only omit the last 2.

## Head and Tail
These commands can work together for example if you want to get info from the middle of a file.

```bash
head -n -5 products.txt | tail -n 5
```
