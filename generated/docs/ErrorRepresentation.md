# ErrorRepresentation


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | 
**description** | **str** |  | 
**cause** | **object** |  | [optional] 
**error_id** | **UUID** |  | [optional] 

## Example

```python
from torizon_io_api.models.error_representation import ErrorRepresentation

# TODO update the JSON string below
json = "{}"
# create an instance of ErrorRepresentation from a JSON string
error_representation_instance = ErrorRepresentation.from_json(json)
# print the JSON string representation of the object
print(ErrorRepresentation.to_json())

# convert the object into a dict
error_representation_dict = error_representation_instance.to_dict()
# create an instance of ErrorRepresentation from a dict
error_representation_from_dict = ErrorRepresentation.from_dict(error_representation_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


