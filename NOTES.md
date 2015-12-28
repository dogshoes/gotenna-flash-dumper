## Interesting firmware offsets

Firmware seems to be made of blocks, each 4096 bytes long (0x1000).  Interesting things will be aligned along these boundries.  The flash is 511 blocks long.

### 0x000000 (55 blocks)

Firmware position A (first firmware / OEM firmware).

### 0x0258E7

Interesting pattern.  Something to look at.  Is not block aligned!  Might just be filler.

### 0x081000 (1 block)

0x01 0x02 x03 0x04

### 0x082000 (1 block)

Ten byte serial number.

### 0x083000 (1 block)

A copy of the serial number.

### 0x087000 (55 blocks)

Firmware position B (second firmware).

### 0x0DC000 (1 block)

Firmware position B offset?

### 0x0DD000 (1 block)

Firmware position B offset copy?

### 0x0DE000 (73 blocks)

Log / event data, highly stuctured.

### 0x19A000 (10 blocks)

Some structured data.

### 0x1B1000 (1 block)

Diagnostic data (block 433)

### 0x1B2000 (1 block)

Diagnostic data (block 434)
