cmake_minimum_required(VERSION 3.12)
project(TaskTrackerCLI)

# Use C++17
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include headers
include_directories(include)

# Add executable
add_executable(task_tracker 
    src/main.cpp 
    src/task_tracker.cpp
)

# Link JSON library (if using nlohmann/json)
find_package(nlohmann_json REQUIRED)
target_link_libraries(task_tracker PRIVATE nlohmann_json::nlohmann_json)