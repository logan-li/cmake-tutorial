cmake_minimum_required(VERSION 3.4)
project (Demo)

aux_source_directory(. DIR_SRCS)

add_subdirectory(math)

add_executable(Demo ${DIR_SRCS})

target_link_libraries(Demo math)