# BadRequestRepr


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
from torizon_io_api.models.bad_request_repr import BadRequestRepr

# TODO update the JSON string below
json = "{}"
# create an instance of BadRequestRepr from a JSON string
bad_request_repr_instance = BadRequestRepr.from_json(json)
# print the JSON string representation of the object
print(BadRequestRepr.to_json())

# convert the object into a dict
bad_request_repr_dict = bad_request_repr_instance.to_dict()
# create an instance of BadRequestRepr from a dict
bad_request_repr_from_dict = BadRequestRepr.from_dict(bad_request_repr_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


