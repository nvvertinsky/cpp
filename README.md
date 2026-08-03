# cpp

### Компиляция
```
g++                               # Компилятор 
g++ -c square.cpp -o my_program   # Компиляция cpp файла
square.o                          # Результат. Содержит машинный код
objdump -d square.o.              # Утилита objdump переводит машинный код в ассемблер
```


mingw32-make         # Компиляция в папку Release
mingw32-make install # Копирует DLL в папку с компилятором
MinGW                # Набор инструментов для разработки ПО
cdb.exe              # Отлатчик. Ставится вместе в Windows SDK (Debugging Tools for Windows)
qmake                # Подготовить проект к компиляции.
nmake                # Компиляция через msvc
nmake install        # Копирования файлов в QT
```

### Данные хранят в куче, сами являются указателями
```
std::vector, std::deque # Все стандартные коллекции
std::string             # Строки
std::unique_ptr         # Умные указатели 
std::thread             # Потоки
std::exception          # Исключения 
```
