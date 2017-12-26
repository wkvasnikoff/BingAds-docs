# NegativeKeywordList
Represents a negative keyword list. For more information, see [Negative Keyword](/bingads/guides/entity-hierarchy-limits#negativekeywords).
# Methods
|Method Name|Return Type|Description|
|-|-|-
[addNegativeKeyword(String keywordText)](#addnegativekeyword~string-keywordtext~)|void|Adds a keyword to the negative keywords list.
[addNegativeKeywords(String keywordText)](#addnegativekeywords~string-keywordtext~)|void|Adds a list of keywords to the negative keywords list.
[getEntityType](#getentitytype)|String|Returns the entity type.
[getId](#getid)|long|Returns the ID of this negative keyword list.
[getName](#getname)|String|Returns the name of this negative keyword list.
[setName(String name)](#setname~string-name~)|void|Sets the name of this negative keyword list.

## <a name="addnegativekeyword~string-keywordtext~"></a>addNegativeKeyword(String keywordText)
Adds a keyword to the negative keywords list. To specify match type for the new negative keyword:

- negativeKeywordList.addNegativeKeyword("shoes") - broad match.
- negativeKeywordList.addNegativeKeyword("\\"shoes\\"") - phrase match.
- negativeKeywordList.addNegativeKeyword("[leather shoes]") - exact match.


### Arguments:
|Name|Type|Description|
|-|-|-
keywordText|String|Text of the negative keyword.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="addnegativekeywords~string-keywordtext~"></a>addNegativeKeywords(String keywordText)
Adds a list of keywords to the negative keywords list. To specify match type for the new negative keyword:

- negativeKeywordsList.addNegativeKeywords(["planes", "trains"]) - broad match.
- negativeKeywordsList.addNegativeKeywords(["\\"planes\\"", "\\"trains\\""]) - phrase match.
- negativeKeywordsList.addNegativeKeywords(["[model planes]", "[toy trains]") - exact match.



### Arguments:
|Name|Type|Description|
|-|-|-
keywordTexts|String[]|Array of keyword strings.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getentitytype"></a>getEntityType
Returns the entity type. 

### Returns:
|Type|Description|
|-|-
String|Type of this entity: "NegativeKeywordList".

## <a name="getid"></a>getId
Returns the ID of this negative keyword list.

### Returns:
|Type|Description|
|-|-
long|ID of this negative keyword list.

## <a name="getname"></a>getName
Returns the name of this negative keyword list.

### Returns:
|Type|Description|
|-|-
String|Name of this negative keyword list.

## <a name="setname~string-name~"></a>setName(String name)
Sets the name of this negative keyword list.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name for this negative keyword list.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

