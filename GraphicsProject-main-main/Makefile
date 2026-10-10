CXX ?= g++
CXXFLAGS ?= -std=c++17 -O2

SRC_DIR := src
TARGET := app
SOURCES := $(SRC_DIR)/glad.c $(SRC_DIR)/font8x8.cpp $(SRC_DIR)/main.cpp

UNAME_S := $(shell uname -s)

ifeq ($(UNAME_S),Darwin)
    CXXFLAGS += -I/opt/homebrew/include -I/usr/local/include
    LDFLAGS += -L/opt/homebrew/lib -L/usr/local/lib
    LDLIBS += -lglfw -lm -framework OpenGL -framework Cocoa -framework IOKit -framework CoreVideo
else
    LDLIBS += -lglfw -lGL -lm -ldl
endif

INCLUDES := -Iinclude -Iinclude/GLFW -Iinclude/glad

.PHONY: all build run clean

all: build

build: $(TARGET)

$(TARGET): $(SOURCES)
	$(CXX) $(CXXFLAGS) $(INCLUDES) $(SOURCES) $(LDFLAGS) $(LDLIBS) -o $(TARGET)

run: build
	./$(TARGET)

clean:
	rm -f $(TARGET)
