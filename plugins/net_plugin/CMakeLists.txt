file(GLOB HEADERS "include/eosio/net_plugin/*.hpp" "*.hpp" )
add_library( net_plugin
    net_plugin.cpp
    connection.cpp
    net_transport.cpp
    ${HEADERS} )

target_link_libraries( net_plugin chain_plugin producer_plugin appbase eosio_chain chainbase softfloat fc )
target_include_directories( net_plugin
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
        ${CMAKE_CURRENT_SOURCE_DIR}/../chain_interface/include
        ${CMAKE_CURRENT_SOURCE_DIR}/../../libraries/chain/include
        ${CMAKE_CURRENT_SOURCE_DIR}/../../libraries/chainbase/include
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
)
