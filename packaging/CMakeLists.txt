cmake_minimum_required(VERSION 3.14)

set(Format.cmake_VERSION 1.8.3)

include(GNUInstallDirs)

set(CMAKEDIR
  ${CMAKE_INSTALL_DATADIR}/cmake/Format.cmake/
    CACHE
      PATH
      "Path to a folder to which install the script Format.cmake . By default: ${CMAKE_INSTALL_DATADIR}/cmake/Format.cmake/"
)

include(CMakePackageConfigHelpers)

include(GNUInstallDirs)

write_basic_package_version_file(${CMAKE_CURRENT_LIST_DIR}/../Format.cmakeConfigVersion.cmake VERSION ${Format.cmake_VERSION} COMPATIBILITY AnyNewerVersion ARCH_INDEPENDENT)

install(FILES "${CMAKE_CURRENT_LIST_DIR}/../CMakeLists.txt"
  DESTINATION "${CMAKEDIR}" RENAME "Format.cmakeConfig.cmake"
)

install(FILES "${CMAKE_CURRENT_LIST_DIR}/../Format.cmakeConfigVersion.cmake"
  DESTINATION "${CMAKEDIR}"
)
install(FILES "${CMAKE_CURRENT_LIST_DIR}/../cmake-format.cmake"
  DESTINATION "${CMAKEDIR}"
)

install(FILES "${CMAKE_CURRENT_LIST_DIR}/../git-clang-format.py"
  DESTINATION "${CMAKEDIR}"
)

message(STATUS "Use `find_package(Format.cmake)` to use it")
