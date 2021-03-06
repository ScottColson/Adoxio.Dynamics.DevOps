
# Export-CrmData

## Synopsis
Exports configuration data from CRM organization into a Configuration Migration tool zip file.

## Description
This function exports CRM data based on supplied configuration migration schema file settings and saves it to a Configuration Migration tool zip file.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| CrmConnectionParameters | Hashtable | A `[hashtable]` of parameters to construct a `[Microsoft.Xrm.Tooling.Connector.CrmServiceClient]` object. See `Get-CrmConnection` for the available parameters. | true | |
| SchemaFile | String | File path to the schema file. | true | |
| ZipFile | String | File path for the created zip file. | true | |

## Examples

## Example 1
This example prepares connection parameters for the `-CrmConnectionParameters` parameter and then uses the connection to export data defined in the specified schema file to the specified zip file.
```powershell
$CrmConnectionParameters = @{
        OrganizationName = 'contoso'
        ServerUrl = 'http://dyn365.contoso.com'
        Credential = [PSCredential]::new("contoso\administrator", ("pass@word1" | ConvertTo-SecureString -AsPlainText -Force))
    }

    Export-CrmData -CrmConnectionParameters $CrmConnectionParameters -SchemaFile 'C:\temp\schema.xml' -ZipFile 'C:\temp\export\AdventureWorksData.zip'
```
