## Windows
`usbipd list` -> Remember the BUSID of the appropriate COM port
`usbipd bind -b <BUSID>` -> Share the BUSID with the WSL Subsystem
`usbipd attach --auto-attach --busid <BUSID> --wsl` -> permanently attach the BUSID to the WSL Subsystem

## WSL2
`cd proxmark3`
`./pm3`
`auto` -> to test all possible cardtypes
