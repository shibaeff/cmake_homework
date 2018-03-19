include_directories(${CMAKE_SOURCE_DIR}/A)
set(CMAKE_CXX_STANDARD 14)
find_package(PythonInterp 3.6 REQUIRED)
execute_process(
	WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}/A"
	COMMAND ${PYTHON_EXECUTABLE} ${CMAKE_SOURCE_DIR}/A/script.py
)
set(HEADERS ${CMAKE_SOURCE_DIR}/A/index.h)
set(SOURCES ${CMAKE_SOURCE_DIR}/A/main.cpp)
add_executable(out $SOURCES $HEADERS)

