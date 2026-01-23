# EcuInfoImage


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**filepath** | **str** |  | 
**size** | **int** |  | 
**hash** | **str** |  | 

## Example

```python
from torizon_io_api.models.ecu_info_image import EcuInfoImage

# TODO update the JSON string below
json = "{}"
# create an instance of EcuInfoImage from a JSON string
ecu_info_image_instance = EcuInfoImage.from_json(json)
# print the JSON string representation of the object
print(EcuInfoImage.to_json())

# convert the object into a dict
ecu_info_image_dict = ecu_info_image_instance.to_dict()
# create an instance of EcuInfoImage from a dict
ecu_info_image_from_dict = EcuInfoImage.from_dict(ecu_info_image_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


