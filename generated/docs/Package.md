# Package


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**version** | **str** |  | 
**package_id** | **str** |  | 
**size** | **int** |  | 
**hashes** | **Dict[str, str]** |  | 
**package_source** | **str** |  | [optional] 
**pkg_type** | **str** |  | [optional] 
**hardware_ids** | **List[str]** |  | [optional] 
**created_at** | **datetime** |  | [optional] 
**uri** | **str** |  | [optional] 
**proprietary_meta** | **object** |  | [optional] 
**comment** | **str** |  | [optional] 

## Example

```python
from torizon_io_api.models.package import Package

# TODO update the JSON string below
json = "{}"
# create an instance of Package from a JSON string
package_instance = Package.from_json(json)
# print the JSON string representation of the object
print(Package.to_json())

# convert the object into a dict
package_dict = package_instance.to_dict()
# create an instance of Package from a dict
package_from_dict = Package.from_dict(package_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


