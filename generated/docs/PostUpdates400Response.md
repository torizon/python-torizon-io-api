# PostUpdates400Response


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
from torizon_io_api.models.post_updates400_response import PostUpdates400Response

# TODO update the JSON string below
json = "{}"
# create an instance of PostUpdates400Response from a JSON string
post_updates400_response_instance = PostUpdates400Response.from_json(json)
# print the JSON string representation of the object
print(PostUpdates400Response.to_json())

# convert the object into a dict
post_updates400_response_dict = post_updates400_response_instance.to_dict()
# create an instance of PostUpdates400Response from a dict
post_updates400_response_from_dict = PostUpdates400Response.from_dict(post_updates400_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


