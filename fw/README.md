#Silta - Python to STM32F4 Bridge Project

## Firmware Build instructions

Make sure you have the arm-none-eabi(gcc, etc...) tools installed: https://launchpad.net/gcc-arm-embedded

Running make on the top directory should build both the driver library, support files, and main.c
Output files are in the build/ directory

## Programming instructions (using openOCD and gdb)

Connect using openOCD and the included configuration file.
`$ openocd -f stm32f4xx-openOCD.cfg`

On a separate terminal window, run arm-none-eabi-gdb
`$ arm-none-eabi-gdb`

Connect to openOCD
`(gdb) target extended-remote localhost:3333`

Load program the stm32f4xx
`(gdb) file build/silta.elf`
`(gdb) load`

To run you program:
`(gdb) continue`