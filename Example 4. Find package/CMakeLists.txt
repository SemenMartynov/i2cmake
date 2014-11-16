# поиск библиотеки
find_package(SDL REQUIRED)
if(NOT SDL_FOUND)
    message(SEND_ERROR "Failed to find SDL")
    return()
else()
    include_directories(${SDL_INCLUDE_DIR})
endif()
##########################################################
# поиск библиотеки
find_package(LibXml2 REQUIRED)
if(NOT LIBXML2_FOUND)
    message(SEND_ERROR "Failed to find LibXml2")
    return()
else()
    include_directories(${LIBXML2_INCLUDE_DIR})
endif()
##########################################################
# ищет не целый пакет библиотек, а лишь необходимый компонент
find_package(Boost COMPONENTS thread-mt REQUIRED)
if(NOT Boost_FOUND)
    message(SEND_ERROR "Failed to find boost::thread-mt.")
    return()
else()
    include_directories(${Boost_INCLUDE_DIRS})
endif()
##########################################################
target_link_libraries(${TARGET}
                                ${SDL_LIBRARY}
                                ${LIBXML2_LIBRARIES}
                                ${Boost_LIBRARIES})
