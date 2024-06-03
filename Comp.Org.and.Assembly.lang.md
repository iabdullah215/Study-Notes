# Computer Organization and Assembly Language Notes

* *Opcode* also known as the operation code specifies the operation to be performed.
* *Next instruction reference* tells the processor to fetch from where it has to fetch the next instruction. 
* *Source operand reference* points to the source operands that work as an input for some other process.
* *Result operand reference* tells or indicates that the process will produce some result.
* **AT&T and Intel** syntaxes are two different ways of writing assembly language code, particularly for the **x86 architecture**.
* In **intel** the destination operand comes first followed by the source operand for example `mov eax, 1`. In naming convention in intel is simple like `eax` and `ebx`. Similarly the constants are written as it is.
* In **AT&T** the source operand comes first followed by the destination operand for example `mov $1, %eax`. In the naming convention of **AT&T** the names are refixed by a percentage sign like `%eax`. Likewise, the constants are attached with a dollar sign like `$1` and `$42`.
* Data Processing --> Arithmetic and Boolean Instructions
* Control --> Test Instructions
* Data Storage --> Data into and out of registers
* Data Movement --> I/O Instructions
---
### Source and result operands can be in one of four areas

* Main or virtual memory --> memory references
* I/O Device --> Specifies the IO module.
* Process Registers --> If more than one register exists each register is assigned a unique name or number and the instruction must contain the number of the desired register.
* Immediate --> The value of the operand is contained in a field in the instruction being executed.
---

* **Packed decimal** - Each decimal digit is represented by a 4-bit code with two digits stored per byte (Hex).
* Textual data in character form cannot be easily stored or transmitted by data processing and communications systems because they are designed for binary data.
 * *Each word or other addressable unit (byte, halfword, and so on) is treated as a single unit of data.
 * Logical Data is a bit-oriented view of the data.
 * **General Purpose Registers** **are**: `Eax , Ebx, Ecx, Edx, Esi, Edi`
 * **Reserved**: `Ebp, Esp, Eip`
 * The multiplication and division instructions always use `EAX` and `EDX`
 ---
### Segment Register

Divides system's memory into multiple segments to manage and protect different parts of memory.
* Code Segment (CS): Holds the starting address of the code segment, contains the instructions to be executed.
* Data Segment (DS): Holds the starting address of the data segment, which contains data used by the program.
* Stack Segment (SS): Holds the starting address of the stack.
---
### Memory Models

* ***SMALL :** Code in one segment, data in one segment
* ***MEDIUM :** Code in more than one segment, data in one segment.
- **COMPACT :** Code in one segment, data in more than one segment.
- **LARGE :** Both code and data in more than one segments. No array larger than `64KB`
- **HUGE :** Both code and data in more than one segments. Array may be larger than `64KB`.
---

* The most important flags for malware analysis are `CF`, `SF`, `ZF` and `T`.
* • `ZF` The zero flag is set when the result of an operation is equal to zero.
* `CF` The carry flag is set when the result of an operation is too large (carry) or too small (borrow) for the destination operand.
* `SF` The sign flag is set when the result of an operation is negative.
* `TF` The trap flag is used for debugging.
* `eax`, `ebx`, `ecx`, and `edx` are all `32` bit registers.
* Lower half of the each register is denoted by `Ax`, `Bx`, `Cx`, and `Dx`. These are `16` bit registers.
* These `16` bit registers can be further divided into lower 8 and upper `8` bits `AL`, `BL`, `CL`, and `DL` and `AH`, `BH`, `CH`, and `DH` respectively. 
* A more flexible approach to parameter passing is the stack. When the processor executes a call, it not only stacks the return address, it stacks parameters to be passed to the called procedure. The called procedure can access the parameters from the stack. Upon return, return parameters can also be placed on the stack.
---
### Big Vs Little Endian

Refers to the order in which the bytes (8-bit units) are arranged within memory.

1. **Big Endian:**
	* In the big endian the most significant byte comes first followed by the least significant byte.
    * Suppose a value to be stored `12345678` it will be stored in this way, `12`- `34` - `56` - `78`.
    * 
