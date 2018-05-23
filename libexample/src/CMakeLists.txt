set(example_sources 
  example.cpp
)

add_library(example
  ${example_sources}
)

add_library(Example::example ALIAS example)


target_include_directories(example
  PUBLIC
  $<INSTALL_INTERFACE:include>
  $<BUILD_INTERFACE:${CMAKE_SOURCE_DIR}/include>
)


install(TARGETS example
  EXPORT example-targets
  LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
  ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
