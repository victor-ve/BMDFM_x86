# Makefile

#==============================================================================
# x86 UnixWare, SCO CCS C
#------------------------------------------------------------------------------
CC = cc -Kthread
OPTIONS = -O3
#==============================================================================

MATH = -lm

all: cflp_udf.o fastlisp BMDFMldr BMDFMsrv CPUPROC

cflp_udf.o: cflp_udf.c cflp_udf.h
	$(CC) $(OPTIONS) -c cflp_udf.c

fastlisp: fastlisp.o cflp_udf.o
	$(CC) -o fastlisp fastlisp.o cflp_udf.o $(MATH)

BMDFMldr: BMDFMldr.o cflp_udf.o
	$(CC) -o BMDFMldr BMDFMldr.o cflp_udf.o $(MATH)

BMDFMsrv: BMDFMsrv.o cflp_udf.o
	$(CC) -o BMDFMsrv BMDFMsrv.o cflp_udf.o $(MATH)

CPUPROC: CPUPROC.o cflp_udf.o
	$(CC) -o CPUPROC CPUPROC.o cflp_udf.o $(MATH)

clean:
	rm -f cflp_udf.o fastlisp BMDFMldr BMDFMsrv CPUPROC 2>/dev/null

