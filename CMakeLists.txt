cmake_minimum_required(VERSION 3.27)
project(vcpkg_test_lib)

add_library(vcpkg_test_lib STATIC)

target_sources(${PROJECT_NAME} INTERFACE
        FILE_SET HEADERS
        FILES
        library.h
)

target_sources(${PROJECT_NAME}
        PRIVATE
        library.cpp
)

target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_23)

install(TARGETS ${PROJECT_NAME}
        FILE_SET HEADERS
        DESTINATION include/${PROJECT_NAME}
)
