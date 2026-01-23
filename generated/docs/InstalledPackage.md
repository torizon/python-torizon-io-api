# InstalledPackage


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**component** | **str** |  | 
**installed** | [**PackageInfo**](PackageInfo.md) |  | 

## Example

```python
from torizon_io_api.models.installed_package import InstalledPackage

# TODO update the JSON string below
json = "{}"
# create an instance of InstalledPackage from a JSON string
installed_package_instance = InstalledPackage.from_json(json)
# print the JSON string representation of the object
print(InstalledPackage.to_json())

# convert the object into a dict
installed_package_dict = installed_package_instance.to_dict()
# create an instance of InstalledPackage from a dict
installed_package_from_dict = InstalledPackage.from_dict(installed_package_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


