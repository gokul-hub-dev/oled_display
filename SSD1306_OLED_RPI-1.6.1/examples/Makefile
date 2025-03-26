## Gavin Lyons 06-2021 
# Makefile to build example program for SSD1306_OLED_RPI library.
# URL: https://github.com/gavinlyonsrepo/SSD1306_OLED_RPI

# ************************************************
# User SRC directory Option Section
# Pick on example "SRC" dir path and ONE Only.
# Comment out the other's. 

SRC=src/HELLO_WORLD
#SRC=src/BITMAP
#SRC=src/CLOCK_DEMO
#SRC=src/OLED_FUNCTIONS
#SRC=src/SPEED_TEST
#SRC=src/TEXT_GRAPHICS
#SRC=src/I2C_TEST
# ************************************************


# ********************
# Options
# 1. make  
# 2. make clean
# 3. make run 
# ********************

CC=g++
LDFLAGS= -L/usr/local/lib -lbcm2835
CFLAGS = -I/usr/local/include
#LDFLAGS= -l./../SSD1306_OLED_RPI 
#LDFLAGS= -L/usr/local/lib -L/home/pi/projects/oled_display/SSD1306_OLED_RPI-1.6.1 \
         -lbcm2835 -lSSD1306_OLED_RPI -lrt
CFLAGS = -Iinclude/ -c -Wall -Wextra 
CFLAGS = -I../include
MD=mkdir
OBJ=obj
SRCS = $(wildcard $(SRC)/*.cpp)
OBJS = $(patsubst $(SRC)/%.cpp,  $(OBJ)/%.o, $(SRCS))
BIN=./bin
TARGET=$(BIN)/test

all: clean pre-build $(TARGET) 

run:
	sudo $(TARGET)

pre-build:
	@echo '*******'
	@echo '[START!]'
	@echo 'Building: ' $(SRC)
	$(MD) -vp $(BIN)
	$(MD) -vp $(OBJ)


$(TARGET): $(OBJS) $(OBJ)
	@echo '[MAKE EXE FILE!]'
	$(CC)  $(OBJS) -o $@ $(LDFLAGS)
	@echo '[DONE!]'

$(OBJ)/%.o :  $(SRC)/%.cpp   $(OBJ) 
	@echo '[MAKE OBJECT FILE!]'
	$(CC) $(CFLAGS) $< -o  $@ 

clean:
	@echo '*******'
	@echo '[CLEANUP!]'
	rm -vf $(OBJS) $(TARGET)
	@echo '[DONE!]'
