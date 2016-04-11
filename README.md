This script is a wrapper for mdb tool by Microchip. mdb_flash.py makes it easier
to automate flash process.

You might want to read a blog post which explains the complete story about
challenges I faced during the implementation:
   [Auto-program with PICkit3 + mdb fails (but I got it working)](http://dmitryfrank.com/blog/2015/1007_auto-program_with_pickit3_mdb_fails_but_i_got_it_working)

Example usage:

```
python -u ./mdb_flash.py \
   --hex="/path/to/file.hex" \
   --mdb-path="/opt/microchip/mplabx/v3.10/mplab_ide/bin/mdb.sh" \
   --mcu="PIC18F87K90" \
   --hwtool="ICD3" \
   --hwtool-serial="JIT140210129"
```

If you have just a single tool of specified type attached to USB (in the
example above, just a single ICD3), you can omit the `--hwtool-serial` option.

The `-u` option to python means "unbuffered"; it's needed to always get output
from the underlying mdb tool immediately.
