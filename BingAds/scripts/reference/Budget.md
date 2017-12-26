# Budget
Represents a budget. For more information, see [Budget](/bingads/guides/entity-hierarchy-limits#budget).
# Methods
|Method Name|Return Type|Description|
|-|-|-
[getAmount](#getamount)|double|Returns the budget's amount in the account's currency.
[getDeliveryMethod](#getdeliverymethod)|String|Returns the delivery method for this budget.
[setAmount(double amount)](#setamount~double-amount~)|void|Sets the budget's amount (in the account's currency) to the specified value.
[setDeliveryMethod(String method)](#setdeliverymethod~string-method~)|void|Set the delivery method for this budget.

## <a name="getamount"></a>getAmount
Returns the budget's amount in the account's currency.

### Returns:
|Type|Description|
|-|-
double|Amount of the budget.

## <a name="getdeliverymethod"></a>getDeliveryMethod
Returns the delivery method for this budget.  Possible return values are:

- STANDARD
- ACCELERATED

For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1).


### Returns:
|Type|Description|
|-|-
String|Delivery method of the budget.

## <a name="setamount~double-amount~"></a>setAmount(double amount)
Sets the budget's amount (in the account's currency) to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
amount|double|Amount of the budget.
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setdeliverymethod~string-method~"></a>setDeliveryMethod(String method)
Set the delivery method for this budget. Supported values are:

- STANDARD
- ACCELERATED

For more information, see [What are my budget options?](https://help.bingads.microsoft.com/#apex/3/en/51006/1).


### Arguments:
|Name|Type|Description|
|-|-|-
method|String|Sets the delivery method of the budget.<br />
### Returns:
|Type|Description|
|-|-
void|Returns nothing.

