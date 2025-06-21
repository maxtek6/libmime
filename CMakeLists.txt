cmake_minimum_required(VERSION 3.15)

project(libmime)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

include(FetchContent)

FetchContent_Declare(
    mime-db
    GIT_REPOSITORY https://github.com/jshttp/mime-db.git 
    GIT_TAG v1.54.0)
FetchContent_MakeAvailable(mime-db)

FetchContent_Declare(
    nlohmann_json
    GIT_REPOSITORY https://github.com/nlohmann/json.git
    GIT_TAG v3.12.0
)
FetchContent_MakeAvailable(nlohmann_json)

add_executable(dbgen ${CMAKE_CURRENT_SOURCE_DIR}/src/dbgen.cpp)