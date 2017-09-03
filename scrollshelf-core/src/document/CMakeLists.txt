cmake_minimum_required(VERSION 3.8)

set(LIBRARY_NAME document)
project(lib-${LIBRARY_NAME})

add_library(${LIBRARY_NAME} STATIC "")
add_library(scrollshelf-core::${LIBRARY_NAME} ALIAS ${LIBRARY_NAME})

target_sources(${LIBRARY_NAME}
        PRIVATE src/Document.cpp
        )

target_link_libraries(${LIBRARY_NAME}
        PRIVATE ${PODOFO_LIB}
        PUBLIC Qt5::Core
        )

target_include_directories(${LIBRARY_NAME} PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/${LIBRARY_NAME}>
        $<INSTALL_INTERFACE:include/${LIBRARY_NAME}>
        )

target_include_directories(${LIBRARY_NAME} INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:include>
        )

add_subdirectory(test)
