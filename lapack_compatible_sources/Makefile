
# Defintions of variables.

CC      = gcc
CCFLAGS = -O -fopenmp
LD      = gcc
LDFLAGS = -O -fopenmp

# Defintions of rules.

simple_test.x : simple_test.o NoFLA_UTV_WY_blk_var2.o
	$(LD) $(LDFLAGS) \
            -o simple_test.x \
            simple_test.o \
            NoFLA_UTV_WY_blk_var2.c \
            /usr/local/lapack/liblapack_340_p4b64_gf.a \
            /usr/local/lapack/mt_openblas/lib/libopenblas_haswellp-r0.2.14.a \
            -lgfortran -lm

simple_test.o : simple_test.c
	$(CC) $(CCFLAGS) -O -fopenmp -c simple_test.c

%.o : %.c
	$(CC) $(CCFLAGS) -c $< -o $@

clean: 
	rm -f a.out *.x *.o *~ core

