# cpp

mingw32-make         # Компиляция в папку Release
mingw32-make install # Копирует DLL в папку с компилятором
MinGW                # Набор инструментов для разработки ПО
g++                  # Компилятор
cdb.exe              # Отлатчик. Ставится вместе в Windows SDK (Debugging Tools for Windows)
qmake                # Подготовить проект к компиляции.
nmake                # Компиляция через msvc
nmake install        # Копирования файлов в QT

### Данные хранят в куче, сами являются указателями
Все стандартные коллекции std::vector, std::deque
Строки std::string
Умные указатели std::unique_ptr и другие 
Потоки std::thread
Исключения std::exception
