# cpp

```
mingw32-make         # Компиляция в папку Release
mingw32-make install # Копирует DLL в папку с компилятором
MinGW                # Набор инструментов для разработки ПО
g++                  # Компилятор
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
