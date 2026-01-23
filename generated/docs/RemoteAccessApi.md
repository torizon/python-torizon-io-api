# torizon_io_api.RemoteAccessApi

All URIs are relative to *https://app.torizon.io/api/v2beta*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_remote_access_device_deviceuuid_sessions**](RemoteAccessApi.md#delete_remote_access_device_deviceuuid_sessions) | **DELETE** /remote-access/device/{deviceUuid}/sessions | Delete a remote access session for a device
[**delete_remote_access_user_ip_accept_list_ip_address**](RemoteAccessApi.md#delete_remote_access_user_ip_accept_list_ip_address) | **DELETE** /remote-access/user/ip-accept-list/{ip-address} | Remove accepted ip address
[**delete_remote_access_user_public_keys_keyid**](RemoteAccessApi.md#delete_remote_access_user_public_keys_keyid) | **DELETE** /remote-access/user/public-keys/{keyId} | Remove ssh public key from user
[**get_remote_access_device_deviceuuid**](RemoteAccessApi.md#get_remote_access_device_deviceuuid) | **GET** /remote-access/device/{deviceUuid} | Fetch remote access info for a device
[**get_remote_access_device_deviceuuid_sessions**](RemoteAccessApi.md#get_remote_access_device_deviceuuid_sessions) | **GET** /remote-access/device/{deviceUuid}/sessions | get a remote access session for a device
[**get_remote_access_user_ip_accept_list**](RemoteAccessApi.md#get_remote_access_user_ip_accept_list) | **GET** /remote-access/user/ip-accept-list | Retrieve list of accepted ip addresses
[**get_remote_access_user_public_keys**](RemoteAccessApi.md#get_remote_access_user_public_keys) | **GET** /remote-access/user/public-keys | Fetch all remote-access public keys registered to a user
[**get_remote_access_user_sessions**](RemoteAccessApi.md#get_remote_access_user_sessions) | **GET** /remote-access/user/sessions | Fetch all sessions (and their related deviceId) for a user
[**post_remote_access_device_deviceuuid_sessions**](RemoteAccessApi.md#post_remote_access_device_deviceuuid_sessions) | **POST** /remote-access/device/{deviceUuid}/sessions | Create new remote access session for device
[**post_remote_access_user_ip_accept_list**](RemoteAccessApi.md#post_remote_access_user_ip_accept_list) | **POST** /remote-access/user/ip-accept-list | Add new ip to list of accepted ip addresses
[**post_remote_access_user_public_keys**](RemoteAccessApi.md#post_remote_access_user_public_keys) | **POST** /remote-access/user/public-keys | Register an ssh public key to user


# **delete_remote_access_device_deviceuuid_sessions**
> delete_remote_access_device_deviceuuid_sessions(device_uuid)

Delete a remote access session for a device


        

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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Delete a remote access session for a device
        api_instance.delete_remote_access_device_deviceuuid_sessions(device_uuid)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->delete_remote_access_device_deviceuuid_sessions: %s\n" % e)
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
**200** |  |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_remote_access_user_ip_accept_list_ip_address**
> delete_remote_access_user_ip_accept_list_ip_address(ip_address)

Remove accepted ip address


        

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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    ip_address = 'ip_address_example' # str | 

    try:
        # Remove accepted ip address
        api_instance.delete_remote_access_user_ip_accept_list_ip_address(ip_address)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->delete_remote_access_user_ip_accept_list_ip_address: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ip_address** | **str**|  | 

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

# **delete_remote_access_user_public_keys_keyid**
> delete_remote_access_user_public_keys_keyid(key_id)

Remove ssh public key from user


        

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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    key_id = 'key_id_example' # str | 

    try:
        # Remove ssh public key from user
        api_instance.delete_remote_access_user_public_keys_keyid(key_id)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->delete_remote_access_user_public_keys_keyid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_id** | **str**|  | 

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

# **get_remote_access_device_deviceuuid**
> DeviceInfo get_remote_access_device_deviceuuid(device_uuid)

Fetch remote access info for a device


        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_info import DeviceInfo
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # Fetch remote access info for a device
        api_response = api_instance.get_remote_access_device_deviceuuid(device_uuid)
        print("The response of RemoteAccessApi->get_remote_access_device_deviceuuid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->get_remote_access_device_deviceuuid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DeviceInfo**](DeviceInfo.md)

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

# **get_remote_access_device_deviceuuid_sessions**
> DeviceSession get_remote_access_device_deviceuuid_sessions(device_uuid)

get a remote access session for a device


        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.device_session import DeviceSession
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    device_uuid = 'device_uuid_example' # str | 

    try:
        # get a remote access session for a device
        api_response = api_instance.get_remote_access_device_deviceuuid_sessions(device_uuid)
        print("The response of RemoteAccessApi->get_remote_access_device_deviceuuid_sessions:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->get_remote_access_device_deviceuuid_sessions: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 

### Return type

[**DeviceSession**](DeviceSession.md)

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

# **get_remote_access_user_ip_accept_list**
> List[str] get_remote_access_user_ip_accept_list()

Retrieve list of accepted ip addresses


The accepted ip addresses are a list of public client IPV4 addresses used.
These IP addresses will be exempt from normal rate limiting by the server.
        

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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)

    try:
        # Retrieve list of accepted ip addresses
        api_response = api_instance.get_remote_access_user_ip_accept_list()
        print("The response of RemoteAccessApi->get_remote_access_user_ip_accept_list:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->get_remote_access_user_ip_accept_list: %s\n" % e)
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
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_remote_access_user_public_keys**
> PublicKeys get_remote_access_user_public_keys()

Fetch all remote-access public keys registered to a user


        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.public_keys import PublicKeys
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)

    try:
        # Fetch all remote-access public keys registered to a user
        api_response = api_instance.get_remote_access_user_public_keys()
        print("The response of RemoteAccessApi->get_remote_access_user_public_keys:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->get_remote_access_user_public_keys: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**PublicKeys**](PublicKeys.md)

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

# **get_remote_access_user_sessions**
> List[UserSession] get_remote_access_user_sessions()

Fetch all sessions (and their related deviceId) for a user


        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.user_session import UserSession
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)

    try:
        # Fetch all sessions (and their related deviceId) for a user
        api_response = api_instance.get_remote_access_user_sessions()
        print("The response of RemoteAccessApi->get_remote_access_user_sessions:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->get_remote_access_user_sessions: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**List[UserSession]**](UserSession.md)

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

# **post_remote_access_device_deviceuuid_sessions**
> post_remote_access_device_deviceuuid_sessions(device_uuid, create_session_request)

Create new remote access session for device


  A remote-access session is an entity that allows the user to connect to a device via ssh.
  All sessions have an expiration and upon expiration the connection will be terminated.

  Before creating a session the user must have at least 1 public key registered with the system.
  To create a session, a valid, registered key must be included in the request.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.create_session_request import CreateSessionRequest
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    device_uuid = 'device_uuid_example' # str | 
    create_session_request = torizon_io_api.CreateSessionRequest() # CreateSessionRequest | 

    try:
        # Create new remote access session for device
        api_instance.post_remote_access_device_deviceuuid_sessions(device_uuid, create_session_request)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->post_remote_access_device_deviceuuid_sessions: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **device_uuid** | **str**|  | 
 **create_session_request** | [**CreateSessionRequest**](CreateSessionRequest.md)|  | 

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
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_remote_access_user_ip_accept_list**
> post_remote_access_user_ip_accept_list(ip_address_request)

Add new ip to list of accepted ip addresses


The accepted ip addresses are a list of public client IPV4 addresses used.
These IP addresses will be exempt from normal rate limiting by the server.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.ip_address_request import IpAddressRequest
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    ip_address_request = torizon_io_api.IpAddressRequest() # IpAddressRequest | 

    try:
        # Add new ip to list of accepted ip addresses
        api_instance.post_remote_access_user_ip_accept_list(ip_address_request)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->post_remote_access_user_ip_accept_list: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ip_address_request** | [**IpAddressRequest**](IpAddressRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: text/plain, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Invalid value for: body |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_remote_access_user_public_keys**
> post_remote_access_user_public_keys(key_data)

Register an ssh public key to user


        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.key_data import KeyData
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
    api_instance = torizon_io_api.RemoteAccessApi(api_client)
    key_data = torizon_io_api.KeyData() # KeyData | 

    try:
        # Register an ssh public key to user
        api_instance.post_remote_access_user_public_keys(key_data)
    except Exception as e:
        print("Exception when calling RemoteAccessApi->post_remote_access_user_public_keys: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_data** | [**KeyData**](KeyData.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: text/plain, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Invalid value for: body |  -  |
**404** | Resource Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

