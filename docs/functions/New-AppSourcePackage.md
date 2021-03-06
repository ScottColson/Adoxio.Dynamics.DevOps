
# New-AppSourcePackage

## Synopsis
Creates an AppSource package.

## Description
This function creates an AppSource package as described at https://docs.microsoft.com/en-us/azure/marketplace/cloud-partner-portal-orig/appsource-package-preparation.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| LogoPath | String | The file path to the logo file. | true | |
 | TermsOfUsePath | String | The file path to the terms of use file. | true | |
 | InputXmlPath | String | The file path to the input.xml file. | true | |
 | PackageFolder | String | The folder containing the package contents. This can be ommitted if the package has been created beforehand using `New-CrmPackage` and using the default behavior of using the `Adoxio.Dynamics.ImportPackage` folder. | false | `"$(GetPackageDeployerFolder)\Adoxio.Dynamics.ImportPackage"` |
 | PackageAssembly | String | The package assembly for importing the package. This can be ommitted if the package has been created beforehand using `New-CrmPackag`e and using the default behavior of using the `Adoxio.Dynamics.ImportPackage.dll` assembly. | false | `"$(GetPackageDeployerFolder)\Adoxio.Dynamics.ImportPackage.dll"` |
 | DestinationPath | String | The file path to save the AppSource package zip file. | true | |


