# CreateSlotTypeVersion<a name="API_CreateSlotTypeVersion"></a>

Creates a new version of a slot type based on the `$LATEST` version of the specified slot type\. If the `$LATEST` version of this resource has not changed since the last version that you created, Amazon Lex doesn't create a new version\. It returns the last version that you created\. 

**Note**  
You can update only the `$LATEST` version of a slot type\. You can't update the numbered versions that you create with the `CreateSlotTypeVersion` operation\.

When you create a version of a slot type, Amazon Lex sets the version to 1\. Subsequent versions increment by 1\. For more information, see [Versioning](versioning-aliases.md#versioning-intro)\. 

This operation requires permissions for the `lex:CreateSlotTypeVersion` action\.

## Request Syntax<a name="API_CreateSlotTypeVersion_RequestSyntax"></a>

```
POST /slottypes/name/versions HTTP/1.1
Content-type: application/json

{
   "checksum": "string"
}
```

## URI Request Parameters<a name="API_CreateSlotTypeVersion_RequestParameters"></a>

The request requires the following URI parameters\.

 ** name **   
The name of the slot type that you want to create a new version for\. The name is case sensitive\.   
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([A-Za-z]_?)+$` 

## Request Body<a name="API_CreateSlotTypeVersion_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** checksum **   
Checksum for the `$LATEST` version of the slot type that you want to publish\. If you specify a checksum and the `$LATEST` version of the slot type has a different checksum, Amazon Lex returns a `PreconditionFailedException` exception and doesn't publish the new version\. If you don't specify a checksum, Amazon Lex publishes the `$LATEST` version\.  
Type: String  
Required: No

## Response Syntax<a name="API_CreateSlotTypeVersion_ResponseSyntax"></a>

```
HTTP/1.1 201
Content-type: application/json

{
   "checksum": "string",
   "createdDate": number,
   "description": "string",
   "enumerationValues": [ 
      { 
         "synonyms": [ "string" ],
         "value": "string"
      }
   ],
   "lastUpdatedDate": number,
   "name": "string",
   "valueSelectionStrategy": "string",
   "version": "string"
}
```

## Response Elements<a name="API_CreateSlotTypeVersion_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 201 response\.

The following data is returned in JSON format by the service\.

 ** checksum **   
Checksum of the `$LATEST` version of the slot type\.  
Type: String

 ** createdDate **   
The date that the slot type was created\.  
Type: Timestamp

 ** description **   
A description of the slot type\.  
Type: String  
Length Constraints: Minimum length of 0\. Maximum length of 200\.

 ** enumerationValues **   
A list of `EnumerationValue` objects that defines the values that the slot type can take\.  
Type: Array of [EnumerationValue](API_EnumerationValue.md) objects  
Array Members: Minimum number of 1 item\. Maximum number of 10000 items\.

 ** lastUpdatedDate **   
The date that the slot type was updated\. When you create a resource, the creation date and last update date are the same\.  
Type: Timestamp

 ** name **   
The name of the slot type\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 100\.  
Pattern: `^([A-Za-z]_?)+$` 

 ** valueSelectionStrategy **   
The strategy that Amazon Lex uses to determine the value of the slot\. For more information, see [PutSlotType](API_PutSlotType.md)\.  
Type: String  
Valid Values:` ORIGINAL_VALUE | TOP_RESOLUTION` 

 ** version **   
The version assigned to the new slot type version\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 64\.  
Pattern: `\$LATEST|[0-9]+` 

## Errors<a name="API_CreateSlotTypeVersion_Errors"></a>

 **BadRequestException**   
The request is not well formed\. For example, a value is invalid or a required field is missing\. Check the field values, and try again\.  
HTTP Status Code: 400

 **ConflictException**   
 There was a conflict processing the request\. Try your request again\.   
HTTP Status Code: 409

 **InternalFailureException**   
An internal Amazon Lex error occurred\. Try your request again\.  
HTTP Status Code: 500

 **LimitExceededException**   
The request exceeded a limit\. Try your request again\.  
HTTP Status Code: 429

 **NotFoundException**   
The resource specified in the request was not found\. Check the resource and try again\.  
HTTP Status Code: 404

 **PreconditionFailedException**   
 The checksum of the resource that you are trying to change does not match the checksum in the request\. Check the resource's checksum and try again\.  
HTTP Status Code: 412

## See Also<a name="API_CreateSlotTypeVersion_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/lex-models-2017-04-19/CreateSlotTypeVersion) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/lex-models-2017-04-19/CreateSlotTypeVersion) 