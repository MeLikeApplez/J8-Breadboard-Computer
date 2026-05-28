# CPU & GPU Project Docs

# Register Table (74LS173 - 24 Chips / 26 Chips)

| 16 Bit | 8 Bit | Description |
| --- | --- | --- |
|  | $ra | ALU Input |
|  | $rb | ALU Input |
|  | $rc | ALU Output |
|  | $re | Error/Status Code |
|  | $rf | Flags |
| $rp[1:0] |  | Ram Pointer |
| $pc[1:0] |  | Program Counter |

# Memory Map

The SRAM chips used, HM62256LP-70 SRAM, only holds up to 15-Bits of address space.

- Address 0x0000 to 0x7FFF is the range of addresses allowed.
- Any addresses listed are **RESERVED** and may not be modified.
- Any addresses **NOT** listed are assumed to be used freely without any restrictions.

| Address (0x0000 → 0x7FFF) | Name | Description |
| --- | --- | --- |
|  |  |  |
|  |  |  |

# Syntax Operations & Definitions

- Syntax Inspiration - [https://llvm.org/docs/LangRef.html](https://llvm.org/docs/LangRef.html)

### Predefined Language Specifics

Registers are predefined by the CPU automatically and are global variables.

```nasm
; 8-Bit Registers
$ra ; => [0000 0000]
$rb ; => [0000 0000]
$rc ; => [0000 0000]
$re ; => [0000 0000]
$rf ; => [0000 0000]

; 16-Bit Registers
$rp[1:0] ; => [0000 0000 0000 0000]
         ;    [ $rp[1]  |  $rp[0] ]
         
$pc[1:0] ; => [0000 0000 0000 0000]
				 ;    [ $rp[1]  |  $rp[0] ]

; Index accessing
$rp[0] ; Lower 8 bits
$rp[1] ; Higher 8 bits
$pc[0] ; Lower 8 bits
$pc[1] ; Higher 8 bits
```

### Variables

```nasm
; Syntax
$<VariableName>

; Setting Variables
$num = 0
```

```nasm
; Usage
$rp[0] = 0xF
$pc[1] = 0x2
$ra = 0x1
```

### Functions/Subroutines/Labels

Functions are only labels that point to a specific line in the number to reference to when calling/jumping.

```nasm
; Definition
@<FunctionName>:
```

```nasm
; Usage
@multiply:
	; code here...
@loop:
  ; code here...
```

```nasm
; Base instructions

; Set program counter from Register A

; Moves and sets RAM/Register data
; RAM[*] = REG *

; REG * = RAM[*]

; Sets specific data onto RAM/Register(<destination>, <source>) destination = source
; Fetches RAM ADDRESS, PROGRAM COUNTER as the "data"

; Logical operations(<destination>, <source>) destination = source

; Math operations(<destination>, <source>) destination = source

; Bitwise Shift operations (n << 1, n >> 1)
****
; Comparison Operations (n < 0, n == 0, n > 0)

; Jump and Jump if (n < 0, n == 0, n > 0)
```

## Micro Instructions

```nasm

```

## Signal Pinout

```nasm
 

```