# ReflectInsight-Extensions-EnterpriseLibrary5

[![Build status](https://ci.appveyor.com/api/projects/status/github/reflectsoftware/reflectinsight-extensions-enterpriselibrary5?svg=true)](https://ci.appveyor.com/project/reflectsoftware/reflectinsight-extensions-enterpriselibrary5)
[![License](https://img.shields.io/:license-MS--PL-blue.svg)](https://github.com/reflectsoftware/reflectinsight-extensions-enterpriselibrary5/license.md)
[![Release](https://img.shields.io/github/release/reflectsoftware/reflectinsight-extensions-enterpriselibrary5.svg)](https://github.com/reflectsoftware/reflectinsight-extensions-enterpriselibrary5/releases/latest)
[![NuGet Version](http://img.shields.io/nuget/v/reflectsoftware.insight.extensions.enterpriselibrary5.svg?style=flat)](http://www.nuget.org/packages/ReflectSoftware.Insight.Extensions.enterpriselibrary5/)
[![Stars](https://img.shields.io/github/stars/reflectsoftware/reflectinsight-extensions-enterpriselibrary5.svg)](https://github.com/reflectsoftware/reflectinsight-extensions-enterpriselibrary5/stargazers)

**Package** - [ReflectSoftware.Insight.Extensions.enterpriselibrary5](http://www.nuget.org/packages/ReflectSoftware.Insight.Extensions.enterpriselibrary5/) | **Platforms** - .NET 4.0

## Overview ##

The Enterprise Library extension supports v5.0 of the Logging Application Block. 

## Benefits of ReflectInsight Extensions ##

The benefits to using the Insight Extensions is that you can easily and quickly add them to your applicable with little effort and then use the ReflectInsight Viewer to view your logging in real-time, allowing you to filter, search, navigate and see the details of your logged messages.

### Specific to Enterprise Library ###

One of the nice benefits of using the Enterprise Library extension is that if your message you log is XML, then the extension will automatically transform your message into the SendXML message type which will show up in the XML syntax.

## Getting Started


```powershell
Install-Package ReflectSoftware.Insight.Extensions.EnterpriseLibrary5
```

Then in your app.config or web.config file, add the following configuration sections:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <configSections>
    <section name="enterpriseLibrary.ConfigurationSource" type="Microsoft.Practices.EnterpriseLibrary.Common.Configuration.ConfigurationSourceSection, Microsoft.Practices.EnterpriseLibrary.Common" requirePermission="true" />    
    <section name="insightSettings" type="ReflectSoftware.Insight.ConfigurationHandler,ReflectSoftware.Insight" />
  </configSections>

  <enterpriseLibrary.ConfigurationSource selectedSource="External Source">
    <sources>
      <add name="External Source" type="Microsoft.Practices.EnterpriseLibrary.Common.Configuration.FileConfigurationSource, Microsoft.Practices.EnterpriseLibrary.Common" filePath="EntLib.config" />
    </sources>
  </enterpriseLibrary.ConfigurationSource>

  <insightSettings>
    <baseSettings>
      <configChange enabled="true" />
      <propagateException enabled="false" />
      <exceptionEventTracker time="20" />
      <debugMessageProcess enabled="true" />
    </baseSettings>

    <listenerGroups active="Debug">
      <group name="Debug" enabled="true" maskIdentities="false">
        <destinations>
          <destination name="Viewer" enabled="true" filter="" details="Viewer" />
        </destinations>
      </group>
    </listenerGroups>

    <!-- Log Manager -->
    <logManager>
      <instance name="EntLibInstance" category="EntLib" bkColor="" />
    </logManager>
  </insightSettings>
    
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
  </startup>
</configuration>
```

Additional configuration details for the ReflectSoftware.Insight.Extensions.EnterpriseLibrary logging extension can be found [here](https://reflectsoftware.atlassian.net/wiki/display/RI5/Logging+Application+Block+Extension).

## Additional Resources

[Documentation](https://reflectsoftware.atlassian.net/wiki/display/RI5/ReflectInsight+5+documentation)

[Submit User Feedback](http://reflectsoftware.uservoice.com/forums/158277-reflectinsight-feedback)

[Contact Support](support@reflectsoftware.com)

[ReflectSoftware Website](http://reflectsoftware.com)
