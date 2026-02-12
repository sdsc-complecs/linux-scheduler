# Example Problem: Estimate $\pi$ via Monte Carlo

To explore managing procesess and threads with the Linux scheduler, we'll need some example programs to run. Here, we'll use the
[4$\pi$](https://github.com/mkandes/4pi) project, a collection of simple computer programs that estimate the value of $\pi$. 

Each program in the 4$\pi$ collection differs only in the programming language it was written in, the set of features of the
language it utilized, and/or the underlying mathematical algorithm it implemented to approximate the value of $\pi$. The aim of
the project is to explore different aspects of each programming language and their feature sets from a scientific and 
high-performance computing perspective. The first set of programs included in the project estimate the value of $\pi$ via the
Monte Carlo method. This solution is particularly useful for exploring different parallel programming models, languages, 
libraries, and APIs as it is an embarrassingly parallel (albeit inefficient) solution to the problem.

### Clone the Repository

Start by cloning the repository to your local system.

*Command*
  ```
  git clone https://github.com/mkandes/4pi.git
  ```

*Output*
```
$ git clone https://github.com/mkandes/4pi.git
Cloning into '4pi'...
remote: Enumerating objects: 19, done.
remote: Counting objects: 100% (19/19), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 19 (delta 4), reused 19 (delta 4), pack-reused 0
Unpacking objects: 100% (19/19), 5.72 KiB | 977.00 KiB/s, done.
```

### Explore the Repository

Take a look at the code available in the repository. 

```
$ cd 4pi/
$ ls
bash  c  fortran  LICENSE.md  python  README.md
$ ls python/
pi.py
$ ls fortran/
Makefile  pi.f90  pi_omp.f90
$ cat fortran/Makefile 
COMPILER := gfortran
COMPILER_OPTIONS := -ffree-form -ffree-line-length-none -fimplicit-none \
                    -O3 -mtune=native -fdefault-integer-8 -fdefault-real-8

all: pi.x pi_omp.x

pi.x: pi.o
	$(COMPILER) $(COMPILER_OPTIONS) -o pi.x pi.o

pi.o: pi.f90
	$(COMPILER) $(COMPILER_OPTIONS) -c pi.f90

pi_omp.x: pi_omp.o
	$(COMPILER) $(COMPILER_OPTIONS) -fopenmp -o pi_omp.x pi_omp.o

pi_omp.o: pi_omp.f90
	$(COMPILER) $(COMPILER_OPTIONS) -fopenmp -c pi_omp.f90

.PHONY: clean
clean:
	rm *.x *.o
$
```

### Computing $\pi$ with Python

We'll start with `pi.py`, which requires only one command-line argument to be specified at runtime.

*Command*

```
python3 pi.py --help
```

*Output*

```
$ python3 pi.py --help
usage: pi.py [-h] [-v] samples

Estimate the value of Pi via Monte Carlo

positional arguments:
  samples        number of Monte Carlo samples

optional arguments:
  -h, --help     show this help message and exit
  -v, --verbose
$
```

### Estimating $\pi$ for the first time

Start by running `pi.py` with 1M samples, then increase the number of samples used to estimate $\pi$.

*Command* 

```
python3 pi.py 1000000
```

*Output*

```
$ python3 pi.py 1000000
3.14000314000314
$
```
