cmake_minimum_required(VERSION 3.20)
project(PixMix)

set(CMAKE_CXX_STANDARD 17)


# Find all Header and Source files
file(GLOB_RECURSE ${PROJECT_NAME}_HEADERS sources/*.h)
file(GLOB_RECURSE ${PROJECT_NAME}_SOURCES sources/*.cpp)
find_package(OpenCV REQUIRED)

add_executable(${PROJECT_NAME}
        ${${PROJECT_NAME}_SOURCES}
        ${${PROJECT_NAME}_HEADERS})

# For Android Building
#find_library(log-lib
#        log)
#target_link_libraries(${PROJECT_NAME}
#        ${log-lib})

target_link_libraries(${PROJECT_NAME}
        ${OpenCV_LIBS})

target_include_directories(${PROJECT_NAME} PUBLIC src)
