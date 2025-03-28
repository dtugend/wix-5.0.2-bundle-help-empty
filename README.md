# wix-5.0.2-bundle-help-empty
Test_setup.exe /? gives empty dialogue

## Repo

```
dotnet tool install --global wix --version 5.0.2
wix extension add -g WixToolset.Bal.wixext/5.0.2
wix extension add -g WixToolset.Netfx.wixext/5.0.2
wix extension add -g WixToolset.UI.wixext/5.0.2
wix extension add -g WixToolset.Util.wixext/5.0.2
wix build -arch x86 -culture en-US -ext "%USERPROFILE%\.wix\extensions\WixToolset.Bal.wixext\5.0.2\wixext5\WixToolset.BootstrapperApplications.wixext.dll" -ext "WixToolset.Netfx.wixext/5.0.2" -outputtype bundle -o "Test_Setup.exe" "Bundle.wxs"
```

PS: Had to use `%USERPROFILE%` for Bal extension since it does not follow the normal naming schema.
