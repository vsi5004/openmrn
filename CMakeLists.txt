file(REAL_PATH ${COMPONENT_DIR} OPENMRNESPIDFPATH)
# When CMakeLists.txt is in component root, OPENMRNPATH is the same directory
set(OPENMRNPATH ${OPENMRNESPIDFPATH})

set(SRCS
    ${OPENMRNPATH}/src/ble/Advertisement.cxx
    ${OPENMRNPATH}/src/ble/Defs.cxx

    ${OPENMRNPATH}/src/dcc/dcc_constants.cxx
    ${OPENMRNPATH}/src/dcc/DccDebug.cxx
    ${OPENMRNPATH}/src/dcc/Defs.cxx
    ${OPENMRNPATH}/src/dcc/LocalTrackIf.cxx
    ${OPENMRNPATH}/src/dcc/Loco.cxx
    ${OPENMRNPATH}/src/dcc/Packet.cxx
    ${OPENMRNPATH}/src/dcc/RailcomBroadcastDecoder.cxx
    ${OPENMRNPATH}/src/dcc/RailCom.cxx
    ${OPENMRNPATH}/src/dcc/RailcomDebug.cxx
    ${OPENMRNPATH}/src/dcc/SimpleUpdateLoop.cxx
    ${OPENMRNPATH}/src/dcc/UpdateLoop.cxx
    
    ${OPENMRNPATH}/src/executor/AsyncNotifiableBlock.cxx
    ${OPENMRNPATH}/src/executor/Executor.cxx
    ${OPENMRNPATH}/src/executor/Notifiable.cxx
    ${OPENMRNPATH}/src/executor/Service.cxx
    ${OPENMRNPATH}/src/executor/StateFlow.cxx
    ${OPENMRNPATH}/src/executor/Timer.cxx

    ${OPENMRNPATH}/src/freertos_drivers/esp32/Esp32HardwareI2C.cxx
    ${OPENMRNPATH}/src/freertos_drivers/esp32/Esp32HardwareTwai.cxx
    ${OPENMRNPATH}/src/freertos_drivers/esp32/Esp32Ledc.cxx
    ${OPENMRNPATH}/src/freertos_drivers/esp32/Esp32SocInfo.cxx
    # Excluded EspIdfWiFi.cxx - requires ESP-IDF 5.3+ APIs (channel_bitmap, WIFI_EVENT_HOME_CHANNEL_CHANGE)
    # ${OPENMRNPATH}/src/freertos_drivers/esp_idf/EspIdfWiFi.cxx
    ${OPENMRNPATH}/src/freertos_drivers/common/WifiDefs.cxx

    ${OPENMRNPATH}/src/openlcb/AliasAllocator.cxx
    ${OPENMRNPATH}/src/openlcb/AliasCache.cxx
    ${OPENMRNPATH}/src/openlcb/BLEAdvertisement.cxx
    ${OPENMRNPATH}/src/openlcb/BLEService.cxx
    ${OPENMRNPATH}/src/openlcb/BroadcastTime.cxx
    ${OPENMRNPATH}/src/openlcb/BroadcastTimeClient.cxx
    ${OPENMRNPATH}/src/openlcb/BroadcastTimeDefs.cxx
    ${OPENMRNPATH}/src/openlcb/BroadcastTimeServer.cxx
    ${OPENMRNPATH}/src/openlcb/BulkAliasAllocator.cxx
    ${OPENMRNPATH}/src/openlcb/CanDefs.cxx
    ${OPENMRNPATH}/src/openlcb/ConfigEntry.cxx
    ${OPENMRNPATH}/src/openlcb/ConfigUpdateFlow.cxx
    ${OPENMRNPATH}/src/openlcb/Datagram.cxx
    ${OPENMRNPATH}/src/openlcb/DatagramCan.cxx
    ${OPENMRNPATH}/src/openlcb/DatagramTcp.cxx
    ${OPENMRNPATH}/src/openlcb/DccAccyProducer.cxx
    ${OPENMRNPATH}/src/openlcb/DefaultNode.cxx
    ${OPENMRNPATH}/src/openlcb/DefaultCdi.cxx
    ${OPENMRNPATH}/src/openlcb/EventHandler.cxx
    ${OPENMRNPATH}/src/openlcb/EventHandlerContainer.cxx
    ${OPENMRNPATH}/src/openlcb/EventHandlerTemplates.cxx
    ${OPENMRNPATH}/src/openlcb/EventService.cxx
    ${OPENMRNPATH}/src/openlcb/FilteringCanHubFlow.cxx
    ${OPENMRNPATH}/src/openlcb/If.cxx
    ${OPENMRNPATH}/src/openlcb/IfCan.cxx
    ${OPENMRNPATH}/src/openlcb/IfImpl.cxx
    ${OPENMRNPATH}/src/openlcb/IfTcp.cxx
    ${OPENMRNPATH}/src/openlcb/MemoryConfig.cxx
    ${OPENMRNPATH}/src/openlcb/nmranet_constants.cxx
    ${OPENMRNPATH}/src/openlcb/Node.cxx
    ${OPENMRNPATH}/src/openlcb/NodeBrowser.cxx
    ${OPENMRNPATH}/src/openlcb/NodeInitializeFlow.cxx
    ${OPENMRNPATH}/src/openlcb/NonAuthoritativeEventProducer.cxx
    ${OPENMRNPATH}/src/openlcb/PIPClient.cxx
    ${OPENMRNPATH}/src/openlcb/RoutingLogic.cxx
    ${OPENMRNPATH}/src/openlcb/SimpleNodeInfo.cxx
    ${OPENMRNPATH}/src/openlcb/SimpleNodeInfoMockUserFile.cxx
    ${OPENMRNPATH}/src/openlcb/SimpleNodeInfoResponse.cxx
    ${OPENMRNPATH}/src/openlcb/SimpleStack.cxx
    ${OPENMRNPATH}/src/openlcb/StreamReceiver.cxx
    ${OPENMRNPATH}/src/openlcb/StreamTransport.cxx
    ${OPENMRNPATH}/src/openlcb/TcpDefs.cxx
    ${OPENMRNPATH}/src/openlcb/TractionCvSpace.cxx
    ${OPENMRNPATH}/src/openlcb/TractionDefs.cxx
    ${OPENMRNPATH}/src/openlcb/TractionProxy.cxx
    ${OPENMRNPATH}/src/openlcb/TractionTestTrain.cxx
    ${OPENMRNPATH}/src/openlcb/TractionThrottle.cxx
    ${OPENMRNPATH}/src/openlcb/TractionTrain.cxx
    ${OPENMRNPATH}/src/openlcb/Velocity.cxx
    ${OPENMRNPATH}/src/openlcb/WriteHelper.cxx
    
    ${OPENMRNPATH}/src/os/FakeClock.cxx
    ${OPENMRNPATH}/src/os/logging_malloc.cxx
    ${OPENMRNPATH}/src/os/MDNS.cxx
    ${OPENMRNPATH}/src/os/os.c
    ${OPENMRNPATH}/src/os/OSImpl.cxx
    ${OPENMRNPATH}/src/os/OSSelectWakeup.cxx
    ${OPENMRNPATH}/src/os/stack_malloc.c
    ${OPENMRNPATH}/src/os/TempFile.cxx
    ${OPENMRNPATH}/src/os/watchdog.c

    ${OPENMRNPATH}/src/traction_modem/Output.cxx

    ${OPENMRNPATH}/src/utils/Base64.cxx
    ${OPENMRNPATH}/src/utils/Blinker.cxx
    ${OPENMRNPATH}/src/utils/Buffer.cxx
    ${OPENMRNPATH}/src/utils/CanIf.cxx
    ${OPENMRNPATH}/src/utils/ClientConnection.cxx
    ${OPENMRNPATH}/src/utils/ConfigUpdateListener.cxx
    ${OPENMRNPATH}/src/utils/constants.cxx
    ${OPENMRNPATH}/src/utils/Crc.cxx
    ${OPENMRNPATH}/src/utils/DirectHub.cxx
    ${OPENMRNPATH}/src/utils/DirectHubGc.cxx
    ${OPENMRNPATH}/src/utils/DirectHubLegacy.cxx
    ${OPENMRNPATH}/src/utils/errno_exit.c
    ${OPENMRNPATH}/src/utils/FdUtils.cxx
    ${OPENMRNPATH}/src/utils/FileUtils.cxx
    ${OPENMRNPATH}/src/utils/format_utils.cxx
    ${OPENMRNPATH}/src/utils/ForwardAllocator.cxx
    ${OPENMRNPATH}/src/utils/GcStreamParser.cxx
    ${OPENMRNPATH}/src/utils/GcTcpHub.cxx
    ${OPENMRNPATH}/src/utils/gc_format.cxx
    ${OPENMRNPATH}/src/utils/GridConnect.cxx
    ${OPENMRNPATH}/src/utils/GridConnectHub.cxx
    ${OPENMRNPATH}/src/utils/HubDevice.cxx
    ${OPENMRNPATH}/src/utils/HubDeviceSelect.cxx
    ${OPENMRNPATH}/src/utils/ieeehalfprecision.c
    ${OPENMRNPATH}/src/utils/JSHubPort.cxx
    ${OPENMRNPATH}/src/utils/logging.cxx
    ${OPENMRNPATH}/src/utils/Queue.cxx
    ${OPENMRNPATH}/src/utils/ReflashBootloader.cxx
    ${OPENMRNPATH}/src/utils/ServiceLocator.cxx
    ${OPENMRNPATH}/src/utils/SocketCan.cxx
    ${OPENMRNPATH}/src/utils/SocketClient.cxx
    ${OPENMRNPATH}/src/utils/socket_listener.cxx
    ${OPENMRNPATH}/src/utils/Stats.cxx
    ${OPENMRNPATH}/src/utils/StringPrintf.cxx
)

