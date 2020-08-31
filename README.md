# The-FakePrinter
Print everything you want with your Game Boy Printer !

This project provide an easy solution to hack the Game Boy Printer. You just need an Arduino and SD shield plus some soldering. The code is divided into two parts : a converter ran with Octave/Matlab to transform any image that fits the format of a GameBoy printed image (160 pixels width, multiple of 16 pixel height, 4 shades of gray) into a tile format.

To choose wich file to convert, simply modify this line in Image_converter.m

    a=imread('GB.png');

Details of the image to tile transformation which is a bit tricky are exposed here for example :
https://blog.flozz.fr/2018/11/19/developpement-gameboy-5-creer-des-tilesets/

Octave converter generate Hex_data.txt whick containes the tiles encoded in hexadecimal. This file must then be uploaded on SD card. It will then be interpreted as a Game Boy Printer protocol by the Arduino code. Example of Game Boy Printer protocol can be found here : 
https://gbdev.gg8.se/wiki/articles/Gameboy_Printer

The protocol followed by the Arduino is the following :
![Game Boy Printer Protocol](https://github.com/Raphael-Boichot/The-FakePrinter/blob/master/Illustrations/Printing_protocol.PNG)

The printing is automatic once the Arduino is powered, connected to the Game Boy Printer swiiched on. Rebooting the Arduino causes another print.
You can also print images from Game Boy Camera or images extracted from games with this code :
https://github.com/mofosyne/arduino-gameboy-printer-emulator

Be careful, the default pinout may vary (to adapt depending on your particular SD shield setting).
![Game Boy Printer to Arduino Uno pinout](https://github.com/Raphael-Boichot/The-FakePrinter/blob/master/Illustrations/Pinout.PNG)

Have fun with it !!!

![Printing a Game Boy Camera image](https://github.com/Raphael-Boichot/The-FakePrinter/blob/master/Illustrations/Printing_Example2.PNG)
![Printing a random image](https://github.com/Raphael-Boichot/The-FakePrinter/blob/master/Illustrations/Printing_Example.PNG)
![Printing a custom banner](https://github.com/Raphael-Boichot/The-FakePrinter/blob/master/Illustrations/Printing_Example3.PNG)
