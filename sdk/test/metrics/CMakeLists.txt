foreach(testname meter_provider_sdk_test)
  add_executable(${testname} "${testname}.cc")
  target_link_libraries(${testname} ${GTEST_BOTH_LIBRARIES}
                        ${CMAKE_THREAD_LIBS_INIT} opentelemetry_common opentelemetry_metrics)
  gtest_add_tests(TARGET ${testname} TEST_PREFIX metrics. TEST_LIST ${testname})
endforeach()