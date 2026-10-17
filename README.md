# cpp

## 1. Компиляторы
```
g++                                   # Компилятор кросплатформенный
clang                                 # Компилятор MacOS
MSVC                                  # Компилятор Windows
```

## 2. Автоматизация сборки
```
qmake                                 # Создают makefile
cmake                                 # Создают makefile. Путь: /opt/homebrew/bin/cmake
make <цель>                           # Читает готовый Makefile и вызывает компилятор g++ или clang
nmake                                 # Читает готовый Makefile и вызывает компилятор MSVC
```

## 3. Компиляция
```
g++ -c square.cpp                     # Компиляция .cpp-файла в объектный файл square.o, содержащий машинный код
g++ -O2 -c square.cpp                 # Компиляция с оптимизацией второго уровня, по-умолчанию 0
g++ -o my_program main.o square.o.    # Компоновка (линковка) нескольких объектных файлов в исполняемый файл
MinGW                                 # Набор инструментов для разработки C++ под Windows, содержит g++, cdb.exe, mingw32-make
ar rc libsquare.a square.o            # Создать библиотеку libsquare.a из square.o
g++ -o my_program main.o -L. -lsquare # Подключение библиотеки
valgrind ./my_program                 # valgrind используется, в частности, для поиска утечек памяти и других проблем с памятью.
```

## 3. Методы
```
void foo(int x);                        # При передаче по значению аргумент копируется
void foo(const int& x);                 # Передача по ссылке
void foo(const int* x);                 # Передача по указателю
using fooptr = void(*)(int);            # Указатель на функцию
void prc(fooptr foo);                   # Функция, принимающая callback
[список захвата](список параметров) {}  # Лямбда-функция, [=] - захват по значению, [&] - захват по ссылке
```


## 4. Как собрать qscintilla на Windows c помощью MSVC
```
Открываем Developer Command Prompt
cd src
qmake
nmake
nmake install

qmake CONFIG+=debug qscintilla.pro
nmake -f Makefile.Debug
```

## 5. Компоненты для QT
```
qt creator
CDB debugger (только для Windows)
Qt 6.12.0
  - MSVC 2022 64-bit or MacOS
Ninja
```

## 6. Скопировать библиотеки QT в папку
```
macdeployqt MyApp.app -dmg  # Для MacOS выполнить из папки build, создаст dmg
windeployqt6 MyApp.app.     # Для Windows выполнить из папки build, будет папка со всеми зависимостями и exe. Папку можно перемещать на другие компы
Остальные библиотеки нужно самостоятельно скопировать в папку или пакет .app/frameworks
```

## 7. Продажа приложения физ.лицу или юр.лицу
```
1. Подключаем платежные сервисы (YooKassa итд)
2. После оплаты можно скачать файл .lic и положить его рядом с exe и dmg
3. Приложение читает файл .lic и активируется
```
