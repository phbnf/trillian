# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [trillian_admin_api.proto](#trillian_admin_api-proto)
    - [CreateTreeRequest](#trillian-CreateTreeRequest)
    - [DeleteTreeRequest](#trillian-DeleteTreeRequest)
    - [GetTreeRequest](#trillian-GetTreeRequest)
    - [ListTreesRequest](#trillian-ListTreesRequest)
    - [ListTreesResponse](#trillian-ListTreesResponse)
    - [UndeleteTreeRequest](#trillian-UndeleteTreeRequest)
    - [UpdateTreeRequest](#trillian-UpdateTreeRequest)
  
    - [TrillianAdmin](#trillian-TrillianAdmin)
  
- [Scalar Value Types](#scalar-value-types)



<a name="trillian_admin_api-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## trillian_admin_api.proto



<a name="trillian-CreateTreeRequest"></a>

### CreateTreeRequest
CreateTree request.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree | [Tree](#trillian-Tree) |  | Tree to be created. See Tree and CreateTree for more details. |






<a name="trillian-DeleteTreeRequest"></a>

### DeleteTreeRequest
DeleteTree request.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree_id | [int64](#int64) |  | ID of the tree to delete. |






<a name="trillian-GetTreeRequest"></a>

### GetTreeRequest
GetTree request.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree_id | [int64](#int64) |  | ID of the tree to retrieve. |






<a name="trillian-ListTreesRequest"></a>

### ListTreesRequest
ListTrees request.
No filters or pagination options are provided.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| show_deleted | [bool](#bool) |  | If true, deleted trees are included in the response. |






<a name="trillian-ListTreesResponse"></a>

### ListTreesResponse
ListTrees response.
No pagination is provided, all trees the requester has access to are
returned.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree | [Tree](#trillian-Tree) | repeated | Trees matching the list request filters. |






<a name="trillian-UndeleteTreeRequest"></a>

### UndeleteTreeRequest
UndeleteTree request.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree_id | [int64](#int64) |  | ID of the tree to undelete. |






<a name="trillian-UpdateTreeRequest"></a>

### UpdateTreeRequest
UpdateTree request.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tree | [Tree](#trillian-Tree) |  | Tree to be updated. |
| update_mask | [google.protobuf.FieldMask](#google-protobuf-FieldMask) |  | Fields modified by the update request. For example: &#34;tree_state&#34;, &#34;display_name&#34;, &#34;description&#34;. |





 

 

 


<a name="trillian-TrillianAdmin"></a>

### TrillianAdmin
Trillian Administrative interface.
Allows creation and management of Trillian trees.

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| ListTrees | [ListTreesRequest](#trillian-ListTreesRequest) | [ListTreesResponse](#trillian-ListTreesResponse) | Lists all trees the requester has access to. |
| GetTree | [GetTreeRequest](#trillian-GetTreeRequest) | [Tree](#trillian-Tree) | Retrieves a tree by ID. |
| CreateTree | [CreateTreeRequest](#trillian-CreateTreeRequest) | [Tree](#trillian-Tree) | Creates a new tree. System-generated fields are not required and will be ignored if present, e.g.: tree_id, create_time and update_time. Returns the created tree, with all system-generated fields assigned. |
| UpdateTree | [UpdateTreeRequest](#trillian-UpdateTreeRequest) | [Tree](#trillian-Tree) | Updates a tree. See Tree for details. Readonly fields cannot be updated. |
| DeleteTree | [DeleteTreeRequest](#trillian-DeleteTreeRequest) | [Tree](#trillian-Tree) | Soft-deletes a tree. A soft-deleted tree may be undeleted for a certain period, after which it&#39;ll be permanently deleted. |
| UndeleteTree | [UndeleteTreeRequest](#trillian-UndeleteTreeRequest) | [Tree](#trillian-Tree) | Undeletes a soft-deleted a tree. A soft-deleted tree may be undeleted for a certain period, after which it&#39;ll be permanently deleted. |

 



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

