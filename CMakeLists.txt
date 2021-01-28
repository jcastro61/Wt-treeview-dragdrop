cmake_minimum_required(VERSION 3.7)

project(treeview)

SET(WT_PROJECT_SOURCE
  CsvUtil.cpp
  FolderView.cpp
  TreeViewDragDrop.cpp
)

SET(WT_PROJECT_TARGET wt_project.wt)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "..")
set(CMAKE_CXX_STANDARD 14)

ADD_EXECUTABLE(treeview ${WT_PROJECT_SOURCE})


INCLUDE_DIRECTORIES(
  ${WT_SOURCE_DIR}/src /usr/include/boost
)

TARGET_LINK_LIBRARIES(treeview boost_system boost_filesystem wthttp wt)