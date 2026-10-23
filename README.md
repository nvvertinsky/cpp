# cpp

## 1. Компиляторы
```
g++            # Кроссплатформенный
clang          # MacOS. Путь: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin
MSVC           # Windows
```

## 2. Отладчики
```
CDB debugger   # Windows
LLDB           # MacOS (Clang)
WinDbg         # 
```

## 3. Автоматизация сборки
```
qmake          # Создают makefile
cmake          # Создают makefile. Путь: /opt/homebrew/bin/cmake
```

## 4. Сборка на MacOS
```
cd build       # Переход в папку сборки
cmake ..       # Читает CMakeLists.txt и подготавливает всё необходимое для последующей компиляции программы (Makefile итд)
make           # Читает Makefile и вызывает компилятор
```

## 5. Сборка на Windows (в x64 Native Tools Command Prompt for VS 2022)
```
cd build                            # Переход в папку сборки
cmake -G "NMake Makefiles" ..       # Читает CMakeLists.txt и подготавливает всё необходимое для последующей компиляции программы (Makefile итд)
nmake                               # Читает Makefile и вызывает компилятор
```

## 6. Компиляция
```
g++ -c square.cpp                     # Компиляция .cpp-файла в объектный файл square.o, содержащий машинный код
g++ -O2 -c square.cpp                 # Компиляция с оптимизацией второго уровня, по-умолчанию 0
g++ -o my_program main.o square.o.    # Компоновка (линковка) нескольких объектных файлов в исполняемый файл
MinGW                                 # Набор инструментов для разработки C++ под Windows, содержит g++, cdb.exe, mingw32-make
ar rc libsquare.a square.o            # Создать библиотеку libsquare.a из square.o
g++ -o my_program main.o -L. -lsquare # Подключение библиотеки
valgrind ./my_program                 # valgrind используется, в частности, для поиска утечек памяти и других проблем с памятью.
```

## 7. Методы
```
void foo(int x);                        # При передаче по значению аргумент копируется
void foo(const int& x);                 # Передача по ссылке
void foo(const int* x);                 # Передача по указателю
using fooptr = void(*)(int);            # Указатель на функцию
void prc(fooptr foo);                   # Функция, принимающая callback
[список захвата](список параметров) {}  # Лямбда-функция, [=] - захват по значению, [&] - захват по ссылке
```


## 8. Сборка qscintilla (MSVC)
```
Открываем Developer Command Prompt
cd src
qmake
nmake
nmake install

qmake CONFIG+=debug qscintilla.pro
nmake -f Makefile.Debug
```

## 9. Компоненты для QT
```
qt creator
CDB debugger (только для Windows)
Qt 6.12.0
  - MSVC 2022 64-bit or MacOS
```

## 10. Скопировать библиотеки QT в папку
```
macdeployqt MyApp.app -dmg  # Для MacOS выполнить из папки build, создаст dmg
windeployqt6 MyApp.app.     # Для Windows выполнить из папки build, будет папка со всеми зависимостями и exe. Папку можно перемещать на другие компы
Остальные библиотеки нужно самостоятельно скопировать в папку или пакет .app/frameworks
```

## 11. Установка PostgreSQL
```
brew update
brew install postgresql
brew services start postgresql
brew services list
psql postgres
CREATE DATABASE vertinsky;
\c vertinsky;
```

## 12. Установка Drogon
```
CMakeLists.txt                                      # Добавить set(PostgreSQL_ADDITIONAL_VERSIONS "18") перед find_package(PostgreSQL), потому в FindPostgreSQL.cmake отсутствует 18 версия
git clone https://github.com/drogonframework/drogon #
cd drogon                                           #
git submodule update --init                         #
mkdir build                                         #
cd build                                            #
cmake .. -DCMAKE_DISABLE_FIND_PACKAGE_OpenSSL=TRUE  # Не поддерживает пока что openssl4 
make && make install                                #
```
