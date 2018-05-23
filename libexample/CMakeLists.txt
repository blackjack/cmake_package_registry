cmake_minimum_required(VERSION 3.0.0)

project(libexample VERSION 1.0.0 LANGUAGES CXX)


include(GNUInstallDirs)
set(INSTALL_CONFIGDIR ${CMAKE_INSTALL_LIBDIR}/cmake/Example)

add_subdirectory(src)



include(CMakePackageConfigHelpers)

configure_package_config_file(
  ${CMAKE_CURRENT_SOURCE_DIR}/example-config.cmake.in
  ${CMAKE_CURRENT_BINARY_DIR}/example-config.cmake
  INSTALL_DESTINATION ${INSTALL_CONFIGDIR}
)

write_basic_package_version_file(
  ${CMAKE_CURRENT_BINARY_DIR}/example-config-version.cmake
  VERSION ${PROJECT_VERSION}
  COMPATIBILITY AnyNewerVersion
)


export(
  EXPORT example-targets
  FILE ${CMAKE_CURRENT_BINARY_DIR}/example-targets.cmake
  NAMESPACE Example::
)

export(PACKAGE Example)
