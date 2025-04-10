#Code interpretation: 
section .text
global _start

_start:
    mov al, [a]      ; Load value of 'a' (17) into AL
    add al, [b]      ; Add value of 'b' (9) → AL = 26
    mov [c], al      ; Store result (26) in 'c'

    mov eax, 4       ; syscall number for sys_write
    mov ebx, 1       ; file descriptor 1 (stdout)
    mov ecx, hello   ; pointer to message to print
    mov edx, len     ; length of message
    int 0x80         ; make syscall (print)

last:
    mov eax, SYS_EXIT ; syscall number for exit
    int 0x80          ; exit the program

## Compile source code with nasm: 
```sh
nasm -g -f elf first.asm -l f.lst
```

##Link object code to create executable file
```sh
ld -m elf_i386 -o first first.o
```

## To run the executable file: 
```sh
./first
```
![image](https://github.com/user-attachments/assets/01100b3a-40e2-409c-ae61-e7b4646091c4)

## Load program in GDB:
Load: <br>
```sh
gdb first -q
```
Disassemble program from start: 
```sh
disas _start
```
![image](https://github.com/user-attachments/assets/0b3a86a9-5116-4be9-9f44-a3a1c50ec82c)

# View 4 variables a, b, c, d: 
Before that, you need to start a program by typing `start`. 
```sh
x/5xb &a 
```
![image](https://github.com/user-attachments/assets/b89a02db-239b-4fdb-99e6-32e4103420da)

Move to this position by hitting enter multiple times (or type stepi multiple time until it moves to the position in the image): 
![image](https://github.com/user-attachments/assets/03d0bbdc-67d8-44f2-ad5d-8880ec021bcc)
and the variable c is now 1a
![image](https://github.com/user-attachments/assets/4d75d68e-6551-490c-9fdf-01434637696e) 

##Examine the memory: 
These will be the locations of a, b, c, d and hello variables: <br>
```sh
info var
```
![image](https://github.com/user-attachments/assets/34ec01b7-1810-49a0-baec-50f638d88692)

Use `x/s <address>` used to examine memory and interpret it as a null-terminated C-style string. 
![image](https://github.com/user-attachments/assets/6e8f5393-fdaa-4b1d-ab5e-4ae9fb11c1be)

#Try to change the variable of a and b: 
![image](https://github.com/user-attachments/assets/4cf98de0-e163-4778-878b-aa0910b80a95)


