# Слово «IMPORTED», указывает, что библиотека берётся извне.
add_library(netutil STATIC IMPORTED)
set_property(TARGET netutil PROPERTY
             IMPORTED_LOCATION Binary/game_client/libnetutil.a)
# Для динамических библиотек все аналогично, только тип «SHARED», расширение — ".so".

target_link_libraries(${TARGET} netutil)
