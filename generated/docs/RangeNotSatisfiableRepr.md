# RangeNotSatisfiableRepr


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
from torizon_io_api.models.range_not_satisfiable_repr import RangeNotSatisfiableRepr

# TODO update the JSON string below
json = "{}"
# create an instance of RangeNotSatisfiableRepr from a JSON string
range_not_satisfiable_repr_instance = RangeNotSatisfiableRepr.from_json(json)
# print the JSON string representation of the object
print(RangeNotSatisfiableRepr.to_json())

# convert the object into a dict
range_not_satisfiable_repr_dict = range_not_satisfiable_repr_instance.to_dict()
# create an instance of RangeNotSatisfiableRepr from a dict
range_not_satisfiable_repr_from_dict = RangeNotSatisfiableRepr.from_dict(range_not_satisfiable_repr_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


