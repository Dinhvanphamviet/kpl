CC = gcc
CFLAGS = -std=c11 -Wall -Wextra
LDFLAGS =
LDLIBS =

SOURCES = main.c parser.c scanner.c reader.c token.c charcode.c error.c
HEADERS = reader.h parser.h scanner.h token.h charcode.h error.h
FILE ?= Test/example1.kpl

ifeq ($(OS),Windows_NT)
SHELL := powershell.exe
.SHELLFLAGS := -NoProfile -NonInteractive -Command
TARGET = parser.exe
RUN = .\$(TARGET)
else
TARGET = parser
RUN = ./$(TARGET)
endif

.PHONY: all run clean

all: $(TARGET)

$(TARGET): $(SOURCES) $(HEADERS) Makefile
	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ $(SOURCES) $(LDLIBS)

# Example: make run FILE=Test/example2.kpl
run: $(TARGET)
	$(RUN) "$(FILE)"

clean:
ifeq ($(OS),Windows_NT)
	if (Test-Path -LiteralPath "$(TARGET)") { Remove-Item -LiteralPath "$(TARGET)" }
else
	rm -f $(TARGET)
endif
