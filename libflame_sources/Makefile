
# Defintions of variables.

LIBFLAME_PATH = /usr/local/libflame-current-gc

CC      = gcc
CCFLAGS = -O -fopenmp -I$(LIBFLAME_PATH)/include-x86_64-r -msse3
LD      = gcc
LDFLAGS = -O -fopenmp -I$(LIBFLAME_PATH)/include-x86_64-r -msse3

# Defintions of rules.

simple_test.x : simple_test.o FLA_UTV_UT_blk_var1.o
	$(LD) $(LDFLAGS) \
            -o simple_test.x \
            simple_test.o \
            FLA_UTV_UT_blk_var1.o \
            -L$(LIBFLAME_PATH)/lib -lflame-x86_64-r  \
            /usr/local/lapack/liblapack_340_p4b64_gf.a \
            /usr/local/lapack/mt_openblas/lib/libopenblas_haswellp-r0.2.14.a \
            -lgfortran -lm

simple_test.o : simple_test.c
	$(CC) $(CCFLAGS) -c simple_test.c

%.o : %.c
	$(CC) $(CCFLAGS) -c $< -o $@

clean: 
	rm -f a.out *.x *.o *~ core

