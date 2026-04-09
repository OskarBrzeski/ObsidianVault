# Usage
## Simple Example
```makefile
build: example.o main.c
	gcc -o main example.o
	
example.o: example.c example.h
	gcc -c example.c
```
## Variables
```makefile
LIBS = -I./libs/ -L./libs/ -lexamplelib

build: main.c
	gcc -o main main.c ${LIBS}
```