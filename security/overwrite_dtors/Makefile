CC=gcc
AS=as
LD=ld
CFLAGS= -O0 -fno-stack-protector -D_FORTIFY_SOURCE=0 -z norelro -z execstack
# -fno-stack-protector: disable stack protection
# -D_FORTIFY_SOURCE=0: disable string vuls and buffer checks

LIBS =

APP = getenvaddr fmt_vuln gen_shellcode rop_vuln

all: $(APP)
	@echo "done"


getenvaddr: getenvaddr.c
	$(CC) $(CFLAGS) -o $@ $^

fmt_vuln: fmt_vuln.c
	$(CC) $(CFLAGS) -o $@ $^

gen_shellcode: gen_shellcode.c
	$(CC) $(CFLAGS) -o $@ $^

rop_vuln: rop_vuln.c
	$(CC) $(CFLAGS) -o $@ $^
	$(CC) $(CFLAGS) -o dummy system.c

clean:
	rm -f *.o $(APP) shellcode.bin
