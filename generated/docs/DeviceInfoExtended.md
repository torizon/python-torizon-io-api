# DeviceInfoExtended


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
**hibernated** | **bool** |  | 
**last_updated** | **datetime** |  | [optional] 
**device_fleets** | [**List[Fleet]**](Fleet.md) |  | [optional] 
**device_packages** | [**List[InstalledPackage]**](InstalledPackage.md) |  | [optional] 
**tags** | **Dict[str, str]** |  | 
**network_info** | [**NetworkInfo**](NetworkInfo.md) |  | 

## Example

```python
from torizon_io_api.models.device_info_extended import DeviceInfoExtended

# TODO update the JSON string below
json = "{}"
# create an instance of DeviceInfoExtended from a JSON string
device_info_extended_instance = DeviceInfoExtended.from_json(json)
# print the JSON string representation of the object
print(DeviceInfoExtended.to_json())

# convert the object into a dict
device_info_extended_dict = device_info_extended_instance.to_dict()
# create an instance of DeviceInfoExtended from a dict
device_info_extended_from_dict = DeviceInfoExtended.from_dict(device_info_extended_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


