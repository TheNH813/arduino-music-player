This project is a music player for the Arduino using the .MOD, .S3M, .XM and .IT file formats. It converts them into a special compressed format that fits into the Arduino's flash memory more easily and plays then on loop. If the module file contains a loop, instead of repeatign the whole file, it repeats fromt hat point.

There was a problem in the original code making it impossible to compile the program in newer versions of the Arduino IDE, or on Arduino UNO boards in any version of the IDE. All it required was changing which register was used in an operation.

I'm new to GitHub, this will be the first time I ever fork a project. If I did something wrong, tell me.

*** This project is originally created by JarkkoPFC ***
