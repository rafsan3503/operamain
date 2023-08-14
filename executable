section .data
    arrayInteger db 10 DUP(?)  ; Define arrayInteger of size 10

section .text
    global _start

_start:
    mov ax, 0x07C0  ; Set up segment registers for bootloader
    mov ds, ax
    mov es, ax

    ; Task 1: Generate and store integers from 1 to 10 in arrayInteger
    mov cx, 10  ; Set loop counter to 10
    mov di, arrayInteger  ; Set DI to point to arrayInteger

    L1:
    mov [di], cl  ; Store current value of CX in arrayInteger
    inc di  ; Increment DI to point to the next element
    dec cx  ; Decrement CX
    jnz L1  ; Continue loop until CX becomes zero

    ; Task 2: Find the summation of all integers stored in arrayInteger
    mov cx, 10  ; Set loop counter to 10
    mov di, arrayInteger  ; Set DI to point to arrayInteger
    xor ax, ax  ; Clear AX (accumulator) to zero

    L2:
    add al, [di]  ; Add the value at [DI] to AL
    inc di  ; Increment DI to point to the next element
    loop L2  ; Continue loop until CX becomes zero

    ; The summation of all integers is now stored in AL

    ; Task 3: Find the summation of all odd integers stored in arrayInteger
    mov cx, 10  ; Set loop counter to 10
    mov di, arrayInteger  ; Set DI to point to arrayInteger
    xor bx, bx  ; Clear BX (accumulator) to zero

    L3:
    mov al, [di]  ; Load the value at [DI] into AL
    test al, 1  ; Test if AL is odd
    jz NOT_ODD  ; If not odd, jump to NOT_ODD
    add bx, al  ; Add the odd value to BX

    NOT_ODD:
    inc di  ; Increment DI to point to the next element
    loop L3  ; Continue loop until CX becomes zero

    ; The summation of all odd integers is now stored in BX

    ; Task 4: Find the summation of all even integers stored in arrayInteger
    mov cx, 10  ; Set loop counter to 10
    mov di, arrayInteger  ; Set DI to point to arrayInteger
    xor bx, bx  ; Clear BX (accumulator) to zero

    L4:
    mov al, [di]  ; Load the value at [DI] into AL
    test al, 1  ; Test if AL is odd
    jnz NOT_EVEN  ; If not zero, jump to NOT_EVEN
    add bx, al  ; Add the even value to BX

    NOT_EVEN:
    inc di  ; Increment DI to point to the next element
    loop L4  ; Continue loop until CX becomes zero

    ; The summation of all even integers is now stored in BX

    ; Task 5: Generalize the program to handle array of integers from 1 to NUMB_TOTAL
    ; You can add code here to handle a user-specified NUMB_TOTAL value

    ; Terminate the program
    mov ah, 0x4C  ; Exit to DOS function
    xor al, al  ; Set exit code to zero
    int 0x21  ; Call the DOS interrupt
