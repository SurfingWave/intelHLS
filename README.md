# Intel HLS

## Intel Quartus HLS Install on Ubuntu 16.04
+ Install **gcc-4.4.7**: add to `/etc/apt/source.list`
> `deb http://dk.archive.ubuntu.com/ubuntu/ trusty main universe`</br>
`deb http://dk.archive.ubuntu.com/ubuntu/ trusty-updates main universe`</br>
`sudo apt-get update`</br>
`sudo apt-get install gcc-4.4 g++-4.4 g++-4.4-multilib gcc-4.4-multilib`</br>

+ Add shared library related to architecture
>  `sudo dpkg --add-architecture i386` </br> 
    `sudo apt-get update` </br> 
    `sudo apt-get install libxft2:i386 libxext6:i386 libncurses5:i386` </br> 
    `sudo apt-get install libc6:i386` </br> 
    `sudo apt-get install libstdc++6:i386`</br> 
    `sudo apt-get install unixodbc-dev`</br> 
    `sudo apt-get install lib32ncurses5-dev`</br> 
    `sudo apt-get install libzmq3-dev`</br> 

+ Add  ` modelsim `  to system path to find `vsim`;
> Add  `export intelFPGA_lite/18.0/modelsim_ase/linuxaloem`  to the end of `~/.profile`.

+ Move `gcc5.4` library to other place or delete;
> At path `/usr/lib/gcc/x86_64-linux-gnu/` do `sudo mv 5 /home/wyk/Desktop/`

+ Remove all other version of `gcc` the `gcc-*.*-linux` folders from path `intelFPGA_lite/18.0/modelsim_ase`.

## Run
+ `source .profile` make `vsim` visiable;
+ `source path_to_hls/init_hls.sh` initialize the hls environment;
+ in `path_to_hls/examples` using `make [options]` <br/>

| Options |      Meanings      |
|----------|:-------------|
|test-gpp | Compile the component and testbench using g++ and run them as a regular program | 
|test-x86-64 |    Run the testbench and the component as a regular program
|test-fpga | Run a simulation with the C testbench and verilog component|
