# *nix Makefile for Minimig bootfirmware assembly
# Written by Christian Vogelgsang <chris@vogelgsang.org>

# ----- the following tools need to be installed -----
# vasm homepage http://sun.hasenbraten.de/vasm
ASM=vasmm68k_mot
ASM_OPTS=
HEXER=python ../hexer.py

.PRECIOUS: %.bin

# ----- rules -----
all: amigaboot.hex

clean:
	rm -f amigaboot.hex amigaboot.bin amigaboot.elf
	
%.hex: %.bin
	$(HEXER) -l 2048 $< $@

%.bin: %.asm
	$(ASM) $(ASM_OPTS) -Fbin -o $@ $<
