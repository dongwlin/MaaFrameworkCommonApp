include_directories(${CMAKE_SOURCE_DIR}/deps/include)
if (WIN32)
    link_directories(${CMAKE_SOURCE_DIR}/deps/lib)
else ()
    link_directories(${CMAKE_SOURCE_DIR}/deps/bin)
endif ()

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CONFIGURATION_TYPES "Release")

add_executable(MFCA_CLI main.cpp main.h)
target_link_libraries(MFCA_CLI PRIVATE MaaFramework MaaToolKit)

add_dependencies(MFCA_CLI AssetsResource)

install(TARGETS MFCA_CLI RUNTIME DESTINATION .)
