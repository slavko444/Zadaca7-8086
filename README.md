# Zadaca7-8086

Потребно е да се пребројат елементите на низата NIZA кои во бинарна претстава имаат повеќе од 4 единици
и тој број да се смести во променливата S. Должината на низата е N, елементите се со големина 1B. Да се
напише асемблерска програма. 


**Resenie:** 

```
DATA SEGMENT
 N DW ?
 S DW 0
 NIZA DB 1000h DUP (?)
 DATA ENDS
 CODE SEGMENT
 ASSUME CS:CODE, DS:DATA
START: MOV AX,DATA ;Иницијализација
 MOV DS,AX
 XOR SI,SI ; Индекс SI
 MOV DX,N ; Бројач за низата
VRTI: MOV AL,NIZA[SI] ; Еден елемент од низата
 MOV CX,8 ; Бројач за поместување
 XOR BL,BL ; Бројач на единици
BROENJE: SHR AL,1
 JNC PONATAMU
 INC BL
PONATAMU: LOOP BROENJE
 CMP BL,4 ; Дали BL>4 единици
 JNA NE_OK
 INC S ;Има, инкрементирај
NE_OK: INC SI
 DEC DX
 JNZ VRTI
 HLT ; Крај
CODE ENDS
 END START 
``` 

![Screenshot (1)](https://github.com/slavko444/Zadaca7-8086/blob/main/Zadaca7.1%208086%20code.png)
![Screenshot (2)](https://github.com/slavko444/Zadaca7-8086/blob/main/Zadaca7.2%208086%20code.png)

**Develop by:**

[Slavko Srebrenoski ](https://github.com/slavko444)


**Subject**

Microcomputer's systems

**Built With**

This project is built using the following tools:

- [8086 simulator](https://emu8086-microprocessor-emulator.en.softonic.com/?ex=RAMP-2046.0): Assembler and emulator for the Intel 8085 microprocessor.

**Getting Started**

To get a local copy up and running, follow these steps.

**Prerequisites**

In order to run this project you need:

A working computer
Connection to internet
Setup

**How to Run**

To run the program, you need an 8086 emulator or assembler. You can use emulators like DOSBox or TASM (Turbo Assembler). Here's how to run the program using 8086 simulator:

1. Download and install 8086 simulator from [here](https://emu8086-microprocessor-emulator.en.softonic.com/?ex=RAMP-2046.0).
2. Clone this repository to your local machine.
3. Open 8086 simulator and load the `Zadaca7 8086 code.asm` file.
4. Assemble the code by pressing the Assemble button.
5. Run the program by pressing the Run button or by pressing F10.
