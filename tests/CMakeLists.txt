enable_testing()
find_package(Catch2 REQUIRED)

add_executable(TileTest TileTest.cpp)
target_link_libraries(TileTest PRIVATE meshgrid Catch2::Catch2)

add_test(NAME TileTest COMMAND TileTest)
