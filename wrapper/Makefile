

F90 = gfortran
CC = cc
F90FLAGS = -O3 
I_CFITSIO =  -I/home/a.bonaldi/software/cfitsio/include/
L_CFITSIO =  -L/home/a.bonaldi/software/cfitsio/lib -lcfitsio
I_HEALPIX = -I/home/a.bonaldi/software/Healpix_3.31/include/
I_SAMPLER = -I../sampler/
L_HEALPIX =  -L/home/a.bonaldi/software/Healpix_3.31/lib -lhealpix -lgif
LDFLAGS = 
INCLUDE := $(I_HEALPIX)  $(I_CFITSIO) $(I_SAMPLER)
LINK := $(LINK) $(L_HEALPIX) $(L_CFITSIO) $(LDFLAGS) 


OBJ := ../sampler/sampler_io.o  ../sampler/random_modules.o ../sampler/sampler_modules.o wrapper.o  


default: all
all : $(OBJ)
	$(F90) $(F90FLAGS) -o ../bin/wrapper $(OBJ) $(LINK) 

%.o : %.f90
	$(F90) $(F90FLAGS) $(INCLUDE) -o $@ -c $<

clean: rm *.o
