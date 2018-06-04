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

ADD_EXECUTABLE(yreditor mainEditor.yr ${EditorSourceFiles})
target_link_libraries (yreditor -lSDL2 -lSDL2main -lSDL2_image -lSDL2_ttf)
include_directories (yreditor ./)

ADD_EXECUTABLE(yrfight mainGame.yr ${GameSourceFiles})
target_link_libraries (yrfight -lSDL2 -lSDL2main -lSDL2_image -lm)
include_directories (yrfight ./)
