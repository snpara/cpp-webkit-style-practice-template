configure_file(
    "hello.txt"
    "${CMAKE_BINARY_DIR}/app/src/hello.txt"
    ESCAPE_QUOTES
    COPYONLY)

configure_file(
    "hello.txt"
    "${CMAKE_XCODE_BINARY_DIR}/app/src/Debug/hello.txt"
    ESCAPE_QUOTES
    COPYONLY)
