SHELL := powershell.exe
.SHELLFLAGS := -NoProfile -NonInteractive -Command

CC := gcc
CFLAGS := -std=c11 -Wall -Wextra
TARGET := scanner.exe
INPUT ?= test/example2.kpl
SOURCES := scanner.c reader.c charcode.c token.c error.c
HEADERS := reader.h charcode.h token.h error.h

.PHONY: all run clean

all: $(TARGET)

$(TARGET): $(SOURCES) $(HEADERS)
	$(CC) $(CFLAGS) $(SOURCES) -o $(TARGET); exit $$LASTEXITCODE

# Override INPUT to scan another source file.
run: $(TARGET)
	& '.\$(TARGET)' '$(INPUT)'; exit $$LASTEXITCODE

clean:
	if (Test-Path -LiteralPath '$(TARGET)') { Remove-Item -LiteralPath '$(TARGET)' -Force }
