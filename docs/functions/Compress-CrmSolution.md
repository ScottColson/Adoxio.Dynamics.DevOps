
# Compress-CrmSolution

## Synopsis
Packages an unpacked CRM solution folder using the SolutionPackager tool.

## Description
This function packs an unpacked CRM solution folder and its individual components using the SolutionPackager tool included in the Dynamics 365 SDK. The SolutionPackager documentation is located online at https://msdn.microsoft.com/en-us/library/jj602987.aspx.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| Folder | String | The folder path to an unpacked solution. See the `/folder` parameter of the SolutionPackager tool. | true | |
| MappingXmlFile | String | The path and name of an .xml file containing file mapping directives. See the `/map` parameter of the SolutionPackager tool. | false | |
| PackageType | String | The package type to process. See the `/packagetype` parameter of the SolutionPackager tool. | true | |
| ZipFile | String | The target solution zip file to create. See the `/zipfile` parameter of the SolutionPackager tool. | true | |

## Examples

## Example 1
This example packs the AdventureWorks unmananged solution to a zip file.
```powershell
 Compress-CrmSolution -Folder 'C:\temp\solutions\AdventureWorks' -ZipFile 'C:\temp\packed\AdventureWorks.zip' -PackageType Unmanaged
```

## Example 2
This example packs the AdventureWorks unmanaged solution to a zip file and uses an XML mapping file as used by the /map parameter of the SolutionPackager tool.
```powershell
 Compress-CrmSolution -Folder 'C:\temp\solutions\AdventureWorks' -MappingXmlFile 'C:\temp\solutions\AdventureWorks.mapping.xml' -ZipFile 'C:\temp\packed\AdventureWorks.zip' -PackageType Unmanaged
```

## Example 3
This example packs the AdventureWorks managed solution to a zip file using the SolutionPackager tool. The managed version of solution must exist in the same folder as the unmanaged solution and end with the name _managed.zip (e.g. AdventureWorks_managed.zip).
```powershell
 Compress-CrmSolution -Folder 'C:\temp\solutions\AdventureWorks' -ZipFile 'C:\temp\export\AdventureWorks.zip' -PackageType Managed
```