1. **Little Endian:**
	* In the little endian the least significant byte comes first followed by the most significant byte.
	* Suppose a value to be stored `12345678` it will be stored in this way, `78`- `56` - `34` - `12`
This presents problems when data are transferred from a machine of one endian type to the other.
---

* We already know that `SHL` performs *unsigned multiplication* efficiently when the multiplier is a power of 2.

```assembly
mov eax,123
mov ebx,eax
shl eax,5           ; mult by 25
shl ebx,2           ; mult by 22
add eax,ebx
```

* Isolating a bit string in assembly means selecting and extracting specific bits from a binary number. This is often done using bitwise operations to focus on a subset of the bits within a larger bit string.
* Signed Byte 

		`0 ---------------I---------------- 225`
		
* Unsigned Byte

		`-128 ---------------I--------------- +127`

* `REAL4` defines a `4-byte` single-precision floating-point variable. `rVal1 REAL4 -1.2`
* `REAL8` defines an `8-byte` double precision value `rVal2 REAL8 3.2E-260`
* `REAL10` defines a `10-byte` extended-precision value `rVal3 REAL10 4.6E+4096`
* Symbol defined with `=` can be redefined within the same program.

```assebmly
; variable defination

bvar db 10                 ; 8-bit
cvar db "H"                ; 8-bit
strn db "Hello World"      ; 32-bit
wVar dw 5000               ; 16-bit
dvar dd 50000              ; 32-bit
arrr dd 100, 200, 500      ; 32-bit
vall db ?                  ; Uninitialed

```

* In assembly language, particularly with assemblers like NASM (Netwide Assembler), `res` is used in data definition to reserve space in memory without initializing it. The `res` directive comes in different forms depending on the size of the memory block you want to reserve:

- `resb` (reserve byte) for reserving bytes.
- `resw` (reserve word) for reserving words (usually 2 bytes).
- `resd` (reserve double word) for reserving double words (usually 4 bytes).
- `resq` (reserve quad word) for reserving quad words (usually 8 bytes).
- `rest` (reserve ten bytes) for reserving ten bytes.

- `ALIGN` directive aligns a variable on a byte, word, doubleword, or paragraph boundary.
- The `ALIGN` directive is a powerful tool in assembly language that helps optimize memory access and performance by aligning data and code segments to specified boundaries.
- The `TYPE` operator is used to determine the size of a data element or a variable. It returns the size in bytes of the data type or the label it is applied to.
- The `LENGTHOF` operator returns the number of elements in an array or data structure. It is used to determine the count of elements in an array.
- The `SIZEOF` operator returns the total size in bytes of a data item or data structure. It is typically used to determine the size of a variable or an array.
- In assembly language, the term "indirect operators" typically refers to operators or addressing modes that indirectly access memory locations through a memory address stored in a register or memory location. For example `mov al, [esi]`

- **Add Operation Example Code:**

```assembly
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
lowercaseChar BYTE 'a'   
uppercaseMask BYTE 11011111b  
.code
main PROC
    
    mov al, lowercaseChar    
    and al, uppercaseMask

    push 0
    call ExitProcess
main ENDP
END main

```

1. `mov al, 'a'`: This instruction moves the ASCII value of the lowercase character 'a' into the AL register. ASCII 'a' has the value 97 (0x61) in decimal or 01100001 in binary.
2. `and al, 11011111b`: This instruction performs a bitwise AND operation between the contents of AL and the binary mask 11011111b. This mask has a 0 in the 5th bit position (counting from right to left), which corresponds to the bit responsible for lowercase/uppercase differentiation in ASCII characters. By ANDing with this mask, we effectively force that bit to 0, thereby converting the lowercase character to uppercase.
3. After executing these instructions, the AL register will contain the ASCII value of the uppercase character 'A', which is 65 (0x41) in decimal or 01000001 in binary.
4. Finally, the program calls `ExitProcess` to terminate.

* **AND Operator Example Code 02**

