add_subdirectory(Compression)

find_package(Qt6 REQUIRED COMPONENTS Core)

qt_add_library(UtilitiesTest STATIC
    QGCFileDownloadTest.cc
    QGCFileDownloadTest.h
)

target_link_libraries(UtilitiesTest
    PRIVATE
        Qt6::Test
        Utilities
    PUBLIC
        qgcunittest
)

target_include_directories(UtilitiesTest PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

qt_add_resources(UtilitiesTest "UtilitiesTest_res"
    PREFIX "/"
    FILES
        arducopter.apj
)
