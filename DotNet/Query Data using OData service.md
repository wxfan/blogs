## Query Data using OData Service ##

1. OData standard query options
One of the benefits of OData is that it defines standard query options, as shown in the following table:
- $select: Selects which properties to include in the response.

```csharp
// GET ~/odata/Products?$select=Name,Price
``````

- $filter: Filters the results, based on a Boolean condition.

```csharp
// GET ~/odata/Products?$filter=Price gt 100
``````
- $orderby: Sorts the results.

```csharp
// GET ~/odata/Products?$orderby=Price desc
``````
- $expand: Expands related entities inline.

```csharp
// GET ~/odata/Products?$expand=Category
``````
- $top: Limits the number of results.

```csharp
// GET ~/odata/Products?$top=10
``````
- $skip: Skips the specified number of results.

```csharp
// GET ~/odata/Products?$skip=10
``````

2. OData operations
- eq: Equal
- ne: Not equal
- gt: Greater than
- ge: Greater than or equal
- lt: Less than
- le: Less than or equal
- and: Logical and
- or: Logical or
- not: Logical negation
- add: Addition
- sub: Subtraction
- mul: Multiplication
- div: Division
- mod: Modulo

```csharp
// GET ~/odata/Products?$filter=Price add 10 gt 100
``````

3. OData functions
- startswith: Returns true if the string starts with the specified substring.
```
// GET ~/odata/Products?$filter=startswith(Name, 'A')
```
- endswith: Returns true if the string ends with the specified substring.
```
// GET ~/odata/Products?$filter=endswith(Name, 'A')
```
- contains: Returns true if the string contains the specified substring.
```
// GET ~/odata/Products?$filter=contains(Name, 'A')
```
- length: Returns the length of the string.
```
// GET ~/odata/Products?$filter=length(Name) eq 5
```
- indexof: Returns the position of the first occurrence of the specified substring.
```
// GET ~/odata/Products?$filter=indexof(Name, 'A') eq 0
```
- substring: Returns a substring of the specified length, starting at the specified position.
```
// GET ~/odata/Products?$filter=substring(Name, 1, 2) eq 'BC'
```
- tolower: Converts the string to lowercase.
```
// GET ~/odata/Products?$filter=tolower(Name) eq 'abc'
```
- toupper: Converts the string to uppercase.
```
// GET ~/odata/Products?$filter=toupper(Name) eq 'ABC'
```
- trim: Removes leading and trailing whitespace.
```
// GET ~/odata/Products?$filter=trim(Name) eq 'ABC'
```
- concat: Concatenates two strings.
```
// GET ~/odata/Products?$filter=concat(Name, 'ABC') eq 'ABCABC'
```
- year: Returns the year component of the specified date.
```
// GET ~/odata/Products?$filter=year(ReleaseDate) eq 2018
```
- month: Returns the month component of the specified date.
```
// GET ~/odata/Products?$filter=month(ReleaseDate) eq 1
```
- day: Returns the day component of the specified date.
```
// GET ~/odata/Products?$filter=day(ReleaseDate) eq 1
```
- hour: Returns the hour component of the specified date.
```
// GET ~/odata/Products?$filter=hour(ReleaseDate) eq 0
```
- minute: Returns the minute component of the specified date.
```
// GET ~/odata/Products?$filter=minute(ReleaseDate) eq 0
```
- second: Returns the second component of the specified date.
```
// GET ~/odata/Products?$filter=second(ReleaseDate) eq 0
```

4. Example
```
// GET ~/odata/Products?$filter=Price gt 100 and Price lt 200
```