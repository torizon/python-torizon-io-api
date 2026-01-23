# EditPackage


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hardware_ids** | **List[str]** |  | [optional] 
**uri** | **str** |  | [optional] 
**proprietary_meta** | **object** |  | [optional] 
**comment** | **str** |  | [optional] 

## Example

```python
from torizon_io_api.models.edit_package import EditPackage

# TODO update the JSON string below
json = "{}"
# create an instance of EditPackage from a JSON string
edit_package_instance = EditPackage.from_json(json)
# print the JSON string representation of the object
print(EditPackage.to_json())

# convert the object into a dict
edit_package_dict = edit_package_instance.to_dict()
# create an instance of EditPackage from a dict
edit_package_from_dict = EditPackage.from_dict(edit_package_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


