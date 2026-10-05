# cpp

## 1. Основное
```
g++                                   # Компилятор кросплатформенный
clang                                 # Компилятор MacOS
MSVC                                  # Компилятор Windows
g++ -c square.cpp                     # Компиляция .cpp-файла в объектный файл square.o, содержащий машинный код
g++ -O2 -c square.cpp                 # Компиляция с оптимизацией второго уровня, по-умолчанию 0
g++ -o my_program main.o square.o.    # Компоновка (линковка) нескольких объектных файлов в исполняемый файл
MinGW                                 # Набор инструментов для разработки C++ под Windows, содержит g++, cdb.exe, mingw32-make
ar rc libsquare.a square.o            # Создать библиотеку libsquare.a из square.o
g++ -o my_program main.o -L. -lsquare # Подключение библиотеки
qmake, cmake                          # Системы автоматизации сборки, создают makefile
make <цель>                           # Читает готовый Makefile и вызывает компилятор g++ или clang
nmake                                 # Читает готовый Makefile и вызывает компилятор MSVC
valgrind ./my_program                 # valgrind используется, в частности, для поиска утечек памяти и других проблем с памятью.
```

---

## 2. Методы
```
void foo(int x);                        # При передаче по значению аргумент копируется
void foo(const int& x);                 # Передача по ссылке
void foo(const int* x);                 # Передача по указателю
using fooptr = void(*)(int);            # Указатель на функцию
void prc(fooptr foo);                   # Функция, принимающая callback
[список захвата](список параметров) {}  # Лямбда-функция, [=] - захват по значению, [&] - захват по ссылке
```


## 3. Как собрать qscintilla на Windows c помощью MSVC
```
Открываем Developer Command Prompt
cd src
qmake
nmake
nmake install

qmake CONFIG+=debug qscintilla.pro
nmake -f Makefile.Debug
```

## 4. Компоненты для QT
```
qt creator
CDB debugger
Qt 6.12.0
  - MSVC 2022 64-bit
  - Qt Debug Information Files
CMake
Ninja
```
