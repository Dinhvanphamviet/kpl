CC = gcc
CFLAGS = -std=c11 -Wall -Wextra
TARGET = symtab.exe
SOURCES = main.c symtab.c debug.c
HEADERS = symtab.h debug.h

ifeq ($(OS),Windows_NT)
SHELL := powershell.exe
.SHELLFLAGS := -NoProfile -Command
endif

.PHONY: all run clean

all: $(TARGET)

$(TARGET): $(SOURCES) $(HEADERS)
	$(CC) $(CFLAGS) $(SOURCES) -o $(TARGET)

run: $(TARGET)
ifeq ($(OS),Windows_NT)
	.\$(TARGET)
else
	./$(TARGET)
endif

clean:
ifeq ($(OS),Windows_NT)
	if (Test-Path -LiteralPath '$(TARGET)') { Remove-Item -LiteralPath '$(TARGET)' }
else
	rm -f $(TARGET)
endif
