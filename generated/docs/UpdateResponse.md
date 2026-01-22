# UpdateResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**update_id** | **UUID** |  | 
**status** | **str** |  | 
**created_at** | **datetime** |  | 
**scheduled_for** | **datetime** |  | [optional] 
**completed_at** | **datetime** |  | [optional] 
**device_result** | [**UpdateReportedResult**](UpdateReportedResult.md) |  | [optional] 
**packages** | **Dict[str, str]** |  | 

## Example

```python
from torizon_io_api.models.update_response import UpdateResponse

# TODO update the JSON string below
json = "{}"
# create an instance of UpdateResponse from a JSON string
update_response_instance = UpdateResponse.from_json(json)
# print the JSON string representation of the object
print(UpdateResponse.to_json())

# convert the object into a dict
update_response_dict = update_response_instance.to_dict()
# create an instance of UpdateResponse from a dict
update_response_from_dict = UpdateResponse.from_dict(update_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


