project(tests LANGUAGES CXX)

# Используем модуль FetchContent
# https://cmake.org/cmake/help/latest/module/FetchContent.html
include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        v1.14.0
)
FetchContent_MakeAvailable(GoogleTest)

add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest_main)

#find_library(PTHREAD_LIBRARY pthread)
#find_library(PCRE_LIBRARY pcre)
#include_directories(include)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED on)
set(CXX_EXTENSIONS NO)
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Werror")

#add_executable(${PROJECT_NAME} main.cpp Fruit.cpp Vegetable.cpp Avocado.cpp)		# Создает исполняемый файл с именем main
									# из исходника main.cpp
#add_executable(main src/Main.cpp src/HttpServer.cpp)
#target_link_libraries(main ${PTHREAD_LIBRARY} ${PCRE_LIBRARY})

#add_subdirectory(tests)
