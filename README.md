# ReactNativeErros

### Could not launch “<app_name>”

1. После запуска приложения в XCode билд проходит без проьлем, после чего появлятся ошибка
```

Could not launch “pmplite”
Domain: IDEDebugSessionErrorDomain
Code: 3
Failure Reason: Failed to get the task for process 8364
User Info: {
    DVTErrorCreationDateKey = "2024-02-28 10:44:30 +0000";
    DVTRadarComponentKey = 855031;
    IDERunOperationFailingWorker = DBGLLDBLauncher;
    RawUnderlyingErrorMessage = "Failed to get the task for process 8364";
}
--

Analytics Event: com.apple.dt.IDERunOperationWorkerFinished : {
    "device_model" = "iPhone8,4";
    "device_osBuild" = "15.1 (19B74)";
    "device_platform" = "com.apple.platform.iphoneos";
    "launchSession_schemeCommand" = Run;
    "launchSession_state" = 1;
    "launchSession_targetArch" = arm64;
    "operation_duration_ms" = 52232;
    "operation_errorCode" = 3;
    "operation_errorDomain" = IDEDebugSessionErrorDomain;
    "operation_errorWorker" = DBGLLDBLauncher;
    "operation_name" = IDEiPhoneRunOperationWorkerGroup;
    "param_consoleMode" = 0;
    "param_debugger_attachToExtensions" = 0;
    "param_debugger_attachToXPC" = 1;
    "param_debugger_type" = 5;
    "param_destination_isProxy" = 0;
    "param_destination_platform" = "com.apple.platform.iphoneos";
    "param_diag_MainThreadChecker_stopOnIssue" = 0;
    "param_diag_MallocStackLogging_enableDuringAttach" = 0;
    "param_diag_MallocStackLogging_enableForXPC" = 1;
    "param_diag_allowLocationSimulation" = 1;
    "param_diag_checker_tpc_enable" = 1;
    "param_diag_gpu_frameCapture_enable" = 0;
    "param_diag_gpu_shaderValidation_enable" = 0;
    "param_diag_gpu_validation_enable" = 0;
    "param_diag_memoryGraphOnResourceException" = 0;
    "param_diag_queueDebugging_enable" = 1;
    "param_diag_runtimeProfile_generate" = 0;
    "param_diag_sanitizer_asan_enable" = 0;
    "param_diag_sanitizer_tsan_enable" = 0;
    "param_diag_sanitizer_tsan_stopOnIssue" = 0;
    "param_diag_sanitizer_ubsan_stopOnIssue" = 0;
    "param_diag_showNonLocalizedStrings" = 0;
    "param_diag_viewDebugging_enabled" = 1;
    "param_diag_viewDebugging_insertDylibOnLaunch" = 1;
    "param_install_style" = 0;
    "param_launcher_UID" = 2;
    "param_launcher_allowDeviceSensorReplayData" = 0;
    "param_launcher_kind" = 0;
    "param_launcher_style" = 0;
    "param_launcher_substyle" = 0;
    "param_runnable_appExtensionHostRunMode" = 0;
    "param_runnable_productType" = "com.apple.product-type.application";
    "param_testing_launchedForTesting" = 0;
    "param_testing_suppressSimulatorApp" = 0;
    "param_testing_usingCLI" = 0;
    "sdk_canonicalName" = "iphoneos16.4";
    "sdk_osVersion" = "16.4";
    "sdk_variant" = iphoneos;
}
--


System Information

macOS Version 13.0 (Build 22A5266r)
Xcode 14.3.1 (21815) (Build 14E300c)
Timestamp: 2024-02-28T12:44:30+02:00
```

*Решение*

Исправил путем включения параметра ```Automatically manage signing``` в ```signing & capabilities```.

### Error: [messaging/unknown] The operation couldn’t be completed. No APNS token specified before fetching FCM Token
Ошибка возникает в момент вызова метода messaging().getToken()

```
Error: [messaging/unknown] The operation couldn’t be completed. No APNS token specified before fetching FCM Token
NativeFirebaseError: [messaging/unknown] The operation couldn’t be completed. No APNS token specified before fetching FCM Token
    at getToken (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:182651:36)
    at ?anon_0_ (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:191496:63)
    at next (native)
    at asyncGeneratorStep (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:4169:26)
    at _next (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:4188:29)
    at anonymous (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:4193:14)
    at tryCallTwo (/Users/distiller/react-native/sdks/hermes/build_iphonesimulator/lib/InternalBytecode/InternalBytecode.js:61:9)
    at doResolve (/Users/distiller/react-native/sdks/hermes/build_iphonesimulator/lib/InternalBytecode/InternalBytecode.js:216:25)
    at Promise (/Users/distiller/react-native/sdks/hermes/build_iphonesimulator/lib/InternalBytecode/InternalBytecode.js:82:14)
    at anonymous (http://localhost:8081/index.bundle//&platform=ios&dev=true&minify=false&modulesOnly=false&runModule=true&app=ru.agbis.PMPLiteReact:4185:25)
    at apply (native)


```
