cmake_minimum_required(VERSION 3.0)
project(qcracker LANGUAGES C)

set(PROJECT_VERSION 1.0)
set(PROJECT_DESCRIPTION "reverse-engineering qcracker")

include(GNUInstallDirs)
include(FindPkgConfig)

add_executable( qcracker qcracker.c )
add_executable( convertmem convertmem.c )
add_executable( qcrypt qcrypt.c )
add_executable( qcrypt_testfilegen qcrypt_testfilegen.c )
add_executable( qcrack_checksum_test qcrack_checksum_test.c )
add_executable( xorfiles xorfiles.c )

install(TARGETS qcracker convertmem qcrypt qcrypt_testfilegen qcrack_checksum_test xorfiles EXPORT ${PROJECT_NAME}Config)
install(PROGRAMS ${CMAKE_CURRENT_SOURCE_DIR}/qdump.py DESTINATION ${CMAKE_INSTALL_BINDIR})
