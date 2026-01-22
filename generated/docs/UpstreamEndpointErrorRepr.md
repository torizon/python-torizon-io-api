# UpstreamEndpointErrorRepr


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
from torizon_io_api.models.upstream_endpoint_error_repr import UpstreamEndpointErrorRepr

# TODO update the JSON string below
json = "{}"
# create an instance of UpstreamEndpointErrorRepr from a JSON string
upstream_endpoint_error_repr_instance = UpstreamEndpointErrorRepr.from_json(json)
# print the JSON string representation of the object
print(UpstreamEndpointErrorRepr.to_json())

# convert the object into a dict
upstream_endpoint_error_repr_dict = upstream_endpoint_error_repr_instance.to_dict()
# create an instance of UpstreamEndpointErrorRepr from a dict
upstream_endpoint_error_repr_from_dict = UpstreamEndpointErrorRepr.from_dict(upstream_endpoint_error_repr_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


