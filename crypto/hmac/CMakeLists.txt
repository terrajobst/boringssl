include_directories(../../include)

add_library(
  hmac

  OBJECT

  hmac.c
)


if(ENABLE_TESTS)
add_executable(
  hmac_test

  hmac_test.cc

  $<TARGET_OBJECTS:test_support>
)

target_link_libraries(hmac_test crypto)
add_dependencies(all_tests hmac_test)
endif()
