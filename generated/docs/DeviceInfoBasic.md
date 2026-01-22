# DeviceInfoBasic


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**device_uuid** | **UUID** |  | 
**device_name** | **str** |  | 
**device_id** | **str** |  | 
**last_seen** | **datetime** |  | [optional] 
**created_at** | **datetime** |  | 
**activated_at** | **datetime** |  | [optional] 
**device_status** | [**DeviceStatus**](DeviceStatus.md) |  | 
**notes** | **str** |  | 
**tags** | **Dict[str, str]** |  | 
**hibernated** | **bool** |  | 

## Example

```python
from torizon_io_api.models.device_info_basic import DeviceInfoBasic

# TODO update the JSON string below
json = "{}"
# create an instance of DeviceInfoBasic from a JSON string
device_info_basic_instance = DeviceInfoBasic.from_json(json)
# print the JSON string representation of the object
print(DeviceInfoBasic.to_json())

# convert the object into a dict
device_info_basic_dict = device_info_basic_instance.to_dict()
# create an instance of DeviceInfoBasic from a dict
device_info_basic_from_dict = DeviceInfoBasic.from_dict(device_info_basic_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


