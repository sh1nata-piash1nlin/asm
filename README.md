# asm 
# gdb lab#1 


## Set up lab env: <br> 
First, we need to compile source code: <br> 
```sh
gcc -g -m32 test.c -o test.out -mpreferred-stack-boundary=2
```

Then, we need to load, debug, disassemble code: <br> 
Load <br> 
```sh
gdb test.out -q
```
Dissamble <br> 
```sh
disas main
```
![image](https://github.com/user-attachments/assets/9dc08686-9cec-43c2-9f51-6aa9a432ad3b)


