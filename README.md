# Laser (VTech, Dick Smith, Sanyo Video Technologies, ...) VZ-200 Lazarus Daugher Board

## Background

The PCB quality of these machines is really low, and chances are that you are going to lift pads and/or traces if you should have to replace the ROM chips during a repair: 

![PCB damage]() 

In my case, the PCB got damaged so badly that I opted to create a daughter board replacing the entire memory (RAM, ROM) sub-system on a plugin daughter board. This brought my VZ-200 back to life! 

The daugher board also contains a socket for an optional 32 KB SRAM chip upgrade - `U7` is a `74LS00` NAND gate, and  
`U5` is the 32 KB SRAM chip `CY62256-70PC`. The credit for figuring out how to add this 32 KB RAM expansion
to the VZ-200 goes to [Adrian Black.](https://youtu.be/MnOnCbGJgRE)

You can find the [system ROM images for the two 2764 system ROMs here.](http://www.vz200.org/bushy/software.html) 


## Details 

Remove the 6116 SRAM chips as well as the two ROM chips. As the motherboard is so deli

Also, remove the black bodge wires that refactored the PCB for 24-pin 2364 EPROMS; more details in 
[this excellent repository, which includes recreated readable schematics in KiCAD, and even a diagnostics ROM.](https://github.com/rweather/vz200-restoration) 

Note that you will need three chip select lines from the motherboard, as they are not available from the Z80 CPU socket: `ROM0`, `ROM1`, `78XX`. 
You can grab these from `U3` pin 4, pin 5, and pin 9, respectively - see [page 2 here](https://github.com/rweather/vz200-restoration/blob/main/schematics/VZ200/PDF/VZ200.pdf).

## Gerbers 

The Gerbers are [here.](gerbers/vz200-lazarus.zip) 

## Video

Details can also be found in my [YouTube video.](https://youtu.be/oaSFn2akLK8) 



