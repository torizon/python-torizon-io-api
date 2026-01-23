# ExternalPackage


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**delegation_origin** | **str** |  | 
**version** | **str** |  | 
**package_id** | **str** |  | 
**size** | **int** |  | 
**hashes** | **Dict[str, str]** |  | 
**pkg_type** | **str** |  | [optional] 
**hardware_ids** | **List[str]** |  | [optional] 
**created_at** | **datetime** |  | [optional] 
**uri** | **str** |  | [optional] 
**proprietary_meta** | **object** |  | [optional] 

## Example

```python
from torizon_io_api.models.external_package import ExternalPackage

# TODO update the JSON string below
json = "{}"
# create an instance of ExternalPackage from a JSON string
external_package_instance = ExternalPackage.from_json(json)
# print the JSON string representation of the object
print(ExternalPackage.to_json())

# convert the object into a dict
external_package_dict = external_package_instance.to_dict()
# create an instance of ExternalPackage from a dict
external_package_from_dict = ExternalPackage.from_dict(external_package_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


