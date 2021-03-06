set (exe_tstorenightwatch "TStoreNightWatchTXRService.exe" CACHE STRING "TStore nightwatch Perf test")

add_executable(${exe_tstorenightwatch}
  ../NightWatchTXRService/PerfResult.cpp
  ../NightWatchTXRService/Service.cpp
  ../NightWatchTXRService/TestAction.cpp
  ../NightWatchTXRService/TestRunner.cpp
  ../NightWatchTXRService/TestStatus.cpp
  main.cpp
  TestComStateProvider2Factory.cpp
  TStoreService.cpp
  TStoreTestRunner.cpp
)

#add_precompiled_header(${exe_tstorenightwatch} stdafx.h)

target_link_libraries(${exe_tstorenightwatch}
    ${lib_TransactionalReplicator}
    ${lib_txnreplicator_testcommon}
    ${lib_data_utilities}
    ${lib_httptransport}
    ${lib_StatefulServiceBase}
    ${lib_FabricNode}
    ${lib_Communication}
    ${lib_ManagementSubsystem}
    ${lib_UpgradeService}
    ${lib_Testability}
    ${lib_HealthManager}
    ${lib_ClusterManager}
    ${lib_FabricGateway}
    ${lib_Hosting2}
    ${lib_ReliableConcurrentQueue}
    ${lib_TestHooks}
    ${lib_KtlLoggerNode}
    ${lib_TStore}
    ${lib_StoreRepairPolicy}
    ${lib_Replication}
    ${lib_TransactionalReplicator}
    ${lib_LoadBalancing}
    ${lib_Failover}
    ${lib_ServiceGroup}
    ${lib_ImageModel}
    ${lib_Query}
    ${lib_Federation}
    ${lib_LeaseAgent}
    ${lib_Lease}
    ${lib_Transport}
    ${lib_EntreeService}
    ${lib_StoreService}
    ${lib_Client}
    ${lib_ServiceModel}
    ${lib_ApiWrappers}
    ${lib_ImageStore}
    ${lib_ManagementRepairManager}
    ${lib_Store}
    ${lib_FileStoreService}
    ${lib_ManagementCommon}
    ${lib_SystemServices}
    ${lib_ClientServerTransport}
    ${lib_Common}
    ${Ktlfull}
    ${lib_FabricRuntime}
    ${lib_FabricCommon}
    ${lib_InternalFabricUUID}
    ${lib_FabricUUID}
    ssh2
    ssl
    crypto
    minizip
    z
    m
    rt
    pthread
    c
    dl
    xml2
    uuid
)

set_target_properties(${exe_tstorenightwatch} PROPERTIES 
    RUNTIME_OUTPUT_DIRECTORY ${TEST_OUTPUT_DIR})
