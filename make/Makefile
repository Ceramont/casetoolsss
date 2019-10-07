CC=gcc
CFLAGS=  -Wall -O3 -march=native -mtune=native
LDFLAGS= -s
SOURCES= prog.c lib.c
HEADERS= lib.h
OBJECTS= $(SOURCES:.c=.o)
EXECUTABLE= hello

all: test $(SOURCES) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS) 
	@$(CC) $(CFLAGS) -o $(EXECUTABLE) $(OBJECTS)

$(OBJECTS):$(SOURCES)
	@$(CC) $(CFLAGS) -c $(SOURCES)

test: $(EXECUTABLE)
	@./$(EXECUTABLE)
install:
	@install ./hello /home/01/sogolovs/Seti

tar:
	@tar -cf hello.tar $(SOURCES) $(HEADERS) Doxyfile

doc:
	@doxygen Doxyfile

clean:
	rm -f $(OBJECTS) $(EXECUTABLE)

cleanobject:
	rm -f $(OBJECTS)
	
cleanexecutable:
	rm -f $(EXECUTABLE)

help:
	@echo "make - собирает программу в текущей директории" 
	@echo "make install- устанавливает программу" 
	@echo "make clean - удаляет объектные файлы и исполняемый файл"
	@echo "make cleanobject - удаляет объектные файлы"
	@echo "make cleanexecutable - удаляет исполняемый файл"
	@echo "make doc - создание документации"
	@echo "make tar - создание дистрибутива"
wc:
	 @wc -l lib.c
