# Create a library called hellolib
add_library (hellolib hellolib.cpp hellolib.h)

# Make sure the compiler can find include files for our hellolib
# when other libraries or executables link to hellolib
target_include_directories(hellolib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# Set public headers property
set_target_properties(hellolib PROPERTIES PUBLIC_HEADER hellolib.h)

# Set C compiler standard
set_property(TARGET hellolib PROPERTY CXX_STANDARD 20)

# Install library and header
install(TARGETS hellolib PUBLIC_HEADER DESTINATION include)
