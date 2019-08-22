cmake_minimum_required(VERSION 3.0.0)

set(CMAKE_CXX_STANDARD 11)
    set(CompilerFlags
            CMAKE_CXX_FLAGS
            CMAKE_CXX_FLAGS_DEBUG
            CMAKE_CXX_FLAGS_RELEASE
            CMAKE_C_FLAGS
            CMAKE_C_FLAGS_DEBUG
            CMAKE_C_FLAGS_RELEASE
            )
    foreach(CompilerFlag ${CompilerFlags})
        string(REPLACE "/MD" "/MT" ${CompilerFlag} "${${CompilerFlag}}")
    endforeach()

include(CTest)
enable_testing()

set(CMAKE_INSTALL_PREFIX ${PROJECT_SOURCE_DIR})

set(LBT_INFO_INSTALL_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include)
#set(LBT_INFO_INSTALL_LIB_DIR ${PROJECT_SOURCE_DIR}/lib)
#set(LBT_INFO_INSTALL_BIN_DIR ${PROJECT_SOURCE_DIR}/bin)

include_directories(${LBT_INFO_INSTALL_INCLUDE_DIR})

#set(DIVISION_HEADERS_DIR ${PROJECT_SOURCE_DIR}/src/division)
#include_directories(${DIVISION_HEADERS_DIR})

add_subdirectory(src)
add_subdirectory(test)