project(nginx)
cmake_minimum_required(VERSION 2.8)

aux_source_directory(. SRC_LIST)
aux_source_directory(./src/core SRC_LIST)
aux_source_directory(./src/event SRC_LIST)
aux_source_directory(./src/event/modules SRC_LIST)
aux_source_directory(./src/os/unix SRC_LIST)
aux_source_directory(./src/http SRC_LIST)
aux_source_directory(./src/http/modules SRC_LIST)
aux_source_directory(./src/http/v2 SRC_LIST)
aux_source_directory(./src/mail SRC_LIST)
aux_source_directory(./src/stream SRC_LIST)


add_executable(${PROJECT_NAME} ${SRC_LIST})

INCLUDE_DIRECTORIES(./)
INCLUDE_DIRECTORIES(./src/core)
INCLUDE_DIRECTORIES(./src/event)
INCLUDE_DIRECTORIES(./src/event/modules)
INCLUDE_DIRECTORIES(./src/os/unix)
INCLUDE_DIRECTORIES(./src/http)
INCLUDE_DIRECTORIES(./src/http/modules)
INCLUDE_DIRECTORIES(./src/http/v2)
INCLUDE_DIRECTORIES(./src/mail)
INCLUDE_DIRECTORIES(./src/stream)

INCLUDE_DIRECTORIES(/opt/local/include)

TARGET_LINK_LIBRARIES (${PROJECT_NAME} /opt/local/lib/libpcre.a)
TARGET_LINK_LIBRARIES (${PROJECT_NAME} /opt/local/lib/libcrypto.a)
TARGET_LINK_LIBRARIES (${PROJECT_NAME} /opt/local/lib/libz.a)
