# Минимальная версия CMake
cmake_minimum_required (VERSION 2.6)

# Переменной PROJECT задается значение hello_world
set (PROJECT hello_world)

# Конструкция ${ИМЯ_ПЕРЕМЕННОЙ} возвращает значение переменной,
# таким образом проект будет называться hello_world
project (${PROJECT})


set (HEADERS
    hello.h)

set (SOURCES
    hello.cpp
    main.cpp)

# Собрать исполняемый файл с именем указанном в переменной PROJECT
# и из файлов имена которых находятся в переменных HEADERS и SOURCES
add_executable (${PROJECT} ${HEADERS} ${SOURCES})

# Собрать статическую библиотеку можно так
# add_library(${PROJECT} ${HEADERS} ${SOURCES})

# для сборки динамической библиотеки надо указать параметр SHARED после имени библиотеки
# add_library (${PROJECT} SHARED ${HEADERS} ${SOURCES})