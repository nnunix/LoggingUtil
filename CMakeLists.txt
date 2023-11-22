project(LoggingUtil C CXX)
find_package(Qt5Core REQUIRED)

set(CMAKE_AUTOMOC TRUE)

set(SOURCES src/InputReader.cpp
src/InputReader.h
src/LoggingUtil.cpp
src/LogProcessor.cpp
src/LogProcessor.h
src/Version.h
)

set(CMAKE_C_FLAGS_RELWITHDEBINFO "${CMAKE_C_FLAGS_RELWITHDEBINFO} /MT")
set(CMAKE_CXX_FLAGS_RELWITHDEBINFO "${CMAKE_CXX_FLAGS_RELWITHDEBINFO} /MT")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} /MTd")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MTd")

qt5_wrap_cpp(SOURCES)

add_executable(${PROJECT_NAME} ${SOURCES} ) 
target_link_libraries(${PROJECT_NAME} Qt5::Core qtpcre ws2_32)