```assembly
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
wordVal WORD 1234      ; Example integer value
.code
main PROC
    ; Move the integer value into AX
    mov ax, wordVal

    ; AND the lowest bit with 1
    and ax, 1

    ; Jump to label EvenValue if the Zero flag is set
    jz EvenValue

    ; If the Zero flag is not set, the number is odd, continue processing here
    ; ...

EvenValue:
    ; If the Zero flag is set, the number is even, handle the even case here
    ; ...

    ; Exit the program
    push 0
    call ExitProcess
main ENDP
END main

```

1. `mov ax, wordVal`: This instruction moves the integer value stored in the memory location `wordVal` into the AX register. This value represents the integer that we want to check if it's even or odd.
2. `and ax, 1`: This instruction performs a bitwise AND operation between the contents of AX and the binary value 00000001 (1 in decimal), effectively isolating the lowest bit of the integer. If this lowest bit is 1, the number is odd; if it's 0, the number is even.
3. `jz EvenValue`: This instruction jumps to the `EvenValue` label if the Zero flag is set after the AND operation. If the lowest bit of the integer was 0 (indicating that it's even), the result of the AND operation will be 0, setting the Zero flag.
4. If the Zero flag is not set, it means the lowest bit was 1 (indicating that the number is odd), and the program continues processing at the next instruction after the `jz` instruction.
5. At the `EvenValue` label, you would handle the case where the integer is even. After that, the program calls `ExitProcess` to terminate.

* **OR Operator Example Code 01**

```assembly
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
binaryByte BYTE 6   ; Binary decimal byte to be converted
.code
main PROC
    ; Move the binary decimal byte into AL
    mov al, binaryByte

    ; OR AL with binary 00110000 (set bits 4 and 5)
    or al, 00110000b

    ; Now AL contains the ASCII representation of the 
    ; digit equivalent to the binary decimal byte.
    ; For example, if binaryByte is 6, after the OR operation, 
    ; AL will contain the ASCII digit '6'.

    ; Exit the program
    push 0
    call ExitProcess
main ENDP
END main

```

1. `mov al, binaryByte`: This instruction moves the value stored in the memory location `binaryByte` into the AL register. This value represents the binary decimal byte that we want to convert to its ASCII equivalent.
2. `or al, 00110000b`: This instruction performs a bitwise OR operation between the contents of AL and the binary value `00110000b`. This operation sets bits 4 and 5 in the AL register without affecting the other bits. These bits correspond to the ASCII representation of decimal digits.
3. After the OR operation, AL contains the ASCII representation of the digit equivalent to the binary decimal byte. For example, if the `binaryByte` is 6 (00000110b), after the OR operation, AL will contain the ASCII digit '6' (00110110b).
4. Finally, the program calls `ExitProcess` to terminate.
---
### Loops 

**Copying a string**

```assembly
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
source BYTE "This is the source string", 0   ; Source string with null terminator
target BYTE SIZEOF source DUP(0)             ; Target array with same size as source
.code
main PROC
    ; Initialize index register (ESI) and loop counter (ECX)
    mov esi, 0
    mov ecx, SIZEOF source

L1:
    ; Get character from source using indexed addressing
    mov al, source[esi]
    
    ; Store the character in the target array
    mov target[esi], al
    
    ; Increment the index register to move to the next character
    inc esi
    
    ; Loop until ECX (loop counter) reaches zero
    loop L1

    ; Exit the program
    push 0
    call ExitProcess
main ENDP
END main

```

### Explanation:

1. **Data Section**:
    - `source BYTE "This is the source string", 0`: This declares a null-terminated string `source`.
    - `target BYTE SIZEOF source DUP(0)`: This creates an array `target` of the same size as `source`, initialized with zeros. The `SIZEOF source` gives the total size of the `source` array, including the null terminator.
1. **Code Section**:
    - `mov esi, 0`: Initializes the index register `ESI` to 0. `ESI` will be used to index through the characters of the `source` and `target` arrays.
    - `mov ecx, SIZEOF source`: Initializes the loop counter `ECX` with the size of the `source` array. `ECX` will be decremented with each iteration of the loop.
1. **Loop (L1)**:
    - `mov al, source[esi]`: Loads the byte at `source[esi]` into the `AL` register. This gets the current character from the `source` array.
    - `mov target[esi], al`: Stores the value in `AL` (the current character from `source`) into `target[esi]`. This copies the character to the `target` array.
    - `inc esi`: Increments `ESI` to point to the next character in the arrays.
    - `loop L1`: Decrements `ECX` and jumps to the label `L1` if `ECX` is not zero. The `loop` instruction combines decrementing `ECX` with a conditional jump, making it convenient for loops.
1. **Exit**:
    - `push 0` and `call ExitProcess`: Terminates the program by calling `ExitProcess` with an exit code of 0.

**String Reversing**

```assembly
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
aName BYTE "Kip Irvine", 0          ; Original string with null terminator
nameSize = SIZEOF aName - 1         ; Size of the string excluding the null terminator
.code
main PROC

    ; Push the name on the stack
    mov ecx, nameSize               ; Set ECX to the size of the string
    mov esi, 0                      ; Initialize index register to 0

L1:
    movzx eax, aName[esi]           ; Move character from aName to EAX (zero-extended)
    push eax                        ; Push the character onto the stack
    inc esi                         ; Move to the next character
    loop L1                         ; Repeat until all characters are pushed

    ; Pop the name from the stack, in reverse, and store in the aName array
    mov ecx, nameSize               ; Reset ECX to the size of the string
    mov esi, 0                      ; Reset index register to 0

L2:
    pop eax                         ; Pop character from stack into EAX
    mov aName[esi], al              ; Store the character back into aName
    inc esi                         ; Move to the next character
    loop L2                         ; Repeat until all characters are popped

    ; Exit the program
    push 0
    call ExitProcess
main ENDP
END main
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO,
dwExitCode: DWORD
.data
aName BYTE "Kip Irvine", 0          ; Original string with null terminator
nameSize = SIZEOF aName - 1         ; Size of the string excluding the null terminator
.code
main PROC

    ; Push the name on the stack
    mov ecx, nameSize               ; Set ECX to the size of the string
    mov esi, 0                      ; Initialize index register to 0

L1:
    movzx eax, aName[esi]           ; Move character from aName to EAX (zero-extended)
    push eax                        ; Push the character onto the stack
    inc esi                         ; Move to the next character
    loop L1                         ; Repeat until all characters are pushed

    ; Pop the name from the stack, in reverse, and store in the aName array
    mov ecx, nameSize               ; Reset ECX to the size of the string
    mov esi, 0                      ; Reset index register to 0

L2:
    pop eax                         ; Pop character from stack into EAX
    mov aName[esi], al              ; Store the character back into aName
    inc esi                         ; Move to the next character
    loop L2                         ; Repeat until all characters are popped

    ; Exit the program
    push 0
    call ExitProcess
main ENDP
END main

```

1. **Data Section**:
    - `aName BYTE "Kip Irvine", 0`: This declares the null-terminated string `aName`.
    - `nameSize = SIZEOF aName - 1`: This calculates the size of the string excluding the null terminator, which is useful for looping.
2. **Code Section**:
    - `mov ecx, nameSize`: Initializes the loop counter `ECX` with the size of the string.
    - `mov esi, 0`: Initializes the index register `ESI` to 0, used for indexing through the string.
3. **First Loop (L1)**:
    - `movzx eax, aName[esi]`: Moves the character from `aName[esi]` into `EAX` and zero-extends it.
    - `push eax`: Pushes the character onto the stack.
    - `inc esi`: Increments `ESI` to move to the next character.
    - `loop L1`: Decrements `ECX` and repeats the loop if `ECX` is not zero.
4. **Second Loop (L2)**:
    - `mov ecx, nameSize`: Resets the loop counter `ECX` to the size of the string.
    - `mov esi, 0`: Resets the index register `ESI` to 0.
    - `pop eax`: Pops the top value from the stack into `EAX`.
    - `mov aName[esi], al`: Stores the lower byte of `EAX` (the character) back into `aName`.
    - `inc esi`: Increments `ESI` to move to the next character.
    - `loop L2`: Decrements `ECX` and repeats the loop if `ECX` is not zero.
5. **Exit**:
    - `push 0` and `call ExitProcess`: Terminates the program by calling `ExitProcess` with an exit code of 0.
---
