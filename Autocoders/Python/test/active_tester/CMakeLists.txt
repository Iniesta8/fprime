# Default module cmake file
# AUTOCODER_INPUT_FILES: Contains all Autocoder input files
# SOURCE_FILES: Handcoded C++ source files)

set(SOURCE_FILES
  "${CMAKE_CURRENT_LIST_DIR}/Simple_ActiveComponentAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/Simple_Active_TesterComponentAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/Active_TesterTopologyAppAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/F32PortAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/U32PortAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/Simple_ActiveImpl.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Simple_Active_TesterImpl.cpp"
)

register_fprime_module()

# Sets MODULE_NAME to unique name based on path
get_module_name(${CMAKE_CURRENT_LIST_DIR})

# Exclude test module from all build
set_target_properties(
  ${MODULE_NAME}
  PROPERTIES
  EXCLUDE_FROM_ALL TRUE
)

# Add unit test directory
# UT_SOURCE_FILES: Sources for unit test
set(UT_SOURCE_FILES
  "${FPRIME_FRAMEWORK_PATH}/Autocoders/Python/test/active_tester/Simple_Active_TesterComponentAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/Top.cpp"
)
#register_fprime_ut()


