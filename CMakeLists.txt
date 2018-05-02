CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
PROJECT(YrFight C)
SET(CMAKE_C_COMPILER "gyc")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -fdump-tree-gimple")

FILE (
  GLOB_RECURSE
  GameSourceFiles
  game/*
  common/*
  common/sprite/*
  )

FILE (
  GLOB_RECURSE
  EditorSourceFiles
  editor/*
  common/*
  common/sprite/*
  )

SET_SOURCE_FILES_PROPERTIES(mainGame.yr mainEditor.yr ${GameSourceFiles} ${EditorSourceFiles} PROPERTIES LANGUAGE C)

#ADD_EXECUTABLE(../yrfight mainGame.yr ${GameSourceFiles})
ADD_EXECUTABLE(../yreditor mainEditor.yr ${EditorSourceFiles})
#target_link_libraries (../yrfight -lSDL2 -lSDL2main -lSDL2_image -lm)
target_link_libraries (../yreditor -lSDL2 -lSDL2main -lSDL2_image)
#include_directories (yrfight ./)
include_directories (yreditor ./)
