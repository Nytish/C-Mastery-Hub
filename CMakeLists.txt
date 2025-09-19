cmake_minimum_required(VERSION 3.15)
project(CPPUpskill LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Main application executable (entry point)
add_executable(upskill_app src/main.cpp)
target_include_directories(upskill_app PRIVATE include)

# Add SOLID principles module (extend for other modules)
add_subdirectory(modules/solid)

# Link SOLID module with main app (add others as more modules are written)
target_link_libraries(upskill_app PRIVATE solid)

# Enable testing globally for future test integration
enable_testing()
