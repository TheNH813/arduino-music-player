This project is a music player for the Arduino using the .MOD, .S3M, .XM and .IT file formats. It converts them into a special compressed format that fits into the Arduino's flash memory more easily and plays them. Disconnect output speakers/amiplifier when uploading the code or you'l hear the data transfer. You will need to connect a Resistor DAC across pins 0,1,2,3,4,5,6 and 7 with pin 0 being the least signifigant bit. I reccommend a R2R Ladder for best sound quality, but you could also use resistors of doubling value. Anything within about 15% tolerance of being double the resistor before it should work. If the module file contains a loop, instead of repeating the whole file, it repeats from that point.

To create files for this program, make sure that the modules are under 56KiB or they nmay not fit. Compressing the samples to lower quality may help. The Arduino UNO only has 32KiB of memory, 2-3 KiB are used by the bootloader, 5KiB by the code of the main PMF Player program, and the rest is needed for the actual audio samples and tracker-type audio data. Use the program found in ./pmf_converter/bin/pmf_converter.exe to convert the files. Type the command like this "pmf_converter.exe -hex -i </path/to/module.mod/.s3m/.xm/.it> -o </path/to/output.pmf>.  I have confirmed it works flawlessly on Wine for Linux systems like I use. I may add a makefile and adapt the program to build natively on Linux. Open the file in Geany/Notepad++ or a similar program and copy the contents. Paste them into the main pmf_player.ino file, replacing the existing hexidecimal data in the variable named s_pmf_file.

There was a problem in the original code making it impossible to compile the program in newer versions of the Arduino IDE, or on Arduino UNO boards in any version of the IDE. All it required was changing which register was used in an operation. In the future, I will be most likely making small modifications to improve performance. This is, however, after I become more experienced in programming for the Arduino.

I'm new to GitHub, this will be the first time I ever fork a project. If I did something wrong, please tell me.

*** This project is originally created by JarkkoPFC ***
