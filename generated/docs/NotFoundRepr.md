# NotFoundRepr


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**msg** | **str** |  | 
**description** | **object** |  | [optional] 
**code** | **str** |  | 
**cause** | **object** |  | [optional] 
**error_id** | **UUID** |  | [optional] 

## Example

```python
from torizon_io_api.models.not_found_repr import NotFoundRepr

# TODO update the JSON string below
json = "{}"
# create an instance of NotFoundRepr from a JSON string
not_found_repr_instance = NotFoundRepr.from_json(json)
# print the JSON string representation of the object
print(NotFoundRepr.to_json())

# convert the object into a dict
not_found_repr_dict = not_found_repr_instance.to_dict()
# create an instance of NotFoundRepr from a dict
not_found_repr_from_dict = NotFoundRepr.from_dict(not_found_repr_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


