# CustomUpdateData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uri** | **str** |  | [optional] 
**metadata** | **object** |  | [optional] 

## Example

```python
from torizon_io_api.models.custom_update_data import CustomUpdateData

# TODO update the JSON string below
json = "{}"
# create an instance of CustomUpdateData from a JSON string
custom_update_data_instance = CustomUpdateData.from_json(json)
# print the JSON string representation of the object
print(CustomUpdateData.to_json())

# convert the object into a dict
custom_update_data_dict = custom_update_data_instance.to_dict()
# create an instance of CustomUpdateData from a dict
custom_update_data_from_dict = CustomUpdateData.from_dict(custom_update_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


