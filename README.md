## 🧱 1. Creational Patterns

### [1.1] Factory Design Pattern  
**Purpose:** Creates objects without specifying the exact class/type.

**Real-Life Analogy:**  
You go to a **vehicle factory** and say you want a "Bike" or "Car". You don’t care how it’s made, just that it returns the appropriate vehicle.

### oled_display
**cd ~** 
**wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.71.tar.gz** 
tar zxvf bcm2835-1.71.tar.gz
cd bcm2835-1.71
./configure
make
sudo make install

g++ -I../include -c src/HELLO_WORLD/main.cpp -o obj/main.o

g++ -o bin/test obj/main.o -lbcm2835 -L/usr/local/lib -I/usr/local/include -L/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 -lSSD1306_OLED_RPI



g++ -I../include src/HELLO_WORLD/main.cpp -o obj/main.o -lbcm2835 -L/usr/local/lib -I/usr/local/include -L/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 -lSSD1306_OLED_RPI


pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1 $ ln -s libSSD1306_OLED_RPI.so.1.0 libSSD1306_OLED_RPI.so.1
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1 $ export LD_LIBRARY_PATH=/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1:$LD_LIBRARY_PATH
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1 $ cd -
/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1/examples/bin
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1/examples/bin $ ./test
OLED Test Begin
Error 1202: bcm2835_i2c_begin :Cannot start I2C, Running as root?
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1/examples/bin $ sudo ./test
./test: error while loading shared libraries: libSSD1306_OLED_RPI.so.1: cannot open shared object file: No such file or directory
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1/examples/bin $ sudo LD_LIBRARY_PATH=/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 ./test
OLED Test Begin
SSD1306 library Version Number :: 161
bcm2835 library Version Number :: 10071
^C
pi@raspberrypi:~/projects/oled_display/SSD1306_OLED_RPI-1.6.1/examples/bin $ sudo LD_LIBRARY_PATH=/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 ./test
OLED Test Begin
SSD1306 library Version Number :: 161
bcm2835 library Version Number :: 10071





=======================================Test Before CPP development===================================
use below link to test oled and i2c connection:-
https://www.raspberrypi-spy.co.uk/2018/04/i2c-oled-display-module-with-raspberry-pi/
