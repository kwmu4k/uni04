# uni04

uni04 (or uni.4) is a 4-bit architecture made for [Alex's 4-bit arch challenge](http://207.180.202.42/common/events/4bit-1.html)

```
  v ALU
┌──┬─┐
│  │ │ <- Registers
│  │ │
├──┴─┤
└────┘
  ^ Control Unit
```

## Instructions

| Opcode | Instruction | Arguments     | Description                      |
| ------ | ----------- | ------------- | -------------------------------- |
| 00     | imm         | reg con       | Immediate value                  |
| 01     | ldx         | adr           | Load `adr` into X                |
| 02     | ldy         | adr           | Load `adr` into Y                |
| 03     | ldi         | reg adr reg   | Indexed load                     |
| 04     | stx         | adr           | Store X into `adr`               |
| 05     | sty         | adr           | Store Y into `adr`               |
| 06     | mov         | reg reg       | Move value from `reg`1 to `reg`2 |
| 07     | add         | reg reg       | `reg`1 += `reg`2                 |
| 08     | sub         | reg reg       | `reg`1 -= `reg`2                 |
| 09     | shr         | reg con       | Shift right `reg` by `con`       |
| 0A     | not         | reg           | Bitwise NOT on `reg`             |
| 0B     | nor         | reg con       | Bitwise NOR on `reg` by `con`    |
| 0C     | jmp         | adr           | Jump to `adr`                    |
| 0D     | jmz         | adr           | Jump to `adr` if zero            |
| 0E     | cal         | adr           | Call subroutine                  |
| 0F     | ret         |               | Return from subroutine           |

## ASM syntax example

```
mov x y    // Hmmm comment
ldx 7      // meow :3
ldi x 21 a
```

As you can see instead of `;` you use `//` and there is no `,` unlike most ASMs

## Turning into opcode

### Registers

| | |
|-|-|
|x|0|
|y|1|

`mov x y` = `06 00 01`

`imm x 8` = `00 00 08`

### Addreses (8-bit)

|   |   |
|---|---|
|adr|## |

`ldx 16` = `01 0F`

`jmz 27` = `0D 1B`

### Constants

|   |   |
|---|---|
|con|#  |

`nor x 1` = `0B 01 01`
