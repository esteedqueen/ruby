# Kubernetes::ApiextensionsV1beta1Api

All URIs are relative to *https://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_custom_resource_definition**](ApiextensionsV1beta1Api.md#create_custom_resource_definition) | **POST** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions | 
[**delete_collection_custom_resource_definition**](ApiextensionsV1beta1Api.md#delete_collection_custom_resource_definition) | **DELETE** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions | 
[**delete_custom_resource_definition**](ApiextensionsV1beta1Api.md#delete_custom_resource_definition) | **DELETE** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions/{name} | 
[**get_api_resources**](ApiextensionsV1beta1Api.md#get_api_resources) | **GET** /apis/apiextensions.k8s.io/v1beta1/ | 
[**list_custom_resource_definition**](ApiextensionsV1beta1Api.md#list_custom_resource_definition) | **GET** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions | 
[**patch_custom_resource_definition**](ApiextensionsV1beta1Api.md#patch_custom_resource_definition) | **PATCH** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions/{name} | 
[**read_custom_resource_definition**](ApiextensionsV1beta1Api.md#read_custom_resource_definition) | **GET** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions/{name} | 
[**replace_custom_resource_definition**](ApiextensionsV1beta1Api.md#replace_custom_resource_definition) | **PUT** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions/{name} | 
[**replace_custom_resource_definition_status**](ApiextensionsV1beta1Api.md#replace_custom_resource_definition_status) | **PUT** /apis/apiextensions.k8s.io/v1beta1/customresourcedefinitions/{name}/status | 


# **create_custom_resource_definition**
> V1beta1CustomResourceDefinition create_custom_resource_definition(body, opts)



create a CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

body = Kubernetes::V1beta1CustomResourceDefinition.new # V1beta1CustomResourceDefinition | 

opts = { 
  pretty: "pretty_example", # String | If 'true', then the output is pretty printed.
}

begin
  result = api_instance.create_custom_resource_definition(body, opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->create_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)|  | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 

### Return type

[**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **delete_collection_custom_resource_definition**
> V1Status delete_collection_custom_resource_definition(opts)



delete collection of CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

opts = { 
  pretty: "pretty_example", # String | If 'true', then the output is pretty printed.
  continue: "continue_example", # String | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.
  field_selector: "field_selector_example", # String | A selector to restrict the list of returned objects by their fields. Defaults to everything.
  include_uninitialized: true, # BOOLEAN | If true, partially initialized resources are included in the response.
  label_selector: "label_selector_example", # String | A selector to restrict the list of returned objects by their labels. Defaults to everything.
  limit: 56, # Integer | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.
  resource_version: "resource_version_example", # String | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.
  timeout_seconds: 56, # Integer | Timeout for the list/watch call.
  watch: true # BOOLEAN | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.
}

begin
  result = api_instance.delete_collection_custom_resource_definition(opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->delete_collection_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 
 **continue** | **String**| The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional] 
 **field_selector** | **String**| A selector to restrict the list of returned objects by their fields. Defaults to everything. | [optional] 
 **include_uninitialized** | **BOOLEAN**| If true, partially initialized resources are included in the response. | [optional] 
 **label_selector** | **String**| A selector to restrict the list of returned objects by their labels. Defaults to everything. | [optional] 
 **limit** | **Integer**| limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional] 
 **resource_version** | **String**| When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it&#39;s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. | [optional] 
 **timeout_seconds** | **Integer**| Timeout for the list/watch call. | [optional] 
 **watch** | **BOOLEAN**| Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. | [optional] 

### Return type

[**V1Status**](V1Status.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **delete_custom_resource_definition**
> V1Status delete_custom_resource_definition(name, body, opts)



delete a CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

name = "name_example" # String | name of the CustomResourceDefinition

body = Kubernetes::V1DeleteOptions.new # V1DeleteOptions | 

opts = { 
  pretty: "pretty_example" # String | If 'true', then the output is pretty printed.
  grace_period_seconds: 56, # Integer | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.
  orphan_dependents: true, # BOOLEAN | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \"orphan\" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.
  propagation_policy: "propagation_policy_example" # String | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.
}

begin
  result = api_instance.delete_custom_resource_definition(name, body, opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->delete_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **String**| name of the CustomResourceDefinition | 
 **body** | [**V1DeleteOptions**](V1DeleteOptions.md)|  | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 
 **grace_period_seconds** | **Integer**| The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. | [optional] 
 **orphan_dependents** | **BOOLEAN**| Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \&quot;orphan\&quot; finalizer will be added to/removed from the object&#39;s finalizers list. Either this field or PropagationPolicy may be set, but not both. | [optional] 
 **propagation_policy** | **String**| Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. | [optional] 

### Return type

[**V1Status**](V1Status.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **get_api_resources**
> V1APIResourceList get_api_resources



get available resources

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

begin
  result = api_instance.get_api_resources
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->get_api_resources: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**V1APIResourceList**](V1APIResourceList.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: application/json, application/yaml, application/vnd.kubernetes.protobuf
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **list_custom_resource_definition**
> V1beta1CustomResourceDefinitionList list_custom_resource_definition(opts)



list or watch objects of kind CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

opts = { 
  pretty: "pretty_example", # String | If 'true', then the output is pretty printed.
  continue: "continue_example", # String | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.
  field_selector: "field_selector_example", # String | A selector to restrict the list of returned objects by their fields. Defaults to everything.
  include_uninitialized: true, # BOOLEAN | If true, partially initialized resources are included in the response.
  label_selector: "label_selector_example", # String | A selector to restrict the list of returned objects by their labels. Defaults to everything.
  limit: 56, # Integer | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.
  resource_version: "resource_version_example", # String | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.
  timeout_seconds: 56, # Integer | Timeout for the list/watch call.
  watch: true # BOOLEAN | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.
}

begin
  result = api_instance.list_custom_resource_definition(opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->list_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 
 **continue** | **String**| The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional] 
 **field_selector** | **String**| A selector to restrict the list of returned objects by their fields. Defaults to everything. | [optional] 
 **include_uninitialized** | **BOOLEAN**| If true, partially initialized resources are included in the response. | [optional] 
 **label_selector** | **String**| A selector to restrict the list of returned objects by their labels. Defaults to everything. | [optional] 
 **limit** | **Integer**| limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional] 
 **resource_version** | **String**| When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it&#39;s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. | [optional] 
 **timeout_seconds** | **Integer**| Timeout for the list/watch call. | [optional] 
 **watch** | **BOOLEAN**| Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. | [optional] 

### Return type

[**V1beta1CustomResourceDefinitionList**](V1beta1CustomResourceDefinitionList.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf, application/json;stream=watch, application/vnd.kubernetes.protobuf;stream=watch



# **patch_custom_resource_definition**
> V1beta1CustomResourceDefinition patch_custom_resource_definition(name, body, opts)



partially update the specified CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

name = "name_example" # String | name of the CustomResourceDefinition

body = nil # Object | 

opts = { 
  pretty: "pretty_example" # String | If 'true', then the output is pretty printed.
}

begin
  result = api_instance.patch_custom_resource_definition(name, body, opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->patch_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **String**| name of the CustomResourceDefinition | 
 **body** | **Object**|  | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 

### Return type

[**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: application/json-patch+json, application/merge-patch+json, application/strategic-merge-patch+json
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **read_custom_resource_definition**
> V1beta1CustomResourceDefinition read_custom_resource_definition(name, , opts)



read the specified CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

name = "name_example" # String | name of the CustomResourceDefinition

opts = { 
  pretty: "pretty_example" # String | If 'true', then the output is pretty printed.
  exact: true, # BOOLEAN | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'.
  export: true # BOOLEAN | Should this value be exported.  Export strips fields that a user can not specify.
}

begin
  result = api_instance.read_custom_resource_definition(name, , opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->read_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **String**| name of the CustomResourceDefinition | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 
 **exact** | **BOOLEAN**| Should the export be exact.  Exact export maintains cluster-specific fields like &#39;Namespace&#39;. | [optional] 
 **export** | **BOOLEAN**| Should this value be exported.  Export strips fields that a user can not specify. | [optional] 

### Return type

[**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **replace_custom_resource_definition**
> V1beta1CustomResourceDefinition replace_custom_resource_definition(name, body, opts)



replace the specified CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

name = "name_example" # String | name of the CustomResourceDefinition

body = Kubernetes::V1beta1CustomResourceDefinition.new # V1beta1CustomResourceDefinition | 

opts = { 
  pretty: "pretty_example" # String | If 'true', then the output is pretty printed.
}

begin
  result = api_instance.replace_custom_resource_definition(name, body, opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->replace_custom_resource_definition: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **String**| name of the CustomResourceDefinition | 
 **body** | [**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)|  | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 

### Return type

[**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



# **replace_custom_resource_definition_status**
> V1beta1CustomResourceDefinition replace_custom_resource_definition_status(name, body, opts)



replace status of the specified CustomResourceDefinition

### Example
```ruby
# load the gem
require 'kubernetes'
# setup authorization
Kubernetes.configure do |config|
  # Configure API key authorization: BearerToken
  config.api_key['authorization'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['authorization'] = 'Bearer'
end

api_instance = Kubernetes::ApiextensionsV1beta1Api.new

name = "name_example" # String | name of the CustomResourceDefinition

body = Kubernetes::V1beta1CustomResourceDefinition.new # V1beta1CustomResourceDefinition | 

opts = { 
  pretty: "pretty_example" # String | If 'true', then the output is pretty printed.
}

begin
  result = api_instance.replace_custom_resource_definition_status(name, body, opts)
  p result
rescue Kubernetes::ApiError => e
  puts "Exception when calling ApiextensionsV1beta1Api->replace_custom_resource_definition_status: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **String**| name of the CustomResourceDefinition | 
 **body** | [**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)|  | 
 **pretty** | **String**| If &#39;true&#39;, then the output is pretty printed. | [optional] 

### Return type

[**V1beta1CustomResourceDefinition**](V1beta1CustomResourceDefinition.md)

### Authorization

[BearerToken](../README.md#BearerToken)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json, application/yaml, application/vnd.kubernetes.protobuf



