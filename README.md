# doc_eco32


ECO32® Architecture

### 2.1 General purpose registers (GPR)

Bank A

| A0 | ZERO |
| :--- | :--- |
| A1 | VL |
| A2 | ARG0 |
| A3 | ARG1 |
| A4 | ARG2 |
| A5 | ARG3 |
| A6 | ARG4 |
| A7 | ARG5 |
| A8 | (saved) |
| A9 | (saved) |
| A10 | (saved) |
| A11 | (saved) |
| A12 | (saved) |
| A13 | (saved) |
| A14 | (saved) |
| A15 | (saved) |
| A16 | (saved) |
| A17 | (saved) |
| A18 | (saved) |
| A19 | (saved) |
| A20 |  |
| A21 |  |
| A22 |  |
| A23 |  |
| A24 |  |
| A25 |  |
| A26 |  |
| A27 |  |
| A28 | GP |
| A29 | FP |
| A30 |  |
| A31 | LR |
|  |  |


| Bank B |
| :--- |
| B0 ZERO <br> B1 VH (n) <br> B2 (tmp) <br> B3 (tmp) <br> B4 (tmp) <br> B5 (tmp) <br> B6 (tmp) <br> B7 (tmp) <br> B8 (saved) <br> B9 (saved) <br> B10 (saved) <br> B11 (saved) <br> B12 (saved) <br> B13 (saved) <br> B14 (saved) <br> B15 (saved) <br> B16 (saved) <br> B17 (saved) <br> B18 (saved) <br> B19 (saved) <br> B20  <br> B21  <br> B22  <br> B23  <br> B24  <br> B25  <br> B26  <br> B27  <br> B28 KGP <br> B29 KFP <br> B30 KSP <br> B31  <br>   |

### 2.2 Control registers (CR)

Bank A

| CRA0 | Flags |
| :--- | :---: |
| CRA1 | - |
| CRA2 | - |
| CRA3 | - |
| CRA4 | - |
| CRA5 | Counter Lo |
| CRA6 | Processor ID |
| CRA7 | Thread ctx |
| CRA8 | Thread ctx |
| CRA9 | Debug control |
| CRA10 | Debug control |
| CRA11 | SystemTemp |
| CRA12 | System |
| CRA13 | Event Ctrl |
| CRA14 | Event Data Lo |
| CRA15 | SysCall 0 |
| CRA16 | SysCall 1 |
| CRA17 | SysCall 2 |
| CRA18 | SysCall 3 |
| CRA19 | SysCall 4 |
| CRA20 | SysCall 5 |
| CRA21 | SysCall 6 |
| CRA22 | SysEvent |
| CRA23 | RetAddr0 - Int Exc |
| CRA24 | RetAddr1 - Dbg Exc |
| CRA25 - Ext Exc |  |
| CRA26 | JetAddr3 - TLB Exc |
| CRA27 | JP_ADDR0 |
| CRA28 |  |
| CRA29 |  |
| CRA30 | ADDR3 |
| CRA31 |  |
|  | JPd2 |

Bank B

| CRA0 | Flags |
| :--- | :--- |
| CRB1 | reserved |
| CRB2 | reserved |
| CRB3 | reserved |
| CRB4 | reserved |
| CRB5 | reserved |
| CRB6 | Counter Hi |
| CRB7 | Processor CAP |
| CRB8 | Thread param |
| CRB9 | Thread param |
| CRB10 | Debug flags |
| CRB11 | Debug flags |
| CRB12 | SystemTemp |
| CRB13 | System |
| CRB14 | Event Flags |
| CRB15 | Event Data Hi |
| CRB16 | reserved |
| CRB17 | reserved |
| CRB18 | reserved |
| CRB19 | reserved |
| CRB20 | reserved |
| CRB21 | reserved |
| CRB22 | reserved |
| CRB23 | reserved |
| CRB24 | Ret_ISW0 |
| CRB25 | Ret_ISW1 |
| CRB26 | Ret_ISW2 |
| CRB27 | Ret_ISW3 |
| CRB28 | JP_ISW0 |
| CRB29 | JP_ISW1 |
| CRB30 | JP_ISW2 |
| CRB31 | JP_ISW3 |
|  |  |

### 2.3 Flag Register CRAO and CRBO

| 31 | 30 | 29 | 28 | 27 | 26 | 25 | 24 | 23 | 22 | 21 | 20 | 19 | 18 | 17 | 16 | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | $\mathrm{I}$ | $\mathrm{N}$ | $\mathrm{D}$ | - | - | - | - | $\mathrm{S}$ | $\mathrm{O}$ | $\mathrm{C}$ | $\mathrm{Z}$ |

### 2.4 Conditional field

| 31 30 29 28 27 26 | 25 24 | ![](https://cdn.mathpix.com/cropped/2024_02_12_006e9902d1f4354f4cecg-011.jpg?height=60&width=272&top_left_y=705&top_left_x=521) | 18 17 16 15 14 13 12 11 10 9 | 8 7 6 5 4 3 2 1 0 |
| :---: | :---: | :---: | :---: | :---: |
| mopc | 0 | cond |  |  |


| code[3:0] | code[4]==0 | code[4]==1 |
| :---: | :--- | :--- |
| 0000 | ae (always execute) | ne (never execute) |
| 0001 | le (lower or equal) | gt (greater than) |
| 0010 | ge (greater or equal) | It (lower than) |
| 0011 | - | - |
| 0100 | z (zero) | nz (not zero) |
| 0101 | c (carry) | nc (not carry) |
| 0110 | o (overflow) | no (not overflow) |
| 0111 | s (sign) | ns (not sign) |
| 1000 | - | - |
| 1001 | - | - |
| 1010 | - | - |
| 1011 | - | - |
| 1100 | inf (infinity) | ninf (not infinity) |
| 1101 | nan (not a number) | nnan (not (not a number)) |
| 1110 | norm (normalized) | dnorm (denormalized) |
| 1111 | - | - |

### 2.5 Debug Register CRBA10, CRBA11

Registers CRA10, CRA11 and CRB11 are not in use. They are reserved for future debuging purposes.

Writing to register CRB10 can enable or disable sending trace data through debuging port. This register is described below:

| 31 | 30 | 29 | 28 | 27 | 26 | 25 | 24 | 23 | 22 | 21 | 20 | 19 | 18 | 17 | 16 | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | $\mathrm{E}$ |

E - enable debug trace: 0 - disable; 1 - enable

System function dbg_on_inline is used to enable debug mode and to send all registers values through debug port. To do this number of loading operation from general registers to SystemTemp control register (CRBA12) is done.

System function dbg_off_inline is used to disable debug mode.
