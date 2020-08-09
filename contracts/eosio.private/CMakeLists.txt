add_contract(eosio.private eosio.private ${CMAKE_CURRENT_SOURCE_DIR}/src/eosio.private.cpp)

target_include_directories(eosio.private
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(eosio.private
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/eosio.private.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/eosio.private.contracts.md @ONLY )

target_compile_options( eosio.private PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
