# torizon_io_api.PackagesApi

All URIs are relative to *https://app.torizon.io/api/v2beta*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_packages_packageid**](PackagesApi.md#delete_packages_packageid) | **DELETE** /packages/{packageId} | Delete a package
[**get_packages**](PackagesApi.md#get_packages) | **GET** /packages | Retrieve metadata about packages in your repository
[**get_packages_external**](PackagesApi.md#get_packages_external) | **GET** /packages_external | Retrieve metadata about packages in your repository from other sources
[**get_packages_external_info**](PackagesApi.md#get_packages_external_info) | **GET** /packages_external/info | Fetch information about external package sources
[**get_packages_external_refresh_source_file_name**](PackagesApi.md#get_packages_external_refresh_source_file_name) | **GET** /packages_external/refresh/{source_file_name} | Refresh metadata from an external package source
[**patch_packages_packageid**](PackagesApi.md#patch_packages_packageid) | **PATCH** /packages/{packageId} | Edit metadata about a package
[**post_packages**](PackagesApi.md#post_packages) | **POST** /packages | Upload a new package


# **delete_packages_packageid**
> delete_packages_packageid(package_id)

Delete a package


Deletes a package and its metadata from your repository. Once you delete a package, it will no longer be a
valid install target. Any devices that still have the deleted package installed will show as "Package not 
authorized by your repository".
        

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
    api_instance = torizon_io_api.PackagesApi(api_client)
    package_id = 'package_id_example' # str | 

    try:
        # Delete a package
        api_instance.delete_packages_packageid(package_id)
    except Exception as e:
        print("Exception when calling PackagesApi->delete_packages_packageid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **package_id** | **str**|  | 

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
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_packages**
> PaginationResultComToradexApiGwDataPackagesPackage get_packages(offset=offset, limit=limit, id_contains=id_contains, name_contains=name_contains, package_source=package_source, name=name, version=version, hardware_ids=hardware_ids, hashes=hashes, package_ids=package_ids, sort_by=sort_by, sort_direction=sort_direction)

Retrieve metadata about packages in your repository


Returns a list of packages which includes your own uploaded packages as well as Toradex published delegated targets.

Can be filtered using the documented query parameters:

   `nameContains` filters based on a pattern found in the package name

   `packageSource` filters packages based on the metadata source (commonly "targets.json" or a delegated metadata file)

   `name` filters packages with an exact match of this name
   
   `version` filters packages with an exact match of this version

   `hardwareIds` filters packages which pertain to one of the specified hardwareIds

   `hashes` filters packages which match the specified hashes

   `packageIds` filters packages which have the specified packageId. PackageId is the concatenation of {name}-{version}

Can be sorted in various ways specified with the `sortBy` and `sortDirection` parameters

        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_packages_package import PaginationResultComToradexApiGwDataPackagesPackage
from torizon_io_api.models.sort_direction import SortDirection
from torizon_io_api.models.target_items_sort import TargetItemsSort
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
    api_instance = torizon_io_api.PackagesApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)
    id_contains = 'id_contains_example' # str |  (optional)
    name_contains = 'name_contains_example' # str |  (optional)
    package_source = ['package_source_example'] # List[str] |  (optional)
    name = 'name_example' # str |  (optional)
    version = 'version_example' # str |  (optional)
    hardware_ids = ['hardware_ids_example'] # List[str] |  (optional)
    hashes = ['hashes_example'] # List[str] |  (optional)
    package_ids = ['package_ids_example'] # List[str] |  (optional)
    sort_by = torizon_io_api.TargetItemsSort() # TargetItemsSort |  (optional)
    sort_direction = torizon_io_api.SortDirection() # SortDirection |  (optional)

    try:
        # Retrieve metadata about packages in your repository
        api_response = api_instance.get_packages(offset=offset, limit=limit, id_contains=id_contains, name_contains=name_contains, package_source=package_source, name=name, version=version, hardware_ids=hardware_ids, hashes=hashes, package_ids=package_ids, sort_by=sort_by, sort_direction=sort_direction)
        print("The response of PackagesApi->get_packages:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PackagesApi->get_packages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 
 **id_contains** | **str**|  | [optional] 
 **name_contains** | **str**|  | [optional] 
 **package_source** | [**List[str]**](str.md)|  | [optional] 
 **name** | **str**|  | [optional] 
 **version** | **str**|  | [optional] 
 **hardware_ids** | [**List[str]**](str.md)|  | [optional] 
 **hashes** | [**List[str]**](str.md)|  | [optional] 
 **package_ids** | [**List[str]**](str.md)|  | [optional] 
 **sort_by** | [**TargetItemsSort**](.md)|  | [optional] 
 **sort_direction** | [**SortDirection**](.md)|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataPackagesPackage**](PaginationResultComToradexApiGwDataPackagesPackage.md)

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

# **get_packages_external**
> PaginationResultComToradexApiGwDataPackagesExternalPackage get_packages_external(offset=offset, limit=limit, id_contains=id_contains)

Retrieve metadata about packages in your repository from other sources



This endpoint is deprecated in favor of the `/packages` endpoint which now supports external packages.

This endpoint returns the list of packages in your repository that come from external sources, like
TorizonCore images published by Toradex. Can be filtered by package name.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.pagination_result_com_toradex_api_gw_data_packages_external_package import PaginationResultComToradexApiGwDataPackagesExternalPackage
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
    api_instance = torizon_io_api.PackagesApi(api_client)
    offset = 56 # int |  (optional)
    limit = 56 # int |  (optional)
    id_contains = 'id_contains_example' # str |  (optional)

    try:
        # Retrieve metadata about packages in your repository from other sources
        api_response = api_instance.get_packages_external(offset=offset, limit=limit, id_contains=id_contains)
        print("The response of PackagesApi->get_packages_external:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PackagesApi->get_packages_external: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**|  | [optional] 
 **limit** | **int**|  | [optional] 
 **id_contains** | **str**|  | [optional] 

### Return type

[**PaginationResultComToradexApiGwDataPackagesExternalPackage**](PaginationResultComToradexApiGwDataPackagesExternalPackage.md)

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

# **get_packages_external_info**
> Dict[str, DelegationInfo] get_packages_external_info()

Fetch information about external package sources


This endpoint fetches information about external package sources authorized in your repository. External
package sources are how you can safely include packages from other sources in your repository. For example,
TorizonCore OS images and bootloader binaries published by Toradex are published as an external package
source, and trusted by your repository by default.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.delegation_info import DelegationInfo
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
    api_instance = torizon_io_api.PackagesApi(api_client)

    try:
        # Fetch information about external package sources
        api_response = api_instance.get_packages_external_info()
        print("The response of PackagesApi->get_packages_external_info:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PackagesApi->get_packages_external_info: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**Dict[str, DelegationInfo]**](DelegationInfo.md)

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

# **get_packages_external_refresh_source_file_name**
> get_packages_external_refresh_source_file_name(source_file_name)

Refresh metadata from an external package source


This endpoint refreshes the list of packages in your repository that come from the specified external source.
For example "tdx-nightly.json" is the external source for all Toradex-published TorizonCore nightly builds.

External package sources can expire periodically, with the expiration date set by the external publisher. This
helps ensure that package lists remain fresh and up to date. Your devices will not install packages from an
expired source. Calling this endpoint will attempt to fetch the latest info from the external publisher.
        

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
    api_instance = torizon_io_api.PackagesApi(api_client)
    source_file_name = 'source_file_name_example' # str | 

    try:
        # Refresh metadata from an external package source
        api_instance.get_packages_external_refresh_source_file_name(source_file_name)
    except Exception as e:
        print("Exception when calling PackagesApi->get_packages_external_refresh_source_file_name: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source_file_name** | **str**|  | 

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
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **patch_packages_packageid**
> Package patch_packages_packageid(package_id, edit_package)

Edit metadata about a package


Edits the metadata about a package.

Not all metadata can be edited. The package name and version cannot be changed, and the contents of the package
cannot be changed. (You should upload a new package, with a new version number, if the contents of the package
change.) With this endpoint, you can edit custom metadata fields, package comments, external fetch URIs, and
the list of compatible components.
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.edit_package import EditPackage
from torizon_io_api.models.package import Package
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
    api_instance = torizon_io_api.PackagesApi(api_client)
    package_id = 'package_id_example' # str | 
    edit_package = torizon_io_api.EditPackage() # EditPackage | 

    try:
        # Edit metadata about a package
        api_response = api_instance.patch_packages_packageid(package_id, edit_package)
        print("The response of PackagesApi->patch_packages_packageid:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PackagesApi->patch_packages_packageid: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **package_id** | **str**|  | 
 **edit_package** | [**EditPackage**](EditPackage.md)|  | 

### Return type

[**Package**](Package.md)

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

# **post_packages**
> Package post_packages(name, version, target_format, content_length, body, hardware_id=hardware_id)

Upload a new package


Upload a new package to your repository. The file to be added should be in the body as an octet-stream, and
the content-length header must be specified. You also must supply a package name and version, and the
hardwareId(s) the package is built for (for example, `docker-compose` for an application package).
        

### Example

* Bearer Authentication (BearerAuth):

```python
import torizon_io_api
from torizon_io_api.models.package import Package
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
    api_instance = torizon_io_api.PackagesApi(api_client)
    name = 'name_example' # str | 
    version = 'version_example' # str | 
    target_format = 'target_format_example' # str | 
    content_length = 56 # int | 
    body = None # bytearray | 
    hardware_id = ['hardware_id_example'] # List[str] |  (optional)

    try:
        # Upload a new package
        api_response = api_instance.post_packages(name, version, target_format, content_length, body, hardware_id=hardware_id)
        print("The response of PackagesApi->post_packages:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PackagesApi->post_packages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **str**|  | 
 **version** | **str**|  | 
 **target_format** | **str**|  | 
 **content_length** | **int**|  | 
 **body** | **bytearray**|  | 
 **hardware_id** | [**List[str]**](str.md)|  | [optional] 

### Return type

[**Package**](Package.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/octet-stream
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | Bad Request |  -  |
**409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

