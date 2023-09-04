## uni04
uni04 (or uni.4) is a 4-bit architecture made for [Alex's 4-bit arch challenge](http://207.180.202.42/common/events/4bit-1.html)!

### Instructions

| Bytecode | Instruction | Arguments     | Behaviour    |
| -------- | ----------- | ------------- | ------------ |
| 0        | imm         | reg con       |              |
| 1        | ldx         | adr           |              |
| 2        | ldy         | adr           |              |
| 3        | ldi         | reg adr reg   | <img src="scrunkly.jpg" width="300" height="20"> |
| 4        | stx         | adr           |              |
| 5        | sty         | adr           |              |
| 6        | mov         | reg reg       |              |
| 7        | add         | reg reg       | arg1 += arg2 |
| 8        | sub         | reg reg       | arg1 -= arg2 |
| 9        | shr         | reg con       |              |
| A        | not         | reg           |              |
| B        | nor         | reg con       |              |
| C        | jmp         | adr           |              |
| D        | jmz         | adr           |              |
| E        | cal         | adr           | <img src="niki.png" width="300" height="20"> |
| F        | ret         |               |              |

### ASM syntax example

```
mov x y    // Hmmm comment
ldx 7      // meow :3
ldi x 21 a
```

As you can see instead of `;` you use `//` and there is no `,` unlike most ASMs

### Turning into opcode

#### Registers

| | |
|-|-|
|x|0|
|y|1|

`mov x y` = `06 00 01`

`imm x 8` = `00 00 08`

#### Addreses (8-bit)

|   |   |
|---|---|
|adr|## |

`ldx 16` = `01 0F`

`jmz 27` = `0D 1B`

#### Constants

|   |   |
|---|---|
|con|#  |

`nor x 1` = `0B 01 01`
