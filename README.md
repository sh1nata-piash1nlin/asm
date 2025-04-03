# asm 
# gdb lab#1 


## 1. Set up lab env: <br> 
First, we need to compile source code: <br> 
```sh
gcc -g -m32 test.c -o test.out -mpreferred-stack-boundary=2
```
To check if the test.o can be implemented: 
```sh
ls -l
```
![image](https://github.com/user-attachments/assets/253ecda6-861a-4c38-8219-698f18da10b5)

Then, we need to load, debug, disassemble code: <br> 
Load <br> 
```sh
gdb test.out -q
```
Dissamble main function <br> 
```sh
disas main
```
![image](https://github.com/user-attachments/assets/9dc08686-9cec-43c2-9f51-6aa9a432ad3b)

Dissamble func function <br> 
```sh
disas func
```
![image](https://github.com/user-attachments/assets/18fdec63-d980-413b-9a9f-e7ac0a0abf0f)

