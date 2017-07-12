project(basic C)
cmake_minimum_required(VERSION 3.5)

add_executable(basic
    src/array.c
    src/dictionary.c
    src/hexdump.c
    src/io.c
    src/lines.c
    src/parser.c
    src/tokenizer.c
    src/variables.c
    arch/osx/arch.c
    arch/osx/error.c
    arch/osx/kbhit.c
    arch/osx/main.c

)

target_include_directories(basic PRIVATE
    include
)

target_link_libraries(basic PRIVATE
    readline
    m
)

target_compile_definitions(basic PRIVATE
    -DARCH_OSX=1
    -DARCH_XMEGA=2
    -DARCH=1
)

target_compile_options(basic PRIVATE
    -Wall
    -Werror
)

set_property(TARGET basic PROPERTY C_STANDARD 99)
