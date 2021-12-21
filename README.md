# LaunchDarkly Sample .NET Application 

This is a simple console application that demonstrates how LaunchDarkly's SDK works.I use it to experient LaunchDarkly platform


## Build instructions 

This is a .NET Core application that can be built on any platform where .NET is available. I tested it in VS community version 2019 and 2022

1. Edit `HelloDotNet/Hello.cs` and set the value of `SdkKey` to your LaunchDarkly  Server-side SDK key.and set `FeatureFlagKey` to the flag key.
Example
```csharp
    public const string SdkKey = "sdk-9104f5a9-e5f3-4abd-a013-57736801777e";

    public const string FeatureFlagKey = "verbose-logging";
```

2. If you are using Visual Studio, open `HelloDotNet.sln` and run the application. Or, to run from the command line, type the following command:

```
    dotnet run --project HelloDotNet
```

You should see the message `"Feature flag '<flag key>' is <true/false> for this user"`.

I evaluated 3 feature flags and set up 8 feature flags under the test environment in this exercise.(use LaunchDarkly .Net SDK)
1. Verbose Logging
This is a feature flag for the scenario opposite to the kill switch. I would like Joe Smith to have the verbose logging feature enabled, this would enable QA team to more information about Joe's experience and understand the cause of problems for this individual.

I kept the default result to `false` to keep this feature off for all users and I want `false` to be returned, regardless of whether targeting is enabled or not.
The following screenshot shows what this switch looks like where verbose logging is needed for Joe.
<img width="1510" alt="LD1" src="https://user-images.githubusercontent.com/50951276/146875396-84770e3e-6216-4dfa-ac7f-dc17cb641890.png">

2. User Testing (Percentage Rollouts)
This is a feature flag for the scenario to roll out to a small percentage of users, around 10% to gather user feedback to ensure the feature work as expected. then the feature would be roll out to around 50% for load and performance testing then gradually increase to 100%.

I also would like to use the default key-value,this will rollout for each different user because the user has a unique key. Alternatively, if the feature is designed for a company. we also can see the email as an atttribute.
Default rule is false and the value to be served for when targeting id disabled because we want to achieve the targeting percentage rule.

<img width="1514" alt="LD2" src="https://user-images.githubusercontent.com/50951276/146879564-25f37f57-5e52-444c-a42c-f29c1e5c85a4.png">
<img width="1510" alt="LD3" src="https://user-images.githubusercontent.com/50951276/146879586-624c812b-8b9c-435f-b314-c3522df999c4.png">

3.QA experiment( ring rollouts)
This is a feature flag for the scenario for ring rollouts management,create segment Alpha Users,Beta Users,QA and Stakeholders in the Segments sections respectively.

I assume we need to look after 3 rings- Alpha Users, Beta Users, All Users. Initially, we would like Alpha User test feature 1 and Beta User test feature 2(which is an improved version of feature 1) and overtime feedback from Alpha User and Beta Users will provide evidence and confidence to All Users in main.
<img width="1508" alt="LD4" src="https://user-images.githubusercontent.com/50951276/146890301-9f4a71c3-9e13-4772-9890-48cdba950b33.png">
<img width="1517" alt="LD5" src="https://user-images.githubusercontent.com/50951276/146890313-ccbc4218-8dc4-43bd-929c-18f8772061f4.png">
<img width="1517" alt="LD6" src="https://user-images.githubusercontent.com/50951276/146890324-4ec73939-476c-4211-93f8-236b4194aea0.png">
<img width="1517" alt="LD7" src="https://user-images.githubusercontent.com/50951276/146890410-9083814d-6409-460c-856b-1e6fb58bff10.png">
<img width="1517" alt="LD8" src="https://user-images.githubusercontent.com/50951276/146890444-362c6866-6452-4e50-b0a6-22e7e7755043.png">
<img width="1519" alt="LD9" src="https://user-images.githubusercontent.com/50951276/146890453-cc82f099-2521-4e91-a474-dbb1899f395d.png">




I found the Experiments feature,Relay Proxy and Roles(Roles bases access control) are disabled in the trial. I would love to know more in the next chat!

My feature flags and feature flags dashboards
<img width="1515" alt="LD10" src="https://user-images.githubusercontent.com/50951276/146891370-88b19aee-ad28-4f29-9f72-3087ecbe70ca.png">



