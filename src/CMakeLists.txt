cmake_minimum_required(VERSION 3.0.0)
project(lbt-info VERSION 0.1.0)

set(LBT_SOURCE_FILES lbt-info.cpp)
set(LBT_INCLUDES ${PROJECT_SOURCE_DIR}/include)

add_library(lbt-info STATIC ${LBT_SOURCE_FILES})
target_include_directories(lbt-info PUBLIC ${LBT_INCLUDES})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)