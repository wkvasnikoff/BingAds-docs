# KeywordOperation
Represents the definition of a keyword constructed via [KeywordBuilder](./KeywordBuilder). The keyword is added to the campaign only when one of this object's methods is invoked or when the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[Keyword](./Keyword)|Returns the newly created keyword, otherwise returns null if this operation failed to execute.
[isSuccessful](#issuccessful)|boolean|Returns a Boolean value that determines if this operation was successful.

## <a name="geterrors"></a>getErrors
Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.

### Returns:
|Type|Description|
|-|-
String[]|An empty array if the keyword is successfully created; otherwise, it contains the list of errors.

## <a name="getresult"></a>getResult
Returns the newly created keyword, otherwise returns null if this operation failed to execute.

### Returns:
|Type|Description|
|-|-
[Keyword](./Keyword)|Newly created keyword, otherwise returns null if this operation failed to execute.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that determines if this operation was successful.

### Returns:
|Type|Description|
|-|-
boolean|Boolean value that determines if this operation was successful.

