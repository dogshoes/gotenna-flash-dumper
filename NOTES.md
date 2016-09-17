## Flash memory layout

The goTenna flash memory is made up of 4096 byte chunks, or "blocks", along which data is aligned.  511 of these blocks can be read from the goTenna device, one block short of the theoretical 512 4096k blocks contained in the 16 Mbit onboard flash.

### Block 0 to 84

Firmware position A (first firmware / OEM firmware).

### Block 129

Magic constant?  0x01020304

### Block 130

Ten byte serial number.

### Block 131

A duplicate of block 130.

### Block 133

Some sort of key?  51 bytes of information.

### Block 134

Appears to be the GID table.

### Block 135 to 182

Firmware position B (field upgraded firmware).  Real flash reservation is likely longer than this, perhaps up to block 220.

### Block 220

Firmware position B offset?  Possibly contains other information?

### Block 221

A duplicate of block 221.

### Block 222 to 335

Log / event data, highly structured.

### Block 336

Some sort of data structure.  Diagnostics?  Readable text included.

### Block 337

Some sort of data structure.

### Block 338

A duplicate of block 337.

### Block 339 to 340

Emergency message templates?

### Block 433

Diagnostic data (block 433)

### Block 434

Diagnostic data (block 434)