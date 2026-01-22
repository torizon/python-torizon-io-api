# DevicePackagesSearchParams


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**device_uuids** | **List[UUID]** |  | [optional] 
**name_contains** | **str** |  | [optional] 

## Example

```python
from torizon_io_api.models.device_packages_search_params import DevicePackagesSearchParams

# TODO update the JSON string below
json = "{}"
# create an instance of DevicePackagesSearchParams from a JSON string
device_packages_search_params_instance = DevicePackagesSearchParams.from_json(json)
# print the JSON string representation of the object
print(DevicePackagesSearchParams.to_json())

# convert the object into a dict
device_packages_search_params_dict = device_packages_search_params_instance.to_dict()
# create an instance of DevicePackagesSearchParams from a dict
device_packages_search_params_from_dict = DevicePackagesSearchParams.from_dict(device_packages_search_params_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


