include ../Makefile.header

LDFLAGS	+= -Ttext 0

all: bootsect setup

bootsect: bootsect.s
	@$(AS) -32 -o bootsect.o bootsect.s
	@$(LD) $(LDFLAGS) -o bootsect bootsect.o
	@$(OBJCOPY) -R .pdr -R .comment -R.note -S -O binary bootsect


setup: setup.s
	@$(AS) -32 -o setup.o setup.s
	@$(LD) $(LDFLAGS) -o setup setup.o
	@$(OBJCOPY) -R .pdr -R .comment -R.note -S -O binary setup

head.o: head.s
	@$(AS) -32 -o head.o head.s

clean:
	@rm -f bootsect bootsect.o setup setup.o head.o
