# oled_display
cd ~
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.71.tar.gz
tar zxvf bcm2835-1.71.tar.gz
cd bcm2835-1.71
./configure
make
sudo make install

g++ -I../include -c src/HELLO_WORLD/main.cpp -o obj/main.o

g++ -o bin/test obj/main.o -lbcm2835 -L/usr/local/lib -I/usr/local/include -L/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 -lSSD1306_OLED_RPI



g++ -I../include src/HELLO_WORLD/main.cpp -o obj/main.o -lbcm2835 -L/usr/local/lib -I/usr/local/include -L/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 -lSSD1306_OLED_RPI
