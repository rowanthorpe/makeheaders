cmake_minimum_required(VERSION 3.0)

add_executable(makeheaders 
    makeheaders.c
)

install(TARGETS makeheaders
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)