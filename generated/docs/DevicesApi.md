# torizon_io_api.DevicesApi

All URIs are relative to *https://app.torizon.io/api/v2beta*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_devices_deviceuuid**](DevicesApi.md#delete_devices_deviceuuid) | **DELETE** /devices/{deviceUuid} | Delete a single device
[**get_devices**](DevicesApi.md#get_devices) | **GET** /devices | Query device information
[**get_devices_deviceuuid**](DevicesApi.md#get_devices_deviceuuid) | **GET** /devices/{deviceUuid} | Get detailed information about a single device
[**get_devices_name_deviceuuid**](DevicesApi.md#get_devices_name_deviceuuid) | **GET** /devices/name/{deviceUuid} | Get the display name of a single device
[**get_devices_network**](DevicesApi.md#get_devices_network) | **GET** /devices/network | Get network information for many devices
[**get_devices_network_deviceuuid**](DevicesApi.md#get_devices_network_deviceuuid) | **GET** /devices/network/{deviceUuid} | Get network information for a single device
[**get_devices_notes_deviceuuid**](DevicesApi.md#get_devices_notes_deviceuuid) | **GET** /devices/notes/{deviceUuid} | Get the device notes for a specific device
[**get_devices_packages**](DevicesApi.md#get_devices_packages) | **GET** /devices/packages | Get information about the installed packages for many devices
[**get_devices_packages_deviceuuid**](DevicesApi.md#get_devices_packages_deviceuuid) | **GET** /devices/packages/{deviceUuid} | Get information about the installed packages for a single device
[**get_devices_token**](DevicesApi.md#get_devices_token) | **GET** /devices/token | Retrieve device provisioning token
[**get_devices_uptane_deviceuuid_assignment**](DevicesApi.md#get_devices_uptane_deviceuuid_assignment) | **GET** /devices/uptane/{deviceUuid}/assignment | Show detailed information about the currently-assigned update for a single device
[**get_devices_uptane_deviceuuid_components**](DevicesApi.md#get_devices_uptane_deviceuuid_components) | **GET** /devices/uptane/{deviceUuid}/components | Get a list of the software components reported by a single device
[**post_devices**](DevicesApi.md#post_devices) | **POST** /devices | Manually create a new device
[**put_devices_hibernation_deviceuuid**](DevicesApi.md#put_devices_hibernation_deviceuuid) | **PUT** /devices/hibernation/{deviceUuid} | Set the hibernation status of a device
[**put_devices_name_deviceuuid**](DevicesApi.md#put_devices_name_deviceuuid) | **PUT** /devices/name/{deviceUuid} | Set the display name of a single device
[**put_devices_notes_deviceuuid**](DevicesApi.md#put_devices_notes_deviceuuid) | **PUT** /devices/notes/{deviceUuid} | Set the device notes for a specific device


# **delete_devices_deviceuuid**
> delete_devices_deviceuuid(device_uuid)

Delete a single device


Permanently delete a device from your repository. Once deleted, the device will no longer be able
to connect to the server.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Delete a single device
        api_instance.delete_devices_deviceuuid(device_uuid)
    except Exception as e:
        print("Exception when calling DevicesApi->delete_devices_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices**
> PaginationResultComToradexApiGwDataDeviceInfoBasic get_devices(offset=offset, limit=limit, device_uuid=device_uuid, device_id=device_id, name_contains=name_contains, hibernated=hibernated, status=status, activated_after=activated_after, activated_before=activated_before, last_seen_start=last_seen_start, last_seen_end=last_seen_end, created_at_start=created_at_start, created_at_end=created_at_end, hardware_ids=hardware_ids, sort_by=sort_by, sort_direction=sort_direction)

Query device information


Retrieves a list of devices in your repository. This endpoint has two different modes of operation. 

* You can specify `deviceId`s and/or `deviceUuid`s any number of times as query parameters, and all
devices matching those ids will be returned.
* You can specify a number of different filter parameters, and only devices matching all of the
filter parameters you specify will be returned. Available filter parameters:
    * `nameContains`
    * `hibernated`
    * `status`
    * `activatedAfter`
    * `activatedBefore`
    * `lastSeenStart`
    * `lastSeenEnd`
    * `createdAtStart`
    * `createdAtEnd`
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_sort import DeviceSort
from torizon_io_api.models.device_sort_direction import DeviceSortDirection
from torizon_io_api.models.device_status import DeviceStatus
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_device_info_basic import PaginationResultComToradexApiGwDataDeviceInfoBasic
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)
    device_uuid = ['device_uuid_example'] # List[str] |  (optional)
    device_id = ['device_id_example'] # List[str] |  (optional)
    name_contains = 'name_contains_example' # str |  (optional)
    hibernated = True # bool |  (optional)
    status = torizon_io_api.DeviceStatus() # DeviceStatus |  (optional)
    activated_after = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    activated_before = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    last_seen_start = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    last_seen_end = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    created_at_start = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    created_at_end = '2013-10-20T19:20:30+01:00' # datetime |  (optional)
    hardware_ids = ['hardware_ids_example'] # List[str] |  (optional)
    sort_by = torizon_io_api.DeviceSort() # DeviceSort |  (optional)
    sort_direction = torizon_io_api.DeviceSortDirection() # DeviceSortDirection |  (optional)

    try:
        # Query device information
        api_response = api_instance.get_devices(offset=offset, limit=limit, device_uuid=device_uuid, device_id=device_id, name_contains=name_contains, hibernated=hibernated, status=status, activated_after=activated_after, activated_before=activated_before, last_seen_start=last_seen_start, last_seen_end=last_seen_end, created_at_start=created_at_start, created_at_end=created_at_end, hardware_ids=hardware_ids, sort_by=sort_by, sort_direction=sort_direction)
        print("The response of DevicesApi->get_devices:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 
 **device_uuid** | [**List[str]**](str.md)|  | [optional] 
 **device_id** | [**List[str]**](str.md)|  | [optional] 
 **name_contains** | **str**|  | [optional] 
 **hibernated** | **bool**|  | [optional] 
 **status** | [**DeviceStatus**](.md)|  | [optional] 
 **activated_after** | **datetime**|  | [optional] 
 **activated_before** | **datetime**|  | [optional] 
 **last_seen_start** | **datetime**|  | [optional] 
 **last_seen_end** | **datetime**|  | [optional] 
 **created_at_start** | **datetime**|  | [optional] 
 **created_at_end** | **datetime**|  | [optional] 
 **hardware_ids** | [**List[str]**](str.md)|  | [optional] 
 **sort_by** | [**DeviceSort**](.md)|  | [optional] 
 **sort_direction** | [**DeviceSortDirection**](.md)|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataDeviceInfoBasic**](PaginationResultComToradexApiGwDataDeviceInfoBasic.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_deviceuuid**
> DeviceInfoExtended get_devices_deviceuuid(device_uuid)

Get detailed information about a single device


Shows all available information about a single device. Included information:
* Name, ID, UUID, notes (if any)
* Time of provisioning, activation, latest update, and last connection to the repository
* Any fleets the device is part of
* Installed packages, if known
* Network information (local IP address, MAC, hostname)
* Device tags, if any
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_info_extended import DeviceInfoExtended
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get detailed information about a single device
        api_response = api_instance.get_devices_deviceuuid(device_uuid)
        print("The response of DevicesApi->get_devices_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DeviceInfoExtended**](DeviceInfoExtended.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_name_deviceuuid**
> DeviceNameRequest get_devices_name_deviceuuid(device_uuid)

Get the display name of a single device


Gets the display name of a device. The displayed name of the device is only a server-side concept; the device
is not aware of its display name.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_name_request import DeviceNameRequest
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get the display name of a single device
        api_response = api_instance.get_devices_name_deviceuuid(device_uuid)
        print("The response of DevicesApi->get_devices_name_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_name_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DeviceNameRequest**](DeviceNameRequest.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_network**
> PaginationResultComToradexApiGwDataNetworkInfo get_devices_network(offset=offset, limit=limit, device_uuid=device_uuid)

Get network information for many devices


Retrieves network information (local IP address, MAC, hostname) for multiple devices. A list of devices can be specified
as a query parameter; if no devices are specified will return information for all devices in the repository.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_network_info import PaginationResultComToradexApiGwDataNetworkInfo
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)
    device_uuid = ['device_uuid_example'] # List[str] |  (optional)

    try:
        # Get network information for many devices
        api_response = api_instance.get_devices_network(offset=offset, limit=limit, device_uuid=device_uuid)
        print("The response of DevicesApi->get_devices_network:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_network: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 
 **device_uuid** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataNetworkInfo**](PaginationResultComToradexApiGwDataNetworkInfo.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_network_deviceuuid**
> NetworkInfo get_devices_network_deviceuuid(device_uuid)

Get network information for a single device

Retrieves network information (local IP address, MAC, hostname) for a single device.

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.network_info import NetworkInfo
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get network information for a single device
        api_response = api_instance.get_devices_network_deviceuuid(device_uuid)
        print("The response of DevicesApi->get_devices_network_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_network_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**NetworkInfo**](NetworkInfo.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_notes_deviceuuid**
> DeviceNotesRequest get_devices_notes_deviceuuid(device_uuid)

Get the device notes for a specific device


Gets the device notes for a device. Device notes are shown in the web UI, and can be used to store additional
information about the device.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_notes_request import DeviceNotesRequest
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get the device notes for a specific device
        api_response = api_instance.get_devices_notes_deviceuuid(device_uuid)
        print("The response of DevicesApi->get_devices_notes_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_notes_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DeviceNotesRequest**](DeviceNotesRequest.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_packages**
> PaginationResultComToradexApiGwDataDevicePackages get_devices_packages(offset=offset, limit=limit, device_uuid=device_uuid, name_contains=name_contains)

Get information about the installed packages for many devices


Returns a list of devices and the packages those devices have installed. A list of devices can be specified as
a query parameter; if no devices are specified will return information for all devices in the repository.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_device_packages import PaginationResultComToradexApiGwDataDevicePackages
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)
    device_uuid = ['device_uuid_example'] # List[str] |  (optional)
    name_contains = 'name_contains_example' # str |  (optional)

    try:
        # Get information about the installed packages for many devices
        api_response = api_instance.get_devices_packages(offset=offset, limit=limit, device_uuid=device_uuid, name_contains=name_contains)
        print("The response of DevicesApi->get_devices_packages:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_packages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 
 **device_uuid** | [**List[str]**](str.md)|  | [optional] 
 **name_contains** | **str**|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataDevicePackages**](PaginationResultComToradexApiGwDataDevicePackages.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |
**416** | Range not Satisfiable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_packages_deviceuuid**
> DevicePackages get_devices_packages_deviceuuid(device_uuid)

Get information about the installed packages for a single device

Returns a list of the packages installed on the device.

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_packages import DevicePackages
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get information about the installed packages for a single device
        api_response = api_instance.get_devices_packages_deviceuuid(device_uuid)
        print("The response of DevicesApi->get_devices_packages_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_packages_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DevicePackages**](DevicePackages.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_token**
> ProvisionInfo get_devices_token()

Retrieve device provisioning token


Retrieves a short-lived access token that can only be used to provision device

### NOTE:
Typical users of this API can create devices directly with their API token and will
have no use for calling this endpoint. 
This endpoint is intended to be used to generate a short-lived access token solely used
to provision a device. (Like the Torizon Web App)
                

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.provision_info import ProvisionInfo
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)

    try:
        # Retrieve device provisioning token
        api_response = api_instance.get_devices_token()
        print("The response of DevicesApi->get_devices_token:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_token: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ProvisionInfo**](ProvisionInfo.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_uptane_deviceuuid_assignment**
> List[QueueResponse] get_devices_uptane_deviceuuid_assignment(device_uuid)

Show detailed information about the currently-assigned update for a single device


Returns the device's current update assignment, if any.

Update assignments are an Uptane concept. The assignment is what the device will be instructed to install,
the next time it checks for an update. An update assignment does not necessarily mean the device will install
an update. If, for example, the device reports that it already has all of the assigned software components
installed, it will take no further action.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.queue_response import QueueResponse
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Show detailed information about the currently-assigned update for a single device
        api_response = api_instance.get_devices_uptane_deviceuuid_assignment(device_uuid)
        print("The response of DevicesApi->get_devices_uptane_deviceuuid_assignment:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_uptane_deviceuuid_assignment: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**List[QueueResponse]**](QueueResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_devices_uptane_deviceuuid_components**
> List[EcuInfoResponse] get_devices_uptane_deviceuuid_components(device_uuid)

Get a list of the software components reported by a single device


Returns a list of the device components.

Components are an Uptane concept. In the Uptane standard, they are normally referred to as "ECUs", and
represent individual discrete hardware modules in a vehicle. In TorizonCore, we use this concept to allow
updates to be sent independently to different software components of the system.

In particular, TorizonCore devices will normally have at least two components: one for the base OS, and
one for the application software.

Components have an ID (assumed to be the component's serial number in the automotive case) and a hardwareID
(an indicator of the make or model of the component, for determining firmware/package compatibility). In
TorizonCore, we give the application component the hardwareID "docker-compose", and the base OS component a
hardwareID corresponding to the SoM's model (e.g. "apalis-imx8").

This endpoint returns a list of the components registered on the device, and the current software image
installed on each one, if known.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.ecu_info_response import EcuInfoResponse
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Get a list of the software components reported by a single device
        api_response = api_instance.get_devices_uptane_deviceuuid_components(device_uuid)
        print("The response of DevicesApi->get_devices_uptane_deviceuuid_components:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->get_devices_uptane_deviceuuid_components: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**List[EcuInfoResponse]**](EcuInfoResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_devices**
> bytearray post_devices(device_create_req)

Manually create a new device


Creates a new device in your repository, returning the device credentials as a zipfile. This should not normally
be used; the usual way to add a device is for the device itself to call this endpoint, using a short-lived
provisioning token (for example, as retrieved from the [GET /devices/token](#/Devices/getDevicesToken) endpoint).

You can use this endpoint to create devices in bulk, but you will then have to manually provision the individual
credentials onto each device.

`deviceId` must be specified. `deviceName` is optional; if not specified a random name will be generated.
The `hibernated` parameter is optional, and defaults to `false`. If `hibernated` is set to `true`,
the device will automatically be placed in hibernation mode as soon as it is created.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_create_req import DeviceCreateReq
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_create_req = torizon_io_api.DeviceCreateReq() # DeviceCreateReq | 

    try:
        # Manually create a new device
        api_response = api_instance.post_devices(device_create_req)
        print("The response of DevicesApi->post_devices:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DevicesApi->post_devices: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_create_req** | [**DeviceCreateReq**](DeviceCreateReq.md)|  | 

### Return type

**bytearray**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/octet-stream, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **put_devices_hibernation_deviceuuid**
> put_devices_hibernation_deviceuuid(device_uuid, update_hibernation_status_request)

Set the hibernation status of a device


Devices can be placed in _hibernation_ mode. When a device is hibernated, Torizon Cloud will respond to almost
all requests from the device with a 403 HTTP status. It won't be able to check for or receive updates, send
metrics, or be available for remote access.

Depending on your plan and billing contract, a hibernated device may not count towards your billable device
quota. If you aren't sure how hibernated devices will affect your bill, contact Toradex sales.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.update_hibernation_status_request import UpdateHibernationStatusRequest
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 
    update_hibernation_status_request = torizon_io_api.UpdateHibernationStatusRequest() # UpdateHibernationStatusRequest | 

    try:
        # Set the hibernation status of a device
        api_instance.put_devices_hibernation_deviceuuid(device_uuid, update_hibernation_status_request)
    except Exception as e:
        print("Exception when calling DevicesApi->put_devices_hibernation_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 
 **update_hibernation_status_request** | [**UpdateHibernationStatusRequest**](UpdateHibernationStatusRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **put_devices_name_deviceuuid**
> put_devices_name_deviceuuid(device_uuid, device_name_request)

Set the display name of a single device


Sets the display name of a device. The displayed name of the device is only a server-side concept; the device
is not aware of its display name.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_name_request import DeviceNameRequest
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 
    device_name_request = torizon_io_api.DeviceNameRequest() # DeviceNameRequest | 

    try:
        # Set the display name of a single device
        api_instance.put_devices_name_deviceuuid(device_uuid, device_name_request)
    except Exception as e:
        print("Exception when calling DevicesApi->put_devices_name_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 
 **device_name_request** | [**DeviceNameRequest**](DeviceNameRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **put_devices_notes_deviceuuid**
> put_devices_notes_deviceuuid(device_uuid, device_notes_request)

Set the device notes for a specific device


Sets the device notes for a device. Device notes are shown in the web UI, and can be used to store additional
information about the device. Accepts a string up to approximately 64kb; will be rendered as Markdown in the
web UI.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_notes_request import DeviceNotesRequest
from torizon_io_api.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://app.torizon.io/api/v2beta
# See configuration.py for a list of all supported configuration parameters.
configuration = torizon_io_api.Configuration(
    host = "https://app.torizon.io/api/v2beta"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = torizon_io_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with torizon_io_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = torizon_io_api.DevicesApi(api_client)
    device_uuid = 'device_uuid_example' # str | 
    device_notes_request = torizon_io_api.DeviceNotesRequest() # DeviceNotesRequest | 

    try:
        # Set the device notes for a specific device
        api_instance.put_devices_notes_deviceuuid(device_uuid, device_notes_request)
    except Exception as e:
        print("Exception when calling DevicesApi->put_devices_notes_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 
 **device_notes_request** | [**DeviceNotesRequest**](DeviceNotesRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

