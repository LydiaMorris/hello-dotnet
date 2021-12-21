# LaunchDarkly Sample .NET Application 

This is a simple console application that demonstrates how LaunchDarkly's SDK works.I use it to experient LaunchDarkly platform


## Build instructions 

This is a .NET Core application that can be built on any platform where .NET is available. I tested it in VS community version 2019 and 2022

1. Edit `HelloDotNet/Hello.cs` and set the value of `SdkKey` to your LaunchDarkly  Server-side SDK key.and set `FeatureFlagKey` to the flag key.

```csharp
    public const string SdkKey = "sdk-9104f5a9-e5f3-4abd-a013-57736801777e";

    public const string FeatureFlagKey = "verbose-logging";
```

2. If you are using Visual Studio, open `HelloDotNet.sln` and run the application. Or, to run from the command line, type the following command:

```
    dotnet run --project HelloDotNet
```

You should see the message `"Feature flag '<flag key>' is <true/false> for this user"`.

I evaluated 3 feature flags and setted up 8 feature flags under test environment in this exercise.(use LaunchDarkly .Net SDK)
1. Verbose Logging
This is feature flag for the scenario opposite to kill switch. I would like Joe Smith have the verbose logging feature enabled, this would enable QA team to more information about Joe's experience and understand the cause of problems for this individual.

I kept the default result to `false` to keep this feature off for all users and I want `false` to be returned, regardless of whether targeting is enabled or not.
The following screnshot shows what this switch look like where verbose logging is needed for Joe.
