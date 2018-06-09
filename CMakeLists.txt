cmake_minimum_required(VERSION 3.4)
project (Demo)

configure_file(
    "${PROJECT_SOURCE_DIR}/config.h.in"
    "${PROJECT_SOURCE_DIR}/config.h"
)

option (USE_MYMATH "use custom math" on)

if (USE_MYMATH)
    include_directories("${PROJECT_SOUCE_DIR}/math")
    add_subdirectory(math)
    set (EXTRA_LIBS ${EXTRA_LIBS} math)
endif (USE_MYMATH)

aux_source_directory(. DIR_SRCS)

add_executable(Demo ${DIR_SRCS})

target_link_libraries(Demo ${EXTRA_LIBS})