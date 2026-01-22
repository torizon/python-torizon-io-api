# ConflictRepr


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**msg** | **str** |  | 
**description** | [**AnyOf**](AnyOf.md) |  | [optional] 
**code** | **str** |  | 
**cause** | [**AnyOf**](AnyOf.md) |  | [optional] 
**error_id** | **UUID** |  | [optional] 

## Example

```python
from torizon_io_api.models.conflict_repr import ConflictRepr

# TODO update the JSON string below
json = "{}"
# create an instance of ConflictRepr from a JSON string
conflict_repr_instance = ConflictRepr.from_json(json)
# print the JSON string representation of the object
print(ConflictRepr.to_json())

# convert the object into a dict
conflict_repr_dict = conflict_repr_instance.to_dict()
# create an instance of ConflictRepr from a dict
conflict_repr_from_dict = ConflictRepr.from_dict(conflict_repr_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


