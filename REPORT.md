## Name: Jonathan Setiabudi
## Email: jseti007@ucr.edu
## Part 1: Bugs
The lab  was pretty straight forward. The only difficulties was because we went from a Harvard to a Von Neumann Architecture in the Digital file. We also have to convert memory addresses down to 8 bytes, and even though Allan described this before the lab I forgot to apply it. There was also the small mix up where I mixed up my splitters so the 9-2 and the 7-0 were switched. Additionally I had a occillation due to a tunneling mistake, where I had an infinite cycle back into the addition ALUs for the program counter. This was solved with the help of Allan by removing the input tunnel and having it directly connected to the PC instead.

## Part 2: 
### Trace
**Instruction:** lw $v0 31($zero)


**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------:|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0    |
| `$a0`   | 4        | 0    |
| `$a1`   | 5        | 0    |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |


**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x00000000 |



<br>**Instruction:** add $v1 $v0 $v0


**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------:|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0    |
| `$a1`   | 5        | 0    |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |



**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x00000000 |


<br>**Instruction:** sw $v1 132($zero)



**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------:|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0    |
| `$a1`   | 5        | 0    |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |


<br>**Instruction:** sw $v1 132($zero)


**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0    |
| `$a1`   | 5        | 0    |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |


<br>**Instruction:** sub $a0 $v1 $v0


**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0    |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** addi $a1 $v1 12


**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0    |
| `$a3`   | 7        | 0    |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** and $a2 $a1 $v1

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x04 |
| `$a3`   | 7        | 0    |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** or $a3 $a2 $v0

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x04 |
| `$a3`   | 7        | 0x56 |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** nor $t0 $a2 $v0

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x04 |
| `$a3`   | 7        | 0x56 |
| `t0`    | 8        | 0xA9 |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** slt $a2 $a1 $a0

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x01 |
| `$a3`   | 7        | 0x56 |
| `t0`    | 8        | 0xA9 |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |


<br>**Instruction:** beq $a2 $zero -8

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x01 |
| `$a3`   | 7        | 0x56 |
| `t0`    | 8        | 0xA9 |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000AC |

<br>**Instruction:** lw $t0 132($zero)

**Register File**
|Reg. Name|Reg. Addr.|Value |
|---------|---------|------|
| `$zero` | 0        | 0    |
| `$at`   | 1        | 0    |
| `$v0`   | 2        | 0x56 |
| `$v1`   | 3        | 0xAC |
| `$a0`   | 4        | 0x56 |
| `$a1`   | 5        | 0x62 |
| `$a2`   | 6        | 0x01 |
| `$a3`   | 7        | 0x56 |
| `t0`    | 8        | 0xA9 |

**RAM**
|Address|Value       |
|------:|------------|
|31     | 0x00000056 |
|132    | 0x000000A9 |

### Assembly
0000 0001 0010 1010 0100 0000 0010 0100 = 0x012A4024


0010 0001 1000 1011 0000 0000 0111 1011 = 0x218B007B


1000 1101 0010 1101 0000 0000 1000 0111 = 0x8D2D0088


1010 1101 0010 1011 0000 0000 1000 1000 = 0xAB2B0088


0001 0000 0000 1011 1111 1111 1111 0110 = 0x100BFFF6