cmake_minimum_required(VERSION 2.8.7)

project(GSL CXX)

add_library(gsl INTERFACE)
target_include_directories(gsl
    INTERFACE
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
)

install(
    TARGETS gsl
    EXPORT gsl-config
)

install(
    DIRECTORY include/gsl
    DESTINATION include
)

install(
    EXPORT gsl-config
    DESTINATION lib/gsl
)

enable_testing()
#add_subdirectory(tests)
