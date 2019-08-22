add_library(hello-static STATIC
  hellofunc.c
)

add_library(hello SHARED
  hellofunc.c
)

install(TARGETS hello
  LIBRARY CONFIGURATIONS Debug Release
  LIBRARY DESTINATION lib)

install(FILES hello.h
   CONFIGURATIONS Debug Release
   DESTINATION include)

set_target_properties(hello
  PROPERTIES
  SOVERSION ${VERSION_MAJOR}
  VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH}
  )
