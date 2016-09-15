## Interesting firmware offsets

Firmware seems to be made of blocks, each 4096 bytes long (0x1000).  Interesting things will be aligned along these boundries.  The flash is 511 blocks long.

### 0x000000 (55 blocks)

Firmware position A (first firmware / OEM firmware).

### 0x081000 (1 block)

0x01 0x02 x03 0x04

### 0x082000 (1 block)

Ten byte serial number.

### 0x083000 (1 block)

A copy of the serial number.

### 0x085000 (1 block)

Some sort of key?  51 bytes of information.

### 0x086000 (1 block)

GID table?

### 0x087000 (55 blocks)

Firmware position B (field upgraded firmware).

### 0x0DC000 (1 block)

Firmware position B offset?  Possibly contains other information.

### 0x0DD000 (1 block)

Copy of 0x0DC000 (firmware position B offset)?

### 0x0DE000 (73 blocks)

Log / event data, highly structured.

### 0x150000

Some sort of data structure.  Diagnostics?

### 0x152000

Some sort of data structure.

### 0x153000

Emergency message templates?

### 0x19A000 (10 blocks)

Some structured data.

### 0x1B1000 (1 block)

Diagnostic data (block 433)

### 0x1B2000 (1 block)

Diagnostic data (block 434)