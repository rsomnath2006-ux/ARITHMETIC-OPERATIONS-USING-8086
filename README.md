# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   12                     | 
|  2001                   |   34                     |
|  2002                   |   12                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   68                     | 
|  2005                   |   24                     |
|  2006                   |   00                     |

#### Manual Calculations
![IMG-20250919-WA0012](https://github.com/user-attachments/assets/d388ca81-4f72-460c-a220-a15fd99c4a06)

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="639" height="422" alt="Screenshot 2025-09-12 085412" src="https://github.com/user-attachments/assets/2f69010e-4486-49f0-bdfd-8f4a97d7583d" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   56                     | 
|  2001                   |   78                     |
|  2002                   |   25                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   31                     | 
|  2005                   |   44                     |
|  2006                   |   34                     |
#### Manual Calculations
![INSUB](https://github.com/user-attachments/assets/046321fc-ef60-4170-a251-c257bafdb3d4)


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="660" height="441" alt="Screenshot 2025-09-20 085310" src="https://github.com/user-attachments/assets/d6e43fe8-80b2-40e8-9a80-f5985b715bea" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   12                     | 
|  2001                   |   34                     |
|  2002                   |   12                     |
|  2003                   |   34                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   90                     | 
|  2005                   |   5A                     |
|  2006                   |   4B                     |
#### Manual Calculations
![IMG-20250919-WA0013](https://github.com/user-attachments/assets/77ba623e-f8a1-4225-aeb3-c94efc2447fd)

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="641" height="420" alt="Screenshot 2025-09-19 140347" src="https://github.com/user-attachments/assets/4eca69da-9b9c-4aca-9201-2e87602133d6" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   |   68                     | 
|  2001                   |   24                     |
|  2002                   |   34                     |
|  2003                   |   11                     |


| MEMORY LOCATION (INPUT) | DATA (OUTPUT)            |
| ----------------------- | ------------------------ |
|  2004                   |   00                     | 
|  2005                   |   02                     |
|  2006                   |   02                     |

#### Manual Calculations
![INDIVI](https://github.com/user-attachments/assets/022d6d27-c89a-4c0c-8a11-34b42d78ff3d)

## OUTPUT FROM MASM SOFTWARE
<img width="640" height="438" alt="Screenshot 2025-09-20 090533" src="https://github.com/user-attachments/assets/63b8a557-cd78-46c3-b992-2b72cdbb4e93" />



## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

