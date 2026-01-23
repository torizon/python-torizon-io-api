# torizon_io_api.FleetsApi

All URIs are relative to *https://app.torizon.io/api/v2beta*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_fleets_fleetid**](FleetsApi.md#delete_fleets_fleetid) | **DELETE** /fleets/{fleetId} | Delete a fleet
[**delete_fleets_fleetid_devices**](FleetsApi.md#delete_fleets_fleetid_devices) | **DELETE** /fleets/{fleetId}/devices | Remove devices from a fleet
[**get_fleets**](FleetsApi.md#get_fleets) | **GET** /fleets | Get information about all fleets in your repository
[**get_fleets_fleetid**](FleetsApi.md#get_fleets_fleetid) | **GET** /fleets/{fleetId} | Get information about a single fleet in your repository
[**get_fleets_fleetid_devices**](FleetsApi.md#get_fleets_fleetid_devices) | **GET** /fleets/{fleetId}/devices | Get information about the devices in a single fleet
[**post_fleets**](FleetsApi.md#post_fleets) | **POST** /fleets | Create a new fleet
[**post_fleets_fleetid_devices**](FleetsApi.md#post_fleets_fleetid_devices) | **POST** /fleets/{fleetId}/devices | Add devices to a fleet
[**put_fleets_fleetid**](FleetsApi.md#put_fleets_fleetid) | **PUT** /fleets/{fleetId} | Update fleet


# **delete_fleets_fleetid**
> delete_fleets_fleetid(fleet_id)

Delete a fleet


Permanently delete a fleet. Devices in the fleet are not deleted, but are no longer associated with the deleted fleet.
        

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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Delete a fleet
        api_instance.delete_fleets_fleetid(fleet_id)
    except Exception as e:
        print("Exception when calling FleetsApi->delete_fleets_fleetid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 

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
**200** |  |  -  |
**400** | Bad Request |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_fleets_fleetid_devices**
> delete_fleets_fleetid_devices(fleet_id, request_body=request_body)

Remove devices from a fleet


Removes devices, specified by a list of device UUIDs in the body, from a specific fleet.

Note: only applicable to static fleets.
        

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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    request_body = None # List[UUID] |  (optional)

    try:
        # Remove devices from a fleet
        api_instance.delete_fleets_fleetid_devices(fleet_id, request_body=request_body)
    except Exception as e:
        print("Exception when calling FleetsApi->delete_fleets_fleetid_devices: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 
 **request_body** | [**List[UUID]**](UUID.md)|  | [optional] 

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
**416** | Range not Satisfiable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_fleets**
> PaginationResultComToradexApiGwDataFleet get_fleets(offset=offset, limit=limit)

Get information about all fleets in your repository


Returns a list of fleets along with their UUIDs.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_fleet import PaginationResultComToradexApiGwDataFleet
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
    api_instance = torizon_io_api.FleetsApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)

    try:
        # Get information about all fleets in your repository
        api_response = api_instance.get_fleets(offset=offset, limit=limit)
        print("The response of FleetsApi->get_fleets:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FleetsApi->get_fleets: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataFleet**](PaginationResultComToradexApiGwDataFleet.md)

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

# **get_fleets_fleetid**
> Fleet get_fleets_fleetid(fleet_id)

Get information about a single fleet in your repository


Returns fleet info for a single fleet.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.fleet import Fleet
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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Get information about a single fleet in your repository
        api_response = api_instance.get_fleets_fleetid(fleet_id)
        print("The response of FleetsApi->get_fleets_fleetid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FleetsApi->get_fleets_fleetid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 

### Return type

[**Fleet**](Fleet.md)

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

# **get_fleets_fleetid_devices**
> PaginationResultComToradexApiGwDataDeviceInfoBasic get_fleets_fleetid_devices(fleet_id, offset=offset, limit=limit)

Get information about the devices in a single fleet


Returns device information for all devices in the specified fleet. The schema for device data is the same as
the [GET /devices](#/Devices/getDevices) endpoint.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)

    try:
        # Get information about the devices in a single fleet
        api_response = api_instance.get_fleets_fleetid_devices(fleet_id, offset=offset, limit=limit)
        print("The response of FleetsApi->get_fleets_fleetid_devices:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FleetsApi->get_fleets_fleetid_devices: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 

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
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_fleets**
> UUID post_fleets(create_fleet)

Create a new fleet


Creates a new fleet. You must specify a fleet name and a fleet type, which can be `static` or `dynamic`.
Static fleets are the normal way of creating fleets on the Torizon platform. Dynamic fleets have an associated
pattern matching expression, and devices that match the pattern are automatically added to the group.

If you are interested in using dynamic groups, please contact support--the expression language is not fully
documented yet.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.create_fleet import CreateFleet
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
    api_instance = torizon_io_api.FleetsApi(api_client)
    create_fleet = torizon_io_api.CreateFleet() # CreateFleet | 

    try:
        # Create a new fleet
        api_response = api_instance.post_fleets(create_fleet)
        print("The response of FleetsApi->post_fleets:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FleetsApi->post_fleets: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **create_fleet** | [**CreateFleet**](CreateFleet.md)|  | 

### Return type

**UUID**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** |  |  -  |
**400** | Bad Request |  -  |
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_fleets_fleetid_devices**
> post_fleets_fleetid_devices(fleet_id, request_body=request_body)

Add devices to a fleet


Adds devices, specified by a list of device UUIDs in the body, to a specific fleet.

Note: only applicable to static fleets.
        

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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    request_body = None # List[UUID] |  (optional)

    try:
        # Add devices to a fleet
        api_instance.post_fleets_fleetid_devices(fleet_id, request_body=request_body)
    except Exception as e:
        print("Exception when calling FleetsApi->post_fleets_fleetid_devices: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 
 **request_body** | [**List[UUID]**](UUID.md)|  | [optional] 

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
**416** | Range not Satisfiable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **put_fleets_fleetid**
> put_fleets_fleetid(fleet_id, update_fleet)

Update fleet


Updates fleet information.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.update_fleet import UpdateFleet
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
    api_instance = torizon_io_api.FleetsApi(api_client)
    fleet_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    update_fleet = torizon_io_api.UpdateFleet() # UpdateFleet | 

    try:
        # Update fleet
        api_instance.put_fleets_fleetid(fleet_id, update_fleet)
    except Exception as e:
        print("Exception when calling FleetsApi->put_fleets_fleetid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **fleet_id** | **UUID**|  | 
 **update_fleet** | [**UpdateFleet**](UpdateFleet.md)|  | 

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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