set(INCLUDE_DIRS
    ${OPENMRNPATH}/src
    ${OPENMRNPATH}/include/esp-idf
)

# NOTE: We intentionally do NOT add ${OPENMRNPATH}/include to any include path
# because it contains include/freertos/FreeRTOSConfig.h which conflicts with
# ESP-IDF's FreeRTOSConfig.h. Instead, wrapper files in include/esp-idf/
# redirect to the actual files using relative paths.

set(IDF_DEPS
    app_update
    bootloader_support
    bt
    driver
    esp_adc
    esp_app_format
    esp_system
    esp_wifi
    espcoredump
    hal
    heap
    mdns
    nvs_flash
    pthread
    vfs)

idf_component_register(SRCS "${SRCS}"
                       INCLUDE_DIRS "${INCLUDE_DIRS}"
                       REQUIRES "${IDF_DEPS}")

###############################################################################
# C++ Standard - use C++14 for maximum compatibility with ESP-IDF newlib
###############################################################################
set_property(TARGET ${COMPONENT_LIB} PROPERTY CXX_STANDARD 14)
set_property(TARGET ${COMPONENT_LIB} PROPERTY CXX_STANDARD_REQUIRED ON)

###############################################################################
# Compiler flags for GCC 13/14 compatibility with ESP-IDF newlib
# The ESP-IDF newlib lacks some C++ standard library features that GCC's
# libstdc++ expects. We define __STRICT_ANSI__ equivalents to avoid constexpr paths.
###############################################################################
target_compile_options(${COMPONENT_LIB} PRIVATE 
    $<$<COMPILE_LANGUAGE:CXX>:-fno-strict-aliasing>
)
target_compile_definitions(${COMPONENT_LIB} PUBLIC
    _GLIBCXX_USE_C99
)

###############################################################################
# OpenMRN-specific defines
###############################################################################
target_compile_definitions(${COMPONENT_LIB} PUBLIC
    ESP32
    ESP_PLATFORM
    HAVE_CONFIG_H
    _DEFAULT_SOURCE
)

###############################################################################
# Warn all (but don't treat as errors for compatibility)
###############################################################################
target_compile_options(${COMPONENT_LIB} PRIVATE -Wall)
target_compile_options(${COMPONENT_LIB} PRIVATE -Wextra)

###############################################################################
# Suppress compilation warnings in OpenMRN for GCC 14.x
###############################################################################
target_compile_options(${COMPONENT_LIB} PRIVATE $<$<COMPILE_LANGUAGE:CXX>:-Wno-volatile>)
target_compile_options(${COMPONENT_LIB} PRIVATE $<$<COMPILE_LANGUAGE:CXX>:-Wno-error>)
