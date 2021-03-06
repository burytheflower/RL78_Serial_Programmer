About
=====

This is PC software to program RL78 microcontrollers via serial bootloader.
This version can not set any security mode. Only S-record image files are
accepted as input files. RL78/G10 parts can programmed only in 1-wire mode,
other RL78 parts support both 1-wire and 2-wire modes. Reset signal is
controlled by DTR or RTS signal.

Usage examples
==============

$ rl78flash -viva /dev/ttyUSB0 R5F100SL.mot

See also output from 
$ rl78flash -h

Rewrite MCU with RESET pin acting as GPIO
-----------------------------------------

If RESET pin of MCU is acting as GPIO it is no longer possible to enter
bootloader mode without additional user actions. To enter bootloader
mode it nessesary to power up MCU with RESET pin tied to ground.

Procedute to rewrite such microcontrollers:
1. power down MCU
2. start rl78flash tool with -d argument
  $ rl78flash -diva /dev/ttyUSB0 firmware.mot
3. wait till message "Turn MCU's power on and press any key..."
4. power up MCU
5. press any key
6. done.

License
=======

The MIT License (MIT)
Copyright (c) 2012-2014 Maksim Salau

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.