CC = gcc
CFLAGS ?= -std=c11

TARGET = main.exe
SOURCES = main.c parser.c scanner.c reader.c token.c charcode.c error.c symtab.c debug.c
HEADERS = $(wildcard *.h)
INPUT ?= tests/example6.kpl

.PHONY: all run
all: $(TARGET)

$(TARGET): $(SOURCES) $(HEADERS)
	$(CC) $(CPPFLAGS) $(CFLAGS) $(LDFLAGS) -o $@ $(SOURCES) $(LDLIBS)

run: $(TARGET)
	./$(TARGET) "$(INPUT)"
