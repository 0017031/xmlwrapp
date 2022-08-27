cmake_minimum_required(VERSION 3.15)
project(example1 CXX)

set(CMAKE_VERBOSE_MAKEFILE 1)
add_executable(app1 example.cxx)

# set(LDFLAGS -static)

target_compile_features(app1 PRIVATE 
    cxx_std_23)
target_compile_options(app1 PRIVATE 
    -Wall -Wextra) # -Werror  -pedantic 

target_include_directories(app1 PRIVATE 
    ../../include)
target_link_libraries(app1 PRIVATE 
"/home/baic/.local/lib/libxmlwrapp.a"
xml2)


# g++ -I. -I../../include  -c -o example-example.o example.cxx
# g++ -o example example.o  
# ../../src/.libs/libxmlwrapp.so -Wl,-rpath -Wl,/home/baic/.local/lib