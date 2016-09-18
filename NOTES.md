## Flash memory layout

The goTenna flash memory is made up of 4096 byte chunks, or "blocks", along which data is aligned.  511 of these blocks can be read from the goTenna device, one block short of the theoretical 512 4096k blocks contained in the 16 Mbit onboard flash.

### Block 0 to 84

Firmware position A (first firmware / OEM firmware).

### Block 129

Magic constant?  0x01020304

### Block 130

Ten byte serial number.  Also likely contains the device type, hardware version.  May also contain the "bluetooth flag", although not entirely sure about that or what bearing that has.  The "dev_info" command includes these fields.

### Block 131

A duplicate of block 130.

### Block 133

Some sort of key?  Does not match what the goTenna claims is its public key.  51 bytes of information.  Value changes when the GID and public key are regenerated.

### Block 134

Appears to be the GID table.

### Block 135 to 182

Firmware position B (field upgraded firmware).  Real flash reservation is likely longer than this, perhaps up to block 219.

### Block 220

Some sort of data structure.

### Block 221

A duplicate of block 221.

### Block 222 to 336

Log / event data, highly structured.  This data is output via the "getlog" command.

### Block 337

Some sort of data structure.

### Block 338

A duplicate of block 337.

### Block 339 to 340

Emergency message templates?

### Block 433

Diagnostic data (block 433)

### Block 434

Diagnostic data (block 434).  Duplicate of block 433?