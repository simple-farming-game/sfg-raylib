cmake_minimum_required(VERSION 3.12)

project(SFG)

# Raylib 경로를 설정합니다.
set(RAYLIB_PATH "/opt/homebrew/Cellar/raylib/5.0/" CACHE PATH "Path to Raylib")
set(CMAKE_CXX_STANDARD 11)

# Raylib 라이브러리를 찾습니다.
find_library(RAYLIB_LIBRARY
    NAMES raylib
    PATHS ${RAYLIB_PATH}/lib
    NO_DEFAULT_PATH
)

# Raylib 헤더 파일을 포함합니다.
include_directories(${RAYLIB_PATH}/include)

# 프로젝트 소스 파일을 추가합니다.
set(SOURCES
    src/main.cpp
    # 다른 소스 파일들 추가
)

# 실행 파일을 빌드합니다.
add_executable(${PROJECT_NAME} ${SOURCES})

# Raylib 라이브러리를 링크합니다.
target_link_libraries(${PROJECT_NAME} ${RAYLIB_LIBRARY})