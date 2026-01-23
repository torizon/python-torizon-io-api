# torizon_io_api.UpdatesApi

All URIs are relative to *https://app.torizon.io/api/v2beta*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_lockboxes_lockbox_name**](UpdatesApi.md#delete_lockboxes_lockbox_name) | **DELETE** /lockboxes/{lockbox_name} | Delete a lockbox
[**get_lockbox_details**](UpdatesApi.md#get_lockbox_details) | **GET** /lockbox-details | List all existing lockboxes on the repository, and their detailed contents
[**get_lockboxes**](UpdatesApi.md#get_lockboxes) | **GET** /lockboxes | List all existing lockboxes on the repository
[**get_lockboxes_lockbox_name**](UpdatesApi.md#get_lockboxes_lockbox_name) | **GET** /lockboxes/{lockbox_name} | Get the raw Uptane metadata for a lockbox
[**patch_updates**](UpdatesApi.md#patch_updates) | **PATCH** /updates | Cancel a pending update for one or more devices
[**post_lockboxes_lockbox_name**](UpdatesApi.md#post_lockboxes_lockbox_name) | **POST** /lockboxes/{lockbox_name} | Define a new lockbox, or update an existing one
[**post_updates**](UpdatesApi.md#post_updates) | **POST** /updates | Launch an update to one or more devices or fleets


# **delete_lockboxes_lockbox_name**
> delete_lockboxes_lockbox_name(lockbox_name)

Delete a lockbox


Deletes a lockbox. The lockbox will no longer be available on GET
        

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
    api_instance = torizon_io_api.UpdatesApi(api_client)
    lockbox_name = 'lockbox_name_example' # str | 

    try:
        # Delete a lockbox
        api_instance.delete_lockboxes_lockbox_name(lockbox_name)
    except Exception as e:
        print("Exception when calling UpdatesApi->delete_lockboxes_lockbox_name: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lockbox_name** | **str**|  | 

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
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_lockbox_details**
> Dict[str, JsonSignedPayload] get_lockbox_details()

List all existing lockboxes on the repository, and their detailed contents


Returns a JSON object containing all lockbox metadata. The object has the lockbox name as a key, and the
complete metadata contents (same as returned by the [GET /lockboxes/{lockbox_name}](#/Updates/getLockboxesLockbox_name)
endpoint) as a value.

Note that _all_ lockboxes will be returned, including lockboxes that are expired, or that do not contain
any packages.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.json_signed_payload import JsonSignedPayload
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
    api_instance = torizon_io_api.UpdatesApi(api_client)

    try:
        # List all existing lockboxes on the repository, and their detailed contents
        api_response = api_instance.get_lockbox_details()
        print("The response of UpdatesApi->get_lockbox_details:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UpdatesApi->get_lockbox_details: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Dict[str, JsonSignedPayload]**](JsonSignedPayload.md)

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

# **get_lockboxes**
> List[str] get_lockboxes()

List all existing lockboxes on the repository


Returns a list of lockbox names.

Note that _all_ lockboxes will be returned, including lockboxes that are expired, or that do not contain
any packages.
        

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
    api_instance = torizon_io_api.UpdatesApi(api_client)

    try:
        # List all existing lockboxes on the repository
        api_response = api_instance.get_lockboxes()
        print("The response of UpdatesApi->get_lockboxes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UpdatesApi->get_lockboxes: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

**List[str]**

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

# **get_lockboxes_lockbox_name**
> JsonSignedPayload get_lockboxes_lockbox_name(lockbox_name, version=version)

Get the raw Uptane metadata for a lockbox


Uptane metadata defines what packages are included in a lockbox. It is signed with a key specific to the
offline updates role, and lists the valid packages (including their hashes) for a particular lockbox.

This endpoint returns the full Uptane metadata for a given lockbox.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.json_signed_payload import JsonSignedPayload
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
    api_instance = torizon_io_api.UpdatesApi(api_client)
    lockbox_name = 'lockbox_name_example' # str | 
    version = 56 # int |  (optional)

    try:
        # Get the raw Uptane metadata for a lockbox
        api_response = api_instance.get_lockboxes_lockbox_name(lockbox_name, version=version)
        print("The response of UpdatesApi->get_lockboxes_lockbox_name:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UpdatesApi->get_lockboxes_lockbox_name: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lockbox_name** | **str**|  | 
 **version** | **int**|  | [optional] 

### Return type

[**JsonSignedPayload**](JsonSignedPayload.md)

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

# **patch_updates**
> List[UUID] patch_updates(request_body=request_body)

Cancel a pending update for one or more devices


Cancels any pending update for a list of devices. Note that this endpoint does not accept fleet UUIDs,
only device UUIDs.

Updates can only be cancelled when they are Pending. After the device has received its update instructions,
the update can no longer be cancelled from the server side.
        

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
    api_instance = torizon_io_api.UpdatesApi(api_client)
    request_body = None # List[UUID] |  (optional)

    try:
        # Cancel a pending update for one or more devices
        api_response = api_instance.patch_updates(request_body=request_body)
        print("The response of UpdatesApi->patch_updates:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UpdatesApi->patch_updates: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **request_body** | [**List[UUID]**](UUID.md)|  | [optional] 

### Return type

**List[UUID]**

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
**416** | Range not Satisfiable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_lockboxes_lockbox_name**
> post_lockboxes_lockbox_name(lockbox_name, create_lockbox_request)

Define a new lockbox, or update an existing one


See the [secure offline updates](https://developer.toradex.com/torizon/torizon-platform/torizon-updates/how-to-use-secure-offline-updates-with-torizoncore/)
documentation for background on this feature.

This endpoint will create a new lockbox with the specified name, or update the contents of a previously
defined lockbox, if one with the specified name already exists.

The schema of the request body is similar to the [POST /updates](#/Updates/postUpdates) endpoint, with
the principal difference that offline updates are not assigned to specific devices or fleets. Instead,
lockboxes define which update packages are _valid_ for install via an offline update.

It is still possible to add custom metadata when generating a lockbox, but custom URIs will be ignored
during an offline update, as the device will get its files directly from the lockbox rather than fetching
over the network.

This endpoint can also be used to effectively revoke an existing lockbox. You can revoke a lockbox by
updating it so that it does not contain any packages.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.create_lockbox_request import CreateLockboxRequest
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
    api_instance = torizon_io_api.UpdatesApi(api_client)
    lockbox_name = 'lockbox_name_example' # str | 
    create_lockbox_request = torizon_io_api.CreateLockboxRequest() # CreateLockboxRequest | 

    try:
        # Define a new lockbox, or update an existing one
        api_instance.post_lockboxes_lockbox_name(lockbox_name, create_lockbox_request)
    except Exception as e:
        print("Exception when calling UpdatesApi->post_lockboxes_lockbox_name: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lockbox_name** | **str**|  | 
 **create_lockbox_request** | [**CreateLockboxRequest**](CreateLockboxRequest.md)|  | 

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

# **post_updates**
> UpdateCreateResult post_updates(update_request)

Launch an update to one or more devices or fleets


This endpoint launches a software update. You can specify a list of packages to be installed, and a list of
devices and/or fleets that the packages should be installed on. If you specify multiple packages, it will be
treated as a [synchronous update](https://developer.toradex.com/torizon/torizon-platform/torizon-updates/torizon-updates-technical-overview/#synchronous-updates-540).

It is also possible to add custom metadata or a custom download URI when creating the update. This example
sends a synchronous update containing application package `foo-1.0` and OS package `bar-1.0` to a single
device, adding a custom download URI for the application package:

```
{
  "packageIds": [
    "foo-1.0",
    "bar-1.0"
  ],
  "custom": {
    "foo-1.0": {
      "uri": "https://example.com/files/foo-1.0.yaml",
    }
  },
  "devices": [
    "3fa85f64-5717-4562-b3fc-2c963f66afa6"
  ]
}
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.update_create_result import UpdateCreateResult
from torizon_io_api.models.update_request import UpdateRequest
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
    api_instance = torizon_io_api.UpdatesApi(api_client)
    update_request = torizon_io_api.UpdateRequest() # UpdateRequest | 

    try:
        # Launch an update to one or more devices or fleets
        api_response = api_instance.post_updates(update_request)
        print("The response of UpdatesApi->post_updates:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling UpdatesApi->post_updates: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **update_request** | [**UpdateRequest**](UpdateRequest.md)|  | 

### Return type

[**UpdateCreateResult**](UpdateCreateResult.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successfully created Update |  -  |
**400** | Bad Request |  -  |
**416** | Range not Satisfiable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

