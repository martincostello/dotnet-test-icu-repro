# Repro for dotnet test issue with Microsoft.ICU.ICU4C.Runtime

To replicate the issue, clone the repo and run the following command with version `6.0.100-rc.1.21420.39` of the .NET SDK or later:

```sh
dotnet test
```

## Expected Behaviour

```
> dotnet test
  Determining projects to restore...
  All projects are up-to-date for restore.
  You are using a preview version of .NET. See: https://aka.ms/dotnet-core-preview
  DotnetTestIcuRepro -> C:\Coding\martincostello\dotnet-test-icu-repro\bin\Debug\net6.0\DotnetTestIcuRepro.dll
Test run for C:\Coding\martincostello\dotnet-test-icu-repro\bin\Debug\net6.0\DotnetTestIcuRepro.dll (.NETCoreApp,Version=v6.0)
Microsoft (R) Test Execution Command Line Tool Version 17.0.0-preview-20210817-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.

Passed!  - Failed:     0, Passed:     1, Skipped:     0, Total:     1, Duration: < 1 ms - DotnetTestIcuRepro.dll (net6.0)
```

## Actual Behaviour

```
> dotnet test
  Determining projects to restore...
  All projects are up-to-date for restore.
  You are using a preview version of .NET. See: https://aka.ms/dotnet-core-preview
  DotnetTestIcuRepro -> C:\Coding\martincostello\dotnet-test-icu-repro\bin\Debug\net6.0\DotnetTestIcuRepro.dll
Test run for C:\Coding\martincostello\dotnet-test-icu-repro\bin\Debug\net6.0\DotnetTestIcuRepro.dll (.NETCoreApp,Version=v6.0)
Microsoft (R) Test Execution Command Line Tool Version 17.0.0-preview-20210817-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.
Testhost process exited with error: Cannot get symbol ubrk_close_68 from libicui18n
Error: 127
. Please check the diagnostic logs for more information.

Test Run Aborted.
```
