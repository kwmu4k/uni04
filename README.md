## uni04
uni04 (or uni.4) is a 4-bit architecture made for [Alex's 4-bit arch challenge](http://207.180.202.42/common/events/4bit-1.html)!

### Instructions

| Bytecode | Instruction | Arguments     | Behaviour    |
| -------- | ----------- | ------------- | ------------ |
| 0        | imm         | reg con       |              |
| 1        | lda         | adr           |              |
| 2        | ldb         | adr           |              |
| 3        | ldi         | reg adr reg   | <img src="scrunkly.jpg" width="300" height="20"> |
| 4        | sta         | adr           |              |
| 5        | stb         | adr           |              |
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
mov a b    // Hmmm comment
lda 7      // meow :3
ldi b 21 a
```

As you can see instead of `;` you use `//` and there are no `,` unlike most ASMs

### How types in bytecode are encoded

#### Registers

| | |
|-|-|
|a|0|
|b|1|

`mov a b` = `6 0 1`

`imm a 8` = `0 0 8`

#### Addreses

|  |  |
|--|--|
|##|##|

`lda 16` = `1 0F`

`jmz 27` = `D 1B`

#### Constants

| | |
|-|-|
|#|#|

`nor b 1` = `B 1 1`
