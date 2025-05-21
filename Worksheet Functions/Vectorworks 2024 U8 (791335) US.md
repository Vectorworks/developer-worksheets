## Contents
- [General](#general)
- [Logic](#logic)
- [Lookup](#lookup)
- [Math](#math)
- [Objects](#objects)
  - [General](#general)
  - [Legacy](#legacy)
  - [Material](#material)
- [Specialized for Adapter](#specialized-for-adapter)
- [Specialized for Circuit](#specialized-for-circuit)
- [Specialized for Curtain Wall](#specialized-for-curtain-wall)
- [Specialized for Device](#specialized-for-device)
- [Specialized for Door](#specialized-for-door)
- [Specialized for Door CW](#specialized-for-door-cw)
- [Specialized for Fence](#specialized-for-fence)
- [Specialized for Hardscape](#specialized-for-hardscape)
- [Specialized for Hedgerow](#specialized-for-hedgerow)
- [Specialized for Landscape Area](#specialized-for-landscape-area)
- [Specialized for Lighting Device](#specialized-for-lighting-device)
- [Specialized for Marionette Object](#specialized-for-marionette-object)
- [Specialized for Panel Connector](#specialized-for-panel-connector)
- [Specialized for Plant](#specialized-for-plant)
- [Specialized for Railing](#specialized-for-railing)
- [Specialized for Railing/Fence](#specialized-for-railingfence)
- [Specialized for Roof](#specialized-for-roof)
- [Specialized for Site Model](#specialized-for-site-model)
- [Specialized for Slab](#specialized-for-slab)
- [Specialized for Socket](#specialized-for-socket)
- [Specialized for Space](#specialized-for-space)
- [Specialized for Structural Member](#specialized-for-structural-member)
- [Specialized for Wall](#specialized-for-wall)
- [Specialized for WinDoor 6.0](#specialized-for-windoor-60)
- [Specialized for Window](#specialized-for-window)
- [Specialized for Window CW](#specialized-for-window-cw)
- [Text](#text)

___

## General


#### __RunScript(scriptPath [, functionName])__ ####

Executes a script and returns the result value.


```python
Database header cell:
=RunScript('My Script') executes the VectorScript script named “My Script” and returns a value for each object in the database

Spreadsheet cell:
=RunScript(2, 'ScriptFile.py', 2, 1) executes the Python script “ScriptFile.py” in the Vectorworks Plug-Ins folder, passing the parameters “2” and “1,” and returns a value

```

#### __FormatField(record_format_name, field_name)__ ####

Returns the default value of a given field name of the specified record format.


```python
=FormatField(‘Door’, ‘Width’), where “Door” is the name of a record format, returns the default value for the “Width” field.


```

#### __RunScriptEdit(scriptPath [, functionName])__ ####

Executes a script and returns the result value. The cells are editable and the same script is executed to handle the edit.



#### __Database(criteria)__ ####

Creates a database of objects that meet the criteria.


```python
=DATABASE((L='Floor-1')) creates a worksheet database of all objects on layer “Floor-1.”

```

#### __DatabaseByScript([scriptPath], scriptName, ...params...)__ ####

Runs a script to create a database of objects.


```python
=DataBaseByScript('MyScript.py', 2, 1) creates a worksheet database by executing the script named “My Script.py,” passing the parameters “2” and “1” to the script.

```

## Logic


#### __Switch(number, value1, value2, ... value_no_match)__ ####

Use value1, or value2, or value3, etc depending on the (number). When no value is available, then use value_no_match.


```python
=switch(3, 10, 20, 30, 40, 50, 60, 'no match') returns 30

```

#### __IFS((logic1), value1, (logic2), value2, ..., (logicN), valueN))__ ####

One of several possible results based on a series of tests. The first value which passes the test is chosen.


```python
=IFS(A4>30, 'yes', A4<=30, 'no') returns 'yes' if the number in the cell A4 is >30. Else, if it is <=30 'no' is returned

If the final LogicN is ELSE then the final ValueN will be applied to all items that do not match a Logic earlier in the list.
=IFS( COND1; VALUE1; COND2; VALUE2; ELSE; 'ELSE' )
```

#### __Exact(value1, value2)__ ####

True when the two values are exactly the same. It will perform a case-sensitive comparison if the values are strings.


```python
=exact('text', 'text') returns True, while exact('Text', 'text') will return False.

```

#### __IsNA(value)__ ####

True when the value is N/A.


```python
=IF(IsNA(Angle('energos')), '-', 'has value') On a database row, calculates the Energos angle of the objects, and decides which value to output based on if energos is applicable or not.

Note, you can use IfNA in order to use alternative value only when it's not applicable, the 'Angle' would have to be repeated for the IF function.


```

#### __IfNA(value, value_when_na)__ ####

Use value_when_na when value resolves to N/A, otherwise use the value itself.


```python
=IfNA(Angle('energos'), '-') On a database row, calculates the Energos angle of the objects, and if they are not applicable, would use '-'


```

#### __FirstNonEmpty(value1, value2, value3, ...)__ ####

Use value1 if not empty, otherwise use value2 if not empty, otherwise use value3 if not empty, etc. Empty means: empty string, zero value, or N/A value. N/A will be returned if no match.


```python
=FirstNonEmpty('Format-1'.'data', B1, 'Empty')

Return the value of the data field of the Format-1, if empty return B1, or the string 'Empty' if that is empty too.


```

#### __IsError(value)__ ####

True when the value resolves to an error.



#### __IfError(value, value_when_error)__ ####

Use value_when_error when value resolved to an error, otherwise use the value itself.



#### __if((logical_test), value_if_true, value_if_false)__ ####

Use value_if_true if logical_test is true, value_is_false if logical_test is false.


```python
=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition') If no condition value was set for the existing tree object, the value in this cell is a dash; otherwise, the value in this cell is the condition value that was set for the tree object.

=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition')

```

## Lookup


#### __VLookup(value, [use_pattern], result_col_index, not_found_value, table)__ ####

Finds a value in the table range, looking at the leftmost column, and returns the value at the result_col_index in that same row. Uses ECMAScript syntax for the pattern: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


```python
=VLookup(value, [use_pattern], result_col_index, not_found_value, table)

Find a value in the table range, looking at the first column, and return the value at the resut_col_index of that row.

Parameters:
  value - the value that will be searched in the first column of 'table'.
  use_pattern - use regular expression pattern for the search.
  result_col_index - the number of the column in 'table' which will return the result_col_index.
  not_found_value - the result if 'value' is not found
  table - a range referencing the data. the first column will be searched, and 'result_col_index' will specify the result.

=VLookup(A3, 2, 'no email', B1..C4)
=VLookup(A3, 2, 'no email', 'Worksheet-1':B1..C4)

This example will search for the value of A3 in column B, and if found it will return the value in the C column, otherwise it will return 'no email'.

If the table is like this, 'tech' will be searched in B column, and it will return 'tech@vectorworks.net'
Note the second example, the table is a range for another worksheet named 'Worksheet-1'

  |    A   |     B     |     C
-------------------------------------------------
1 |        |  support  | support@vectorworks.net
2 |        |  tech     | tech@vectorworks.net
3 |  tech  |  PR       | PR@vectorworks.net

When [use_pattern] is missing or "false", the "value" will be matched exactly when looking up.
When [use_pattern] is "true" then the "value" is expected to be a regular expression that will be used when looking up.
Here is more information of the syntax of the regular rexpressions: https://cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript
And here is a web-tool that can help developing and testing regular expressions: https://regexr.com/
```

#### __XLookup(value, [use_pattern], not_found_value, array_lookup, array_result)__ ####

Finds a value in the array_lookup, and returns the value from the array_result at the found row. The arrays should be ranges on the same column. Uses ECMAScript syntax for the pattern: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


```python
=XLookup(value, [use_pattern], not_found_value, array_lookup, array_result)

Find a value in the array_lookup, and return the value from the array_result at the found row. the arrays should be ranges on the same column.

Parameters:
  value - the value that will be searched in 'array_lookup' (a range defined in a single column).
  use_pattern - use regular expression pattern for the search.
  not_found_value - the result if 'value' is not found
  array_lookup - a range defined in a single column to search the 'value' in
  array_result - a range defined in a single column to to provide the result from the row that the 'value' was found in 'array_lookup'

=XLookup('tech', 'not found', 'Worksheet-Values':A1..A3, 'Worksheet-Result':B1..B3)

Named worksheet: 'Worksheet-Values':

  |     A     
--------------
1 |  support
2 |  tech
3 |  PR       

Named worksheet: 'Worksheet-Result':

  |   A    |     B
-----------|-------------------------
1 |  1234  | support@vectorworks.net
2 |  1235  | tech@vectorworks.net
3 |  1236  | PR@vectorworks.net

When [use_pattern] is missing or "false", the "value" will be matched exactly when looking up.
When [use_pattern] is "true" then the "value" is expected to be a regular expression that will be used when looking up.
Here is more information of the syntax of the regular rexpressions: https://cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript
And here is a web-tool that can help developing and testing regular expressions: https://regexr.com/
```

## Math


#### __round(number)__ ####

Rounds the specified number to the nearest whole number.


```python
=round(2.345) returns 2

```

#### __sin(number)__ ####

Returns the sine of a given angle.


```python
=sin(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the sine of the angle

```

#### __cos(number)__ ####

Returns the cosine of a given angle.


```python
=cos(deg2rad(23)) converts a 23-degree angle to its radian equivalent, and returns the cosine of the angle

```

#### __exp(number)__ ####

Returns e raised to the power of number.


```python
=exp(2) returns the numeric value of e raised to the power of 2

```

#### __ln(number)__ ####

Returns the natural logarithm (base e) of a number.


```python
=ln(12) returns the natural logarithm of 12

```

#### __sqrt(number)__ ####

Returns the square root of a number.


```python
=sqrt(D27) returns the square root of the number in cell D27

```

#### __atan(number)__ ####

Returns the arctangent of a number.


```python
=atan(A3) returns the angle for which the tangent value is given in cell A3

```

#### __rad2deg(number)__ ####

Converts number from radians to degrees.


```python
=rad2deg(0.5235987) converts the radian angle measurement to its degree equivalent

```

#### __deg2rad(number)__ ####

Converts number from degrees to radians.


```python
=deg2rad(47) converts the 47-degree angle measurement to its radian equivalent

```

#### __asin(number)__ ####

Returns the arcsine of a number.


```python
=asin(A3) returns the angle for which the sine value is given in cell A3

```

#### __acos(number)__ ####

Returns the arccosine of a number.


```python
=acos(3/5) returns the angle for which the cosine value is 3/5

```

#### __rounddown(number, digits)__ ####

Rounds the specified number down to a specified number of decimal digits.


```python
=rounddown(2.345, 2) returns 2.34

```

#### __roundup(number, digits)__ ####

Rounds the specified number up to a specified number of decimal digits.


```python
=roundup(2.345, 2) returns 2.35

```

#### __abs(number)__ ####

The absolute value of a number.


```python
=abs(-12) returns the absolute value of the number -12

```

#### __quotient(numerator, denominator)__ ####

Computes the quotient of an integer division.


```python
=quotient(5, 2) returns 2

You can clculate the remainder by using the MOD operator
=5 MOD 2
```

#### __gcd(number1, number2, …)__ ####

The greatest common divisor of a group of numbers.


```python
=gcd(5, 10, 20) returns 5

```

#### __lcm(number1, number2, …)__ ####

The least common multiple of a group of numbers.


```python
=lcm(2, 5, 11) returns 110

```

#### __median(number1, number2, …)__ ####

The median (middle number) of a group of numbers


```python
=median(1, 2, 3, 4, 5, 6) returns 3.5

```

#### __logX(number, base)__ ####

The natural logarithm of a number with specified base. Number is the positive real number for which the logarithm is calculated. Related function: Power


```python
=logx(16, 2) returns 4

```

#### __power(number, power)__ ####

Raises a number to the given power. The function works like an exponent in a standard math equation.


```python
=power(10, 3) returns 1000

```

#### __sqrtpi(number)__ ####

The square root of (number * pi).


```python
=sqrtpi(3.1415) returns 3.142 (square root of pi*3.1415)

```

#### __sumsq(number1, number2, …)__ ####

The sum of the squares of the arguments.


```python
=sumsq(0, 1, 2, 3, 4, 5) returns 55

```

#### __randBetween(number1, number2)__ ####

A number between bottom and top, including bottom but not including top.


```python
=randBetween(10, 100) returns a random number in the range [10, 100]

```

#### __rand()__ ####

A number between 0 and 1, including 0 but not including 1.


```python
=rand() returns a random number in the range [0, 1)

```

#### __ceiling(number, [significance])__ ####

Rounds a number rounded up, away from zero, to the nearest multiple of significance.


```python
=ceiling(123.123, 0.01) returns 123.13 (123.123 rounded up to the nearest multiple of 0.01)

```

#### __floorNum(number, [significance])__ ####

Rounds a number down, toward zero, to the nearest multiple of significance.


```python
=floorNum(123.123, 0.01) returns 123.12 (123.123 rounded down to the nearest multiple of 0.01)

```

#### __truncate(number, [num digits])__ ####

A number truncated to the specified number of decimal places.


```python
=truncate(123.123, 2) returns 123.12

```

#### __average(number1, number2,...)__ ####

Returns the average (mean) of the arguments.


```python
=average(A2,A10..A12) returns the average of the numbers contained in cells A2, A10, A11, and A12

```

#### __int(number)__ ####

Rounds a number down to the nearest integer.


```python
=int(3.8) returns the value 3

```

#### __log(number)__ ####

Returns the base 10 logarithm of a number.


```python
=log(100) returns the base 10 logarithm of 100

```

#### __max(number1, number2,...)__ ####

Returns the largest number in the list of arguments.


```python
=max(C5,C7,C9) returns the largest of the numbers that are in cells C5, C7, and C9

```

#### __min(number1, number2,...)__ ####

Returns the smallest number in the list of arguments.


```python
=min(C5,C7,C9) returns the smallest of the numbers that are in cells C5, C7, and C9

```

#### __tan(number)__ ####

Returns the tangent of a given angle.


```python
=tan(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the tangent of the angle

```

#### __sum(number1, number2,...)__ ####

Returns the sum of all numbers in the list of arguments.


```python
=sum(A2,A10..A12) returns the sum of the numbers contained in cells A2, A10, A11, and A12

```

## Objects

### General


#### __Depth([optional parameters])__ ####

Returns the object's depth. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __Weight([optional parameters])__ ####

Returns the object's wight. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __ProjectedArea([optional parameters])__ ####

Returns the object's projected area. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __FootPrintArea([optional parameters])__ ####

Returns the object's footprint area. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __CrossSectionArea([optional parameters])__ ####

Returns the object's cross section area. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __SpecialArea([optional parameters])__ ####

Returns the object's special area typically defined by parameters. The optional parameters will return specific values for certain objects, and the available options will be listed separately.



#### __ObjectData('Class Description')__ ####

Returns the class description of the object's class.



#### __ObjectData('component', <value> [, <component index>])__ ####

When called on an object, the function returns the specified <value> of the object's component with the specified <component index>, or the core component if <component index> is missing. When called on a component, the function will return the specified <value> for that component. If the optional <component index> is added, the function will return the component value only for components that match the given index.

The following values are supported: "name", "function", "class", "class desc", "class description", "thickness", "lambda", "u-value", "net area", "net volume".

See the example for more details.


```python
Available options for <value>:
	- Name
	- Function
	- Class
	- Class Desc
	- Thickness
	- Lambda
	- U-Value
	- Net Area
	- Net Volume

Examples:
	# return component name
	ObjectData('component', 'Name')			# core component
	ObjectData('component', 'Name', 2)		# component with index = 2
	
	
	# return component Function value
	ObjectData('component', 'Function')		# core component
	ObjectData('component', 'Function', 2)	# component with index = 2
	
	
	# return component class
	ObjectData('component', 'Class')		# core component
	ObjectData('component', 'Class', 2)		# component with index = 2
	
	
	# return component class description
	ObjectData('component', 'Class Desc')			# core component
	ObjectData('component', 'Class Desc', 2)		# component with index = 2
	ObjectData('component', 'Class Description')	# core component
	ObjectData('component', 'Class Description', 2)	# component with index = 2
	
	
	# return component thickness
	ObjectData('component', 'Thickness')		# core component
	ObjectData('component', 'Thickness', 2)		# component with index = 2
	
	
	# return component lambda value
	ObjectData('component', 'Lambda')			# core component
	ObjectData('component', 'Lambda', 2)		# component with index = 2
	
	
	# return component U-value
	ObjectData('component', 'U-Value')			# core component
	ObjectData('component', 'U-Value', 2)		# component with index = 2
	
	
	# return component net area
	ObjectData('component', 'Net Area')			# core component
	ObjectData('component', 'Net Area', 2)		# component with index = 2
	
	
	# return component net volume
	ObjectData('component', 'Net Volume')		# core component
	ObjectData('component', 'Net Volume', 2)	# component with index = 2
	

```

#### __ObjectData('General Name')__ ####

Returns the object's or symbol's name and if it's a symbol with no name, returns the symbol definition resource name.


```python
Database header cell:
=ObjectData('General Name')        Returns the name for each object in the DB row.
                                If the object is a symbol, it will return the name of the symbol

Spreadsheet cell:
=ObjectData(SEL=TRUE, 'General Name')    Returns the name for the selected object
                                      If the object is a symbol, it will return the name of the symbol

```

#### __ObjectData(criteria, 'inventory part', part_univ_name, part_index)__ ####

Get inventory part name from inventory supported object.



#### __ObjectData(criteria, 'inventory part param', part_univ_name, part_index, param_index)__ ####

Get inventory part parameter value from inventory supported object.



#### __ObjectData(criteria, 'inventory part quantity', part_univ_name, part_index)__ ####

Get inventory part quantity from inventory supported object.



#### __ObjectData('Layer Description')__ ####

Returns the layer description of the object's layer.



#### __ObjectData('Object Variable', variable_index)__ ####

Returns the specified object variable from the object.



#### __ObjectData('Universal Value', format_name, field_name, [is format])__ ####

Returns the universal value of the specified field of record or format if the optional parameter is True. It will work with the parametric format when the format_name is empty. Returns N/A if the object doesn't have the record attached or the format doesn't exist.


```python
Database header cell:
=ObjectData('Universal Value', 'My Format-1', 'data')        Returns the 'data' field for the attached 'My Format-1' for each object in the DB row. Returns N/A if the format or the field is not available.
=ObjectData('Universal Value', 'My Format-1', 'data', True)  Returns the 'data' field for the attached 'My Format-1' for each object in the DB row. Returns N/A if the format or the field is not available.
=ObjectData('Universal Value', '', 'DoorHeight')            Returns the 'DoorHeight' field for each parametric in the DB row. Returns N/A if the field is not avaialble or the object is not a parametric.
=ObjectData('Universal Value', '', 'DoorHeight', True)      Returns the 'DoorHeight' field default value for each parametric in the DB row. Returns N/A if the field is not avaialble or the object is not a parametric.

Spreadsheet cell:
=ObjectData(t=wall, 'Universal Value', 'My Format-1', 'data')        Returns the 'data' field for the attached 'My Format-1' for the wall. Returns N/A if the format or the field is not available.
=ObjectData(t=wall, 'Universal Value', 'My Format-1', 'data', True)  Returns the 'data' field for the attached 'My Format-1' for the wall. Returns N/A if the format or the field is not available.
=ObjectData(PON='Door', 'Universal Value', '', 'DoorHeight')        Returns the 'DoorHeight' field for the parametric object Door. Returns N/A if the field is not avaialble or the object is not a parametric.
=ObjectData(PON='Door', 'Universal Value', '', 'DoorHeight', True)  Returns the 'DoorHeight' field default value the parametric object Door. Returns N/A if the field is not avaialble or the object is not a parametric.

```

#### __ObjectType()__ ####

Returns the object type ID.


```python
Database header cell:
=ObjectType returns the object type value for each object in the database

Spreadsheet cell:
=ObjectType(sel=true) returns the object type value of the selected object; for example, the object type value for a light is 81

```

#### __Width([optional parameters])__ ####

Returns the delta X (width) of objects. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Width returns the width (delta x) for each object in the database

Spreadsheet cell:
=Width(sel=true) returns the combined width (delta x value) of the selected object

```

#### __Height([optional parameters])__ ####

Returns the delta Y (height) of objects. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Height returns the height (delta y) for each object in the database

Spreadsheet cell:
=Height(sel=true) returns the combined height (delta y) value of the selected objects in the drawing

```

#### __Count([optional parameters])__ ####

Returns the number of objects. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Count returns the total number of objects for each row in the database

Spreadsheet cell:
=Count(s='simple sofa') returns the total number of symbol objects named “simple sofa” in the drawing

When used with the COUNT function, the SEL (selection status) criterion counts objects that are actually non-selectable, such as the individual items within a group. The VSEL (visible selection status) criterion counts only the visibly selected items, which is the same counting method used for the Object Info palette. For example, if you select and count a group that has 11 items in it, the SEL criterion returns a value of 12 (the group, plus the 11 items). The VSEL criterion returns a value of 1 (the group only).

```

#### __Angle()__ ####

Returns the angle of lines and walls, the span angle of arcs (in degrees), and the slope angle of slabs (in degrees).


```python
Database header cell:
=Angle returns the angle of each object in the database

Spreadsheet cell:
=Angle((t=arc)&(n='arc-1')) returns the sweep angle of the arc object named “arc-1” in the drawing

```

#### __IsFlipped()__ ####

Returns 1 if the object is flipped, otherwise it returns 0.


```python
Database header cell:
=IsFlipped returns the flip state for each object in the database

Spreadsheet cell:
=IsFlipped(PON='window') returns the flip state of the window object if it resolves to only one, otherwise returns the total number of window objects in the drawing that are flipped

```

#### __XCoordinate()__ ####

Returns the X coordinate of the insertion point for symbols, point plug-in objects, and loci. The returned value is relative to the user origin.


```python
Database header cell:
=XCoordinate returns the x coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __YCoordinate()__ ####

Returns the Y coordinate of the insertion point for symbols, point plug-in objects, and loci. The returned value is relative to the user origin.


```python
Database header cell:
=YCoordinate returns the y coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __ZCoordinate()__ ####

Returns the Z coordinate of the insertion point for symbols, point plug-in objects, and loci. The returned value is relative to the object's layer plane.


```python
Database header cell:
=ZCoordinate returns the z coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __Area()__ ####

Returns the area of 2D objects. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Area returns the area of each object in the database

Spreadsheet cell:
=Area(t=rect) returns the combined area of all rectangle objects in the drawing

```

#### __BotBound()__ ####

Returns the minimum Y coordinate of objects.


```python
Database header cell:
=BotBound returns the bottom 2D boundary of each object in the database

Spreadsheet cell:
=BotBound(t=locus) returns the bottom 2D boundary of the locus that has the lowest bottom 2D boundary value in the drawing

```

#### __TopBound()__ ####

Returns the maximum Y (top boundary) of the objects.


```python
Database header cell:
=TopBound returns the top 2D boundary for each object in the database

Spreadsheet cell:
=TopBound(sel=true) returns the top 2D boundary of the topmost selected object

```

#### __LeftBound()__ ####

Returns the left side minimum X (left boundary) of the objects.


```python
Database header cell:
=LeftBound returns the left 2D boundary for each object in the database

Spreadsheet cell:
=LeftBound(t=locus) returns the left 2D boundary of the leftmost locus in the drawing

```

#### __RightBound()__ ####

Returns the right side minimum X (right boundary) of the objects.


```python
Database header cell:
=RightBound returns the right 2D boundary for each object in the database

Spreadsheet cell:
=RightBound(t=rect) returns the right 2D boundary of the rightmost rectangle in the drawing

```

#### __Perim([optional parameters])__ ####

Returns the object's perimeter. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Perim returns the perimeter for each object in the database

Spreadsheet cell:
=Perim(sel=true) returns the total perimeter of all selected objects
```

#### __Length([optional parameters])__ ####

Returns the length of lines or walls. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Length returns the length for each object in the database

Spreadsheet cell:
=Length(t=line) returns the total length of all line objects in the drawing

```

#### __XCenter()__ ####

Returns the center of objects in the X direction.


```python
Database header cell:
=XCenter returns the x coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=XCenter(sel=true) returns the x coordinate value of the center of the 2D boundary of the selected object

```

#### __YCenter()__ ####

Returns the center of objects in the Y direction.


```python
Database header cell:
=YCenter returns the y coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=YCenter(sel=true) returns the y coordinate value of the center of the 2D boundary of the selected object

```

#### __ZCenter()__ ####

Returns the center of objects in the Z direction.


```python
Database header cell:
=ZCenter returns the z coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=ZCenter(sel=true) returns the z coordinate value of the center of the 2D boundary of the selected object

```

#### __SurfaceArea([optional parameters])__ ####

Returns the object's surface area. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=SurfaceArea returns the surface area for each object in the database

Spreadsheet cell:
=SurfaceArea(st=sphere) returns the total surface area of all sphere objects in the drawing

```

#### __Volume([optional parameters])__ ####

Returns the object's volume of objects. The optional parameters will return specific values for certain objects, and the available options will be listed separately.


```python
Database header cell:
=Volume returns the volume for each object in the database

Spreadsheet cell:
=Volume(t=xtrd) returns the total volume of all extrude objects in the drawing

```

#### __Image()__ ####

Returns an image of the object.


```python
Database header cell:
=Image returns the image for each object in the database

Spreadsheet cell:
=Image(s='cabinet') returns the image of the symbol named “Cabinet”

```

#### __ObjUValue()__ ####

Returns the U-Value of objects.


```python
Database header cell:
=ObjectUValue returns the U-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectUValue(n='wall-1') returns the U-value for the wall named “wall-1”
```

#### __ObjRValue()__ ####

Returns the R-Value of objects.


```python
Database header cell:
=ObjectRValue returns the R-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectRValue(n='wall-1') returns the R-value for the wall named “wall-1”

```

#### __ObjIncludeInEnergos()__ ####

Returns 1 if object will be included in Energos calculations, otherwise it returns 0.


```python
Database header cell:
=ObjIncludeInEnergos returns the Energos status for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjIncludeInEnergos(t=wall) returns the Energos status for all walls in the drawing

```

#### __PluginStyleName()__ ####

Returns the name of the plug-in style used by the object.


```python
Database header cell:
=PluginStyleName returns the plug-in style name for each object in the database

Spreadsheet cell:
=PluginStyleName(sel=true) returns the plug-in style name for all selected objects in the drawing

```

#### __Layer()__ ####

Returns the object's layer name.


```python
Database header cell:
=Layer returns the layer name of each object in the database

Spreadsheet cell:
=Layer(sel=true) returns the layer name of the selected objects in the drawing

```

#### __Class()__ ####

Returns the object's class name.


```python
Database header cell:
=Class returns the class name of each object in the database

Spreadsheet cell:
=Class(sel=true) returns the class name of the selected objects in the drawing

```

#### __ObjectTypeName()__ ####

Returns the object's type name.


```python
Database header cell:
=ObjectTypeName returns the type name for each object in the database

Spreadsheet cell:
=ObjectTypeName(sel=true) returns the type name of the selected objects in the drawing

```

#### __Name()__ ####

Returns the object's name.


```python
Database header cell:
=Name returns the name for each object in the database

Spreadsheet cell:
=Name(sel=true) returns the name of the selected objects in the drawing

```

#### __Story()__ ####

Returns the object's story name.


```python
Database header cell:
=Story returns the story name for each object in the database

Spreadsheet cell:
=Story(sel=true) returns the story name of the selected objects in the drawing

```

#### __ObjectTileFill()__ ####

Returns the object's tile fill name.


```python
Database header cell:
=TileFill returns the tile fill name for each object in the database

Spreadsheet cell:
=TileFill(sel=true) returns the tile fill name of the selected objects in the drawing

```

#### __ObjectHatchFill()__ ####

Returns the object's hatch fill name.


```python
Database header cell:
=HatchFill returns the hatch fill name for each object in the database

Spreadsheet cell:
=HatchFill(sel=true) returns the hatch fill name of the selected objects in the drawing

```

#### __ObjectGradientFill()__ ####

Returns the object's gradient fill name.


```python
Database header cell:
=GradientFill returns the gradient fill name for each object in the database

Spreadsheet cell:
=GradientFill(sel=true) returns the gradient fill name of the selected objects in the drawing

```

#### __ObjectTexture()__ ####

Returns the object's texture name.


```python
Database header cell:
=ObjectTexture returns the texture name of each object in the database

Spreadsheet cell:
=ObjectTexture(sel=true) returns the texture name of the selected objects in the drawing

```

#### __ObjectSketchStyle()__ ####

Returns the object's sketch style name.


```python
Database header cell:
=SketchStyle returns the sketch style name for each object in the database

Spreadsheet cell:
=SketchStyle(sel=true) returns the sketch style name of the selected objects in the drawing

```

#### __ObjectLineType()__ ####

Returns the object's line type name.


```python
Database header cell:
=LineType returns the line type name for each object in the database

Spreadsheet cell:
=LineType(sel=true) returns the line type name of the selected objects in the drawing

```

#### __ObjectImageFill()__ ####

Returns the object's image fill name.


```python
Database header cell:
=ImageFill returns the image fill name for each object in the database

Spreadsheet cell:
=ImageFill(sel=true) returns the image fill name of the selected objects in the drawing

```

#### __GetCOBieSource(worksheetName.columnName.country.version)__ ####

Returns data source of a COBie property for an object.


```python
=GETCOBIESOURCE ('space.floorname') returns the FloorName data source for objects whose COBie property is Space

```

#### __GetCOBieProperty(worksheetName.columnName.country.version)__ ####

Returns the value of a COBie property for an object.


```python
=GETCOBIEPROPERTY ('space.floorname') returns the FloorName value for objects whose COBie property is Space

```

#### __SymbolName()__ ####

Returns the symbol name.


```python
Database header cell:
=SymbolName returns the name for each symbol instance in the database

Spreadsheet cell:
=SymbolName(sel=true) returns the symbol name of the selected symbol instances in the drawing

```

#### __DataTagField(fieldname)__ ####

Returns the value of the specified field in the data tag object. Fieldname is the name of the field in the data tag layout.


```python
Database header cell:
=DataTagField('Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for each data tag in the database.

Spreadsheet cell:
=DataTagField(sel=true, 'Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for the selected data tag in the drawing.

```

#### __ImageByViewport(viewportName)__ ####

Returns an image of the object with the specified viewport's color scheme(s) applied.


```python
Database header cell:
=Imagebyviewport('Plan A') applies the data visualizations from the viewport named “Plan A” to each image in the database 

Spreadsheet cell:
=Imagebyviewport('Space Allocation') applies the data visualization from the viewport named “Space Allocation” to the image in the cell

```

#### __ImageByDataVis(dataVisName)__ ####

Returns an image of the object with the specified data visualizations's color scheme applied.


```python
Database header cell:
=Imagebydatavis('truss by type') applies the “truss by type” data visualization to each image in the database rows

Spreadsheet cell:
=Imagebydatavis('offices') applies the data visualization named “offices” to the image in the cell

```

#### __XRotation()__ ####

Returns the object's rotation angle (in degrees) around the X-axis.



#### __YRotation()__ ####

Returns the object's rotation angle (in degrees) around the Y-axis.



#### __ZRotation()__ ####

Returns the object's rotation angle (in degrees) around the Z-axis.



#### __PartTypeName()__ ####

Returns the part type name of the subpart object. Returns the object type name if the object is not a subpart.


```python
Database header cell:
=PartTypeName returns the part type name for each subpart object in the database. if the database object is not a subpart, the object type name is returned


```

#### __FillForeColor()__ ####

Returns the object's fill foreground color name.


```python
Database header cell:
=FillForeColor returns the name of the fill foreground color for each object in the database

Spreadsheet cell:
=FillForeColor(t=rect) returns the name of the fill foreground color of the rectangle object

```

#### __FillBackColor()__ ####

Returns the object's fill background color name.


```python
Database header cell:
=FillBackColor returns the name of the fill background color for each object in the database

Spreadsheet cell:
=FillBackColor(t=rect) returns the name of the fill background color of the rectangle object

```

#### __PenForeColor()__ ####

Returns the object's pen foreground color name.


```python
Database header cell:
=PenForeColor returns the name of the pen foreground color for each object in the database

Spreadsheet cell:
=PenForeColor(t=rect) returns the name of the pen foreground color of the rectangle object

```

#### __PenBackColor()__ ####

Returns the object's pen background color name.


```python
Database header cell:
=PenBackColor returns the name of the pen background color for each object in the database

Spreadsheet cell:
=PenBackColor(t=rect) returns the name of the pen background color of the rectangle object

```

#### __IsFilled()__ ####

Returns 1 if the object has any fill attribute, otherwise returns 0.


```python
Database header cell:
=IsFilled returns the attribute fill state (1 if filled, otherwise 0) for each object in the database



Spreadsheet cell:
=IsFilled(T=WALL) returns the attribute fill state of the wall object if the criteria resolves to one object, otherwise returns the total number of walls in the drawing that are filled


```

#### __ViewportStyleName()__ ####

Returns the name of the viewport style used by the object.


```python
Database header cell:
=ViewportStyleName returns the viewport style name for each viewport object in the database

Spreadsheet cell:
=ViewportStyleName(n='viewport-1') returns the viewport style name for the object named “viewport-1”

```

### Legacy


#### __ComponentArea( index)__ ####

Returns the area of one side of the specified component,
minus any holes in the 3D object.


```python
Database header cell:
=ComponentArea(2) returns the combined area of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentArea(t=wall,1) returns the combined area of the first components for all walls in the drawing

```

#### __ComponentVolume(index)__ ####

Returns the total 3D volume of the specified component,
minus any holes in the 3D object.


```python
Database header cell:
=ComponentVolume(2) returns the combined volume of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentVolume(t=wall,1) returns the combined volume of the first components for all walls in the drawing

```

#### __ComponentName(index)__ ####

Returns the name of the specified component.


```python
Database header cell:
=ComponentName(2) returns the name of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentName(t=wall,1) returns the name of the first component for all walls in the drawing

```

#### __GetIFCProperty(instanceName.propertyName)__ ####

Returns the value of the property field of the given instance or preset.


```python
=GETIFCPROPERTY ('ifcfurnishingelement.name') returns the Name value for IFC objects whose IFC entity is IfcFurnishingElement 

```

#### __ComponentLambda(index)__ ####

Returns the lambda of the specified component.


```python
Database header cell:
=ComponentLambda(2) returns the Lambda value of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentLambda(t=wall,1) returns the Lambda value of the first component for all walls in the drawing

```

#### __ComponentUValue(index)__ ####

Returns the U-Value of the specified component.


```python
Database header cell:
=ComponentUValue(2) returns the combined U-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentUValue(t=wall,1) returns the combined U-values of the first components for all walls in the drawing

```

#### __ComponentRValue(index)__ ####

Returns the R-Value of the specified component.


```python
Database header cell:
=ComponentRValue(2) returns the combined R-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentRValue(t=wall,1) returns the combined R-values of the first components for all walls in the drawing

```

#### __ComponentThickness(index)__ ####

Returns the thickness of the specified component.


```python
Database header cell:
=ComponentThickness(2) returns the combined thickness of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentThickness(t=wall,1) returns the combined thickness of the first components for all walls in the drawing

```

#### __CompAreaByClass(class)__ ####

The area of one side of the specified wall, slab, or roof component, minus any holes.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompAreaByClass('Class-1') returns the combined area of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByClass(t=wall,'Class-1') returns the combined area of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __CompLambdaByClass(class)__ ####

The Lambda value of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the lambda value of the first matching component will be returned.


```python
Database header cell:
=CompLambdaByClass('Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByClass(t=wall,'Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __CompNameByClass(class)__ ####

The name of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the first component name will be returned.


```python
Database header cell:
=CompNameByClass('Class-1') returns the name of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByClass(t=wall,'Class-1') returns the name of the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __CompRValueByClass(class)__ ####

The R-Value of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompRValueByClass('Class-1') returns the combined R-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByClass(t=wall,'Class-1') returns the combined R-values of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __CompThicknessByClass(class)__ ####

The thickness of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompThicknessByClass('Class-1') returns the combined thickness of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByClass(t=wall,'Class-1') returns the combined thickness of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __CompUValueByClass(class)__ ####

The U-Value of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompUValueByClass('Class-1') returns the combined U-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByClass(t=wall,'Class-1') returns the combined U-values of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __CompVolumeByClass(class)__ ####

The volume of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompVolumeByClass('Class-1') returns the combined volume of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByClass(t=wall,'Class-1') returns the combined volume of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __CompAreaByName(name)__ ####

The area of one side of the specified wall, slab, or roof component, minus any holes. Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompAreaByName('Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByName(t=wall,'Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __CompLambdaByName(name)__ ####

The Lambda value of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the lambda value of the first matching component will be returned.


```python
Database header cell:
=CompLambdaByName('Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByName(t=wall,'Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for all walls in the drawing

```

#### __CompClassByName(name)__ ####

The class of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the specified name the first component class will be returned.


```python
Database header cell:
=CompClassByName('Brick Veneer') returns the class of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByName(t=wall,'Brick Veneer') returns the class of the first component with the name “Brick Veneer” for all walls in the drawing

```

#### __CompRValuesByName(name)__ ####

The R-Value of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompRValueByName('Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByName(t=wall,'Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __CompThicknessByName(name)__ ####

The thickness of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompThicknessByName('Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByName(t=wall,'Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __CompUValueByName(name)__ ####

The U-Value of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompUValueByName('Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByName(t=wall,'Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __CompVolumeByName( name)__ ####

The volume of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompVolumeByName('Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByName(t=wall,'Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __CompMatByClass(class)__ ####

The material of the specified wall, slab, or roof component.  Class is a string that specifies the component's class. If multiple components use the specified class the values will be summed.


```python
Database header cell:
=CompMatByClass('Class-1') returns the materials used by the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByClass(t=wall,'Class-1') returns the material used by the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __CompMatByName(name)__ ####

The material of the specified wall, slab, or roof component.  Name is a string that specifies the component's name. If multiple components use the same name the values will be summed.


```python
Database header cell:
=CompMatByName('Siding') returns the materials used by the first component with the name “Siding” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByName(t=wall,'Siding') returns the material used by the first component with the name “Siding” for all walls in the drawing

```

#### __CompAreaByMat(material)__ ####

The area of one side of the specified wall, slab, or roof component, minus any holes.  Material is a string that specifies the component's material. If multiple components use the specified material the values will be summed.


```python
Database header cell:
=CompAreaByMat('Mortar MT') returns the combined area of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByMat(t=wall, 'Mortar MT') returns the combined area of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __CompClassByMat(material)__ ####

The class of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the first component class will be returned.


```python
Database header cell:
=CompClassByMat('Mortar MT') returns the class of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByMat(t=wall, 'Mortar MT') returns the class of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __CompLambdaByMat(material)__ ####

The Lambda value of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the lambda value of the first matching component will be returned.


```python
Database header cell:
=CompLambdaByMat('Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByMat(t=wall,'Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __CompNameByMat(material)__ ####

The name of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the first component name will be returned.


```python
Database header cell:
=CompNameByMat('Mortar MT') returns the name of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByMat(t=wall,'Mortar MT') returns the name of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __CompRValueByMat(material)__ ####

The R-Value of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the values will be summed.


```python
Database header cell:
=CompRValueByMat('Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByMat(t=wall,'Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __CompThicknessByMat(material)__ ####

The thickness of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the values will be summed.


```python
Database header cell:
=CompThicknessByMat('Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByMat(t=wall,'Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __CompUValueByMat(material)__ ####

The U-Value of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the values will be summed.


```python
Database header cell:
=CompUValueByMat('Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByMat(t=wall,'Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __CompVolumeByMat(material)__ ####

The volume of the specified wall, slab, or roof component.  Material is a string that specifies the component's material. If multiple components use the specified material the values will be summed.


```python
Database header cell:
=CompVolumeByMat('Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByMat(t=wall,'Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for all walls in the drawing

```

### Material


#### __MaterialName()__ ####

Returns the object's material.


```python
Database header cell:
=MaterialName returns the names of materials in objects for each row in the database

Spreadsheet cell:
=MaterialName(t=SOLIDCSG) returns the names of materials in generic solids in the drawing

```

#### __MaterialCount()__ ####

Returns the object's number of materials.


```python
Database header cell:
=MaterialCount returns the total number of materials in objects for each row in the database

Spreadsheet cell:
=MaterialCount(t=SOLIDCSG) returns the total number of materials in generic solids in the drawing

```

#### __MaterialTexture()__ ####

Returns the name of the object's material's texture assignment.


```python
Database header cell:
=MaterialTexture returns the texture of the material assigned to objects for each row in the database

Spreadsheet cell:
=MaterialTexture(t=SOLIDCSG) returns the texture of the material assigned to the generic solid in the drawing

```

#### __MatPropertyByName(materialName, propertyName)__ ####

Returns the value of the specified property for the specified material.


```python
Spreadsheet cell:
=MatPropertyByName('Mortar MT','MaterialFinish') returns the material finish property for the material “Mortar MT”

```

#### __MaterialIsSimple()__ ####

Returns true if the object's material is a simple material.


```python
Database header cell:
=MaterialIsSimple returns TRUE if the material of the object referenced by the database row is a simple material.

Spreadsheet cell:
=MaterialIsSimple(t=SOLIDCSG) returns TRUE if the material of the generic solid in the drawing is a simple material.

```

#### __MaterialPartName(materialName)__ ####

Returns the name of the material-bearing geometry that uses the specified material in the object.


```python
Database header cell:
=MaterialPartName('Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for each row in the database

Spreadsheet cell:
=MaterialPartName(t=wall, 'Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for walls in the drawing

```

#### __MaterialSurfaceArea()__ ####

Returns the surface area of the object's specified material assignment.


```python
Database header cell:
=MaterialSurfaceArea('Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialSurfaceArea(t=wall,'Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all walls in the drawing

```

#### __MaterialVolume()__ ####

Returns the volume of the object's specified material assignment.


```python
Database header cell:
=MaterialVolume('Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialVolume(t=wall,'Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all walls in the drawing

```

#### __MaterialPercent(materialName)__ ####

Returns percentage of the object's specified material.


```python
Database header cell:
=MaterialPercent('Mortar MT') returns the percentage of the material “Mortar MT” in all objects for each row in the database

Spreadsheet cell:
=MaterialPercent(t=wall,'Mortar MT') returns the percentage of the material “Mortar MT” for all walls in the drawing

```

#### __ComponentMaterial(index)__ ####

Returns the material of the specified component.


```python
Database header cell:
=ComponentMaterial(2) returns the material used by the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentMaterial(t=wall,1) returns the material used by the first component for all walls in the drawing

```

#### __MaterialProperty(propertyName)__ ####

Returns the value of the specified property for the material resource.


```python
Database header cell:
=MaterialProperty('MaterialFinish') returns the value of the material property "MaterialCategory" for each material resource in the database

Spreadsheet cell:
=MaterialProperty((t=material) & (n='material-1'), 'MaterialCategory') returns the value of the material property "MaterialCategory" for the material resource named "material-1"

Available property names:

- General info fields
	'MaterialDescription'
	'MaterialKeynote'
	'MaterialMark'

- Physical values
	'MaterialUsesAcousticImpedance' and 'MaterialAcousticImpedance'
	'MaterialUsesAlbedo' and 'MaterialAlbedo'
	'MaterialUsesDensity' and 'MaterialDensity'
	'MaterialUsesEmbodiedCarbon' and 'MaterialEmbodiedCarbon'
	'MaterialUsesEmissivity' and 'MaterialEmissivity'
	'MaterialUsesLambda' and 'MaterialLambda'
	'MaterialUsesModulusOfElasticity' and 'MaterialModulusOfElasticity'
	'MaterialUsesSlipResistance' and 'MaterialSlipResistance'
	'MaterialUsesSoundVelocity' and 'MaterialSoundVelocity'
	'MaterialUsesSpecificGravity' and 'MaterialSpecificGravity'
	'MaterialUsesSpecificHeat' and 'MaterialSpecificHeat'
	'MaterialUsesTensileStrength' and 'MaterialTensileStrength'
	'MaterialUsesThermalExpansionCoefficient' and 'MaterialThermalExpansionCoefficient'
	'MaterialUsesYieldStrength' and 'MaterialYieldStrength'

Construction info
	'MaterialCategory'
	'MaterialClassificationDescription'
	'MaterialCost'
	'MaterialFinish'
	'MaterialIsSurfaceAreaMeasure'
	'MaterialIsVolumetric'
	'MaterialManufacturer'
	'MaterialProductDescription'
	'MaterialProductModel'
	'MaterialProductName'
	'MaterialProductURL'
	'MaterialReferenceID'
	'MaterialSource'
	'MaterialStandard'

```

## Specialized for Adapter


#### __ObjectData('eval adapter plug device', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the adapter's plug device.



#### __ObjectData('eval adapter plug socket', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the adapter's plug socket.



## Specialized for Circuit


#### __ObjectData('eval circuit destination adapter', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's destination adapter.



#### __ObjectData('eval circuit destination device', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's destination device.



#### __ObjectData('eval circuit destination socket', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's destination socket.



#### __ObjectData('eval circuit drop points', ['<RecordName>'], ['<FieldName>'], ['ignoreEnds'])__ ####

List any intermediate drop point ID’s, parameter values or attached record fields through which a circuit passes. Add ignoreEnds to not list the drop points, located at the begging or at the end of the route. The drawing needs to be analyzed.



#### __ObjectData('eval circuit route', ['<RecordName>'], ['<FieldName>'])__ ####

Get path IDs, parameter values or attached record fields from the circuit's used cable paths. The drawing needs to be analyzed.



#### __ObjectData('eval circuit source adapter', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's source adapter.



#### __ObjectData('eval circuit source device', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's source device.



#### __ObjectData('eval circuit source socket', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit's source socket.



## Specialized for Curtain Wall


#### __CurtWallFrameLength(classname)__ ####

Returns the length of curtain wall frames in class 'classname'.


```python
Database header cell:
=CurtWallFrameLength('') returns the combined length of the curtain wall frames for each curtain wall in the database

Spreadsheet cell:
=CurtWallFrameLength(t=wall, '') returns the combined length of the curtain wall frames for all curtain walls in the drawing

```

#### __CurtWallPnlAreaGross(classname)__ ####

Returns the gross area of the curtain wall panels in class 'classname'.


```python
Database header cell:
=CurtWallPnlAreaGross('') returns the combined gross area of the curtain wall panels for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaGross(t=wall, '') returns the combined gross area of the curtain wall panels for all curtain walls in the drawing

```

#### __CurtWallPnlAreaNet(classname)__ ####

Returns the net area of the curtain walls panels in class 'classname'.


```python
Database header cell:
=CurtWallPnlAreaNet ('Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaNet(t=wall, 'Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for all curtain walls in the drawing

```

## Specialized for Device


#### __ObjectData('eval equipment item', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the device's corresponding equipment item.



## Specialized for Door


#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



#### __Volume(criteria, 'door jamb')__ ####

Returns the volume the jamb.


```python
Database header cell:
=VOLUME('door jamb')     Returns the volume the jamb.

Spreadsheet cell:
=VOLUME(SEL, 'door jamb')    Returns the volume the jamb.

```

#### __Volume(criteria, 'door sashes')__ ####

Returns the total volume all sashes (including sidelight and transom sashes).


```python
Database header cell:
=VOLUME('door sashes')     Returns the total volume all sashes (including sidelight and transom sashes).

Spreadsheet cell:
=VOLUME(SEL, 'door sashes')    Returns the total volume all sashes (including sidelight and transom sashes).

```

#### __Volume(criteria, 'glazing all')__ ####

Returns the total volume of all glazing.


```python
Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.

```

#### __Volume(criteria, 'glazing for leaves')__ ####

Returns the volume of glazing for all leaves (including vision panels).


```python
Database header cell:
=VOLUME('glazing for leaves')     Returns the volume of glazing for all leaves (including vision panels).

Spreadsheet cell:
=VOLUME(SEL, 'glazing for leaves')    Returns the volume of glazing for all leaves (including vision panels).

```

#### __Volume(criteria, 'glazing for sidelights')__ ####

Returns the volume of glazing for all sidelights.


```python
Database header cell:
=VOLUME('glazing for sidelights')     Returns the volume of glazing for all sidelights.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sidelights')    Returns the volume of glazing for all sidelights.

```

#### __Volume(criteria, 'glazing for transom')__ ####

Returns the volume of glazing for the transom.


```python
Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.

```

#### __Volume(criteria, 'leaf panels')__ ####

Returns the total volume of the leaf panels.


```python
Database header cell:
=VOLUME('leaf panels')     Returns the total volume of the leaf panels.

Spreadsheet cell:
=VOLUME(SEL, 'leaf panels')    Returns the total volume of the leaf panels.

```

#### __Volume(criteria, 'leaf stiles and rails')__ ####

Returns the total volume of the leaf rails, and stiles.


```python
Database header cell:
=VOLUME('leaf stiles and rails')     Returns the total volume of the leaf rails and stiles.

Spreadsheet cell:
=VOLUME(SEL, 'leaf stiles and rails')    Returns the total volume of the leaf rails and stiles.

```

## Specialized for Door CW


#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



## Specialized for Fence


#### __Depth('Gravel Board')__ ####

The function is applicable to Fence object and Gravel Board subpart.
Returns the depth of the gravel board, if active.



#### __Depth('Horizontal Boards')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the profile thickness. If the fence has different Infill Type, returns N/A.



#### __Depth('Panels')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the profile depth. If the fence has different Infill Type, returns N/A.



#### __Depth('Rail', <Index>)__ ####

The function is applicable to:

Fence object: returns the depth of the selected rail.

Rail subpart: returns the depth of the rail. If the rail doesn't correspond to the selected index, returns N/A.



#### __Depth('Rails')__ ####

The function is applicable to rail subparts: returns the depth of the rail.



#### __Depth('Vertical Boards')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the profile width. If the fence has different Infill Type, returns N/A.



#### __FootPrintArea('Corner Footers')__ ####

The function is applicable to:

Fence object: returns the total footprint area of all footers.

Footer subpart: returns the footprint area of the footer. If the footer is not corner, returns N/A.



#### __FootPrintArea('Footers')__ ####

The function is applicable to:

Fence object: returns the total footprint area of all footers.

Footer subpart: returns the footprint area of the footer.



#### __FootPrintArea('Gate Footers')__ ####

The function is applicable to:

Fence object: returns the total footprint area of all footers.

Footer subpart: returns the footprint area of the footer. If the footer is not gate, returns N/A.



#### __FootPrintArea('Running Footers')__ ####

The function is applicable to:

Fence object: returns the total footprint area of all footers.

Footer subpart: returns the footprint area of the footer. If the footer is not running, returns N/A.



#### __ObjectData('Footer Type')__ ####

The function is applicable to Footer subpart only.

Returns the type of the footer. It can be 'Corner Footer', 'Running Footer' or 'Gate Footer'.



#### __ObjectData('Infill Type')__ ####

The function is applicable to Infill subpart only.

Returns the type of the infill. It can be 'Preconstructed Panel', 'Vertical Board' or 'Horizontal Board'.



#### __ObjectData('Name')__ ####

The function is applicable to all Fence subparts: Post, Gate, Infill, and Rail.

Returns the name of the used symbol definition.



#### __ObjectData('Post Type')__ ####

The function is applicable to Post subpart only.

Returns the type of the post. It can be 'Corner Post', 'Running Post' or 'Gate Post'.



#### __ObjectData('Rail Index')__ ####

The function is applicable to Rail subpart only.

Returns the index of the rail type, starting from index 1.



#### __Width('Horizontal Boards')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the profile width. If the fence has different Infill Type, returns N/A.



#### __Width('Vertical Boards')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the profile thickness. If the fence has different Infill Type, returns N/A.



#### __Height('Corner Footers')__ ####

The function is applicable to:

Fence object: returns the sum of all corner footers.

Footer subpart: returns the height of the footer, which is equal to the (depth below grade + drainage layer) of the related footer type. If the footer type is not corner, returns N/A.



#### __Height('Corner Posts')__ ####

The function is identical to Length('Corner Posts').



#### __Height('Fabric')__ ####

The function is applicable to:

Fence object: returns the height of the fabric subpart ( if there are more than 1, returns the height of the first ).

Rail subpart: returns height only if the rail is of type fabric.



#### __Height('Footers')__ ####

The function is applicable to:

Fence object: returns the sum of all footers.

Footer subpart: returns the height of the footer, which is equal to the (depth below grade + drainage layer) of the related footer type.



#### __Height('Gate Footers')__ ####

The function is applicable to:

Fence object: returns the sum of all gate footers.

Footer subpart: returns the height of the footer, which is equal to the (depth below grade + drainage layer) of the related footer. If the footer type is not gate, returns N/A.



#### __Height('Gate Posts')__ ####

The function is identical to Length('Gate Posts').



#### __Height('Gates')__ ####

The function is applicable to Gate subpart only. Returns the height of the gate.



#### __Height('Gravel Board')__ ####

The function is applicable to Fence object and Gravel Board subpart.
Returns the height of the gravel board, if active.



#### __Height('Panels')__ ####

The function is applicable to Fence object and Infill subpart.
Returns the panel height. If the fence has different Infill type, returns N/A.



#### __Height('Posts')__ ####

The function is identical to Length('Posts').



#### __Height('Rail', <Index>)__ ####

The function is applicable to:

Fence object: returns the height of the <Index> rail.

Rail subpart: returns the height of the rail. If the rail doesn't correspond to the selected index, returns N/A.



#### __Height('Rails')__ ####

The function is applicable to:

Rail subpart: returns the height of the rail.



#### __Height('Running Footers')__ ####

The function is applicable to:

Fence object: returns the sum of all running footers.

Footer subpart: returns the height of the footer, which is equal to the (depth below grade + drainage layer) of the related footer type. If the footer type is not running, returns N/A.



#### __Height('Running Posts')__ ####

The function is identical to Length('Running Posts').



#### __Height('Top Line Above Grade')__ ####

The function is applicable to the Fence object.

If the 'Infill Type' is 'Rails Only': returns the highest top elevation of all rails.

Otherwise: returns the 'Top Line Above Grade' field.



#### __Count('Corner Footers')__ ####

The function is applicable to:

Fence object: returns the count of all corner footers.

Footer subpart: returns 1 for any corner footer. If the footer is not corner, returns N/A.



#### __Count('Corner Posts')__ ####

The function is applicable to:

Fence object: returns the total count of corner posts.

Post subpart: returns 1 for any corner post.



#### __Count('Fabric')__ ####

The function is applicable to:

Fence object: returns the count of all rails that are treated as fabric.

Rail subpart: returns 1 if the rail is fabric.



#### __Count('Footers')__ ####

The function is applicable to:

Fence object: returns the count of all footers.

Footer subpart: returns 1 for any type of footer.



#### __Count('Gate Footers')__ ####

The function is applicable to:

Fence object: returns the count of all gate footers.

Footer subpart: returns 1 for any gate footer. If footer is not gate, returns N/A.



#### __Count('Gate Posts')__ ####

The function is applicable to:

Fence object: returns the total count of gate posts.

Post subpart: returns 1 for any gate post.



#### __Count('Gates')__ ####

The function is applicable to:

Fence object: returns the number of gates in the fence object.

Gate subpart: returns 1 for any gate.



#### __Count('Gravel Board')__ ####

The function is applicable to:

Fence object: returns number of gravel boards if the option is active.

Gravel Board subpart: returns 1.



#### __Count('Horizontal Boards')__ ####

The function is applicable to:

Fence object: returns the number of horizontal boards in the object.

Infill subpart: returns 1 for any horizontal board infill. If the fence has different Infill Type, returns N/A.



#### __Count('Panels')__ ####

The function is applicable to:

Fence object: returns the number of panels in the object.

Infill subpart: returns 1 for any panel infill. If the fence has different Infill Type, returns N/A.



#### __Count('Posts')__ ####

The function is applicable to:

Fence object: returns the total count of posts.

Post subpart: returns 1 for any type of post.



#### __Count('Rail', <Index>)__ ####

The function is applicable to:

Fence object: returns 1 if <Index> is valid one or 0 if it is out of bounds.

Rail subpart: returns 1 if the rail corresponds to the selected index. Otherwise, returns N/A.



#### __Count('Rails')__ ####

The function is applicable to:

Fence object: returns the count of all rail settings.

Rail subpart: returns 1 for any rail.



#### __Count('Running Footers')__ ####

The function is applicable to:

Fence object: returns the count of all running footers.

Footer subpart: returns 1 for any running footer. If the footer is not running, returns N/A.



#### __Count('Running Posts')__ ####

The function is applicable to:

Fence object: returns the total count of running posts.

Post subpart: returns 1 for any running post.



#### __Count('Vertical Boards')__ ####

The function is applicable to:

Fence object: returns the number of vertical boards in the object.

Infill subpart: returns 1 for any vertical board infill. If the fence has different Infill Type, returns N/A.



#### __Length('2D')__ ####

The function is applicable to the Fence object.

Returns the 2D length of the offset object path.



#### __Length('3D')__ ####

The function is applicable to the Fence object.

Returns the 3D length of the offset object path.



#### __Length('Corner Posts')__ ####

The function is applicable to:

Fence object: returns the sum of all post length.

Post subpart: returns the length of the post, counted from top to bottom of depth below grade. If the post is not corner, returns N/A.



#### __Length('Fabric')__ ####

The function is applicable to:

Fence object: return the total length of all fabric rails with equal index. If there are multiple fabric rails, selects the first one.

Rail subpart: returns the length of the rail. If the rail isn't fabric, returns N/A.



#### __Length('Gate Posts')__ ####

The function is applicable to:

Fence object: returns the sum of all post length.

Post subpart: returns the length of the post, counted from top to bottom of depth below grade. If the post is not gate, returns N/A.



#### __Length('Gates')__ ####

The function is applicable to:

Fence object: returns the sum of all gate lengths.

Gate subpart: return the length along the fence line of this Gate.



#### __Length('Gravel Board')__ ####

The function is applicable to:

 returns the sum length of all gravel boards.

Gravel Board subpart: returns the length of the gravel board.



#### __Length('Horizontal Boards')__ ####

The function is applicable to:

Fence object: returns the sum of all horizontal board lengths.

Infill subpart: returns the length of the horizontal board. It is defined as the distance/arc length from the start post to the end (depending on the object path). If the fence has different Infill Type, returns N/A.



#### __Length('Panels')__ ####

The function is applicable to:

Fence object: returns the sum of all panel lengths.

Infill subpart: returns the length of the panel. If the fence has different Infill Type, returns N/A.



#### __Length('Posts')__ ####

The function is applicable to:

Fence object: returns the sum of all post length.

Post subpart: returns the length of the post, counted from top to bottom of depth below grade.



#### __Length('Rail', <Index>)__ ####

The function is applicable to:

Fence object: returns the total length of all rails with index <Index>.

Rail subpart: return the length of the rail. If the rail doesn't correspond to the selected index, returns N/A.



#### __Length('Rails')__ ####

The function is applicable to:

Fence object: returns the total length of all rails.

Rail subpart: returns the length of the rail.



#### __Length('Running Posts')__ ####

The function is applicable to:

Fence object: returns the sum of all post length.

Post subpart: returns the length of the post, counted from top to bottom of depth below grade. If the post is not running, returns N/A.



#### __Length('Vertical Boards')__ ####

The function is applicable to:

Fence object: returns the sum of all vertical boards lengths.

Infill subpart: returns the length of the vertical board. It is defined from the bottom position of the board to top. If the fence has different Infill Type, returns N/A.



#### __SurfaceArea('Fabric')__ ####

The function is applicable to:

Fence object: returns the total surface area of all fabric rails.

Rail subpart: returns the surface area of the rail if it is fabric. Otherwise, returns N/A.



#### __SurfaceArea('Panels')__ ####

The function is applicable to:

Fence object: returns the sum of all panel surface areas.

Infill subpart: returns the panel surface area. If the fence has different Infill Type, returns N/A.



#### __Volume()__ ####

The function is applicable to the Fence object.

Returns the total volume of the fence object.



#### __Volume('Corner Footers')__ ####

The function is applicable to:

Fence object: returns the total volume of all corner footers.

Footer subpart: returns the volume of the footer. If the footer is not corner, returns N/A.



#### __Volume('Corner Posts')__ ####

The function is applicable to:

Fence object: returns the volume of all corner posts.

Post subpart: returns the volume of the corner post. If the post is not corner, returns N/A.



#### __Volume('Footers')__ ####

The function is applicable to:

Fence object: returns the total volume of all footers.

Footer subpart: returns the volume of the footer.



#### __Volume('Gate Footers')__ ####

The function is applicable to:

Fence object: returns the total volume of all gate footers.

Footer subpart: returns the volume of the footer. If the gate is not gate, returns N/A.



#### __Volume('Gate Posts')__ ####

The function is applicable to:

Fence object: returns the volume of all gate posts.

Post subpart: returns the volume of the gate post. If the post is not gate, returns N/A.



#### __Volume('Gates')__ ####

The function is applicable to:

Fence object: returns the total volume of all gates.

Gate subpart: returns the volume of the gate.



#### __Volume('Gravel Board')__ ####

The function is applicable to:

 returns the total volume of all gravel boards.

Gravel Board subpart: returns the volume of the gravel board.



#### __Volume('Horizontal Boards')__ ####

The function is applicable to:

Fence object: returns the total volume of the horizontal boards.

Infill subpart: returns the horizontal board volume. If the fence has different Infill Type, returns N/A.



#### __Volume('Panels')__ ####

The function is applicable to:

Fence object: returns the total volume of the panels.

Infill subpart: returns the panel volume. If the fence has different Infill Type, returns N/A.



#### __Volume('Posts')__ ####

The function is applicable to:

Fence object: returns the volume of all posts.

Post subpart: returns the volume of the post.



#### __Volume('Rail', <Index>)__ ####

The function is applicable to:

Fence object: returns the total volume of all rails from the selected index.

Rail subpart: returns the volume of the rail. If the rail doesn't correspond to the selected index, returns N/A.



#### __Volume('Rails')__ ####

The function is applicable to:

Fence object: returns the total volume of all rails.

Rail subpart: returns the volume of the rail. Function is defined only if Depth and Height return nonzero result.



#### __Volume('Running Footers')__ ####

The function is applicable to:

Fence object: returns the total volume of all running footers.

Footer subpart: returns the volume of the footer. If the footer is not running, returns N/A.



#### __Volume('Running Posts')__ ####

The function is applicable to:

Fence object: returns the volume of all running posts.

Post subpart: returns the volume of the running post. If the post is not running, returns N/A.



#### __Volume('Vertical Boards')__ ####

The function is applicable to:

Fence object: returns the total volume of the vertical boards.

Infill subpart: returns the vertical board volume. If the fence has different Infill Type, returns N/A.



## Specialized for Hardscape


#### __Depth()__ ####

Calculate the depth of the Landscape Area, Hardscape, or Site Model and their components.



#### __ProjectedArea()__ ####

Calculate the projected area of the Landscape Area, Hardscape, or Site Model and their components.



#### __ObjectData('component name')__ ####

Return the name of the component subpart for Landscape Area, Hardscape, and Site Model.



#### __Area()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __SurfaceArea()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __Volume()__ ####

Calculate the volume of the Landscape Area, Hardscape, or Site Model and their components.



## Specialized for Hedgerow


#### __ObjectData('percentage')__ ####

Return the percentage value of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('Plant Record', <field>)__ ####

Provides access to the Plant Record data of the Landscape Area Plant subparts for edit if the style allows.



#### __ObjectData('rate')__ ####

Return the rate value value of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('rate unit')__ ####

Return the rate unit string of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('rate with unit')__ ####

Return the rate value and unit of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



## Specialized for Landscape Area


#### __Depth()__ ####

Calculate the depth of the Landscape Area, Hardscape, or Site Model and their components.



#### __ProjectedArea()__ ####

Calculate the projected area of the Landscape Area, Hardscape, or Site Model and their components.



#### __ObjectData('component name')__ ####

Return the name of the component subpart for Landscape Area, Hardscape, and Site Model.



#### __ObjectData('divider')__ ####

Return the divider string or empty of this divider from a Landscape Area. This must be used on a database row listing the dividers/plants of Landscape Areas.



#### __ObjectData('Landscape Area', <field>)__ ####

Provides access to the Landscape Area data field for edit if the style allows.



#### __ObjectData('percentage')__ ####

Return the percentage value of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('Plant Record', <field>)__ ####

Provides access to the Plant Record data of the Landscape Area Plant subparts for edit if the style allows.



#### __ObjectData('rate')__ ####

Return the rate value value of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('rate unit')__ ####

Return the rate unit string of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __ObjectData('rate with unit')__ ####

Return the rate value and unit of this plant from a Landscape Area. This must be used on a database row listing the plants of Landscape Areas.



#### __Area()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __SurfaceArea()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __Volume()__ ####

Calculate the volume of the Landscape Area, Hardscape, or Site Model and their components.



## Specialized for Lighting Device


#### __Weight(criteria)__ ####

Returns the total weight of the Lighting Device and all it's accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to the Instrument Type of Lighting Device accessories. Use no parameters for all cells and accessories or use parameters to specify cells or accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to a data of the Lighting Device accessory. Use  the first parameter to specify the universal parameter name. Use no parameters additional for all cells and accessories or use additional parameters to specify cells or accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to the symbol names of Lighting Device accessories. Use no parameters for all cells and accessories or use parameters to specify cells or accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to a parameter of the Lighting Devices and ignores accessories. Use parameters to specify the universal parameter name.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to the channel of Lighting Devices. Use no parameters for all cells and accessories or use parameters to specify cells or accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to the color of Lighting Devices. Use no parameters for all cells and accessories or use parameters to specify cells or accessories.



#### __ObjectData('Lighting Device', <field>)__ ####

Provides access to a parameter of Lighting Devices. Use parameters to specify the universal parameter name, cell number and accessory number.



## Specialized for Marionette Object


#### __ObjectData('parameter', '<OIP FieldName>')__ ####

Get parameter values or attached record fields from Marionette objects.



## Specialized for Panel Connector


#### __ObjectData('eval panel connector circuit', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the circuit connected to the panel connector.



## Specialized for Plant


#### __Count('excav component')__ ####

Returns the number of planting excavation components.



#### __Volume('excav component', <index>)__ ####

Returns the volume of the <index> planting excavation component.



#### __PlantImage(index)__ ####

Returns an image of the object at the specified index.


```python
Database header cell:
=PlantImage(2) displays the image specified for Image Detail in the More Data pane of the plant symbol definition

Spreadsheet cell:
=PlantImage((‘Plant’.’plant ID’=’TaxfR’), 4) displays the image specified for Custom Image in the More Data pane of the plant symbol definition with a plant ID of TaxfR

```

## Specialized for Railing


#### __Width()__ ####

This function is applicable to the following subparts: Frame, Panel, Bracket and Face Post.

QUANTITY DESCRIPTION:
For Frame: Width of the rectangular frame.

For Panel: Width of the rectangular panel.

For Bracket: width of bracket (actually represents the value of Handrail offset).

For Face Post: width of face post (actually represents the value of Inset).



#### __Width('brackets')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Width of bracket subpart.



#### __Width('face posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Width of face post subpart.



#### __Width('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the width of all frame subparts.



#### __Width('panels')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the width of all panel subparts.



#### __Width('profile')__ ####

This function is applicable to the following subparts: Handrail, Guardrail, Post, Frame, Bar Vertical, Bar Horizontal, Bracket and Face Post.

QUANTITY DESCRIPTION:
Width of subparts listed above.



#### __Height()__ ####

This function is applicable to the Railing object and the following subparts: Handrail, Guardrail, Frame, Panel, Bracket, Post and Face Post.

QUANTITY DESCRIPTION:
For Railing object: Height of the Railing object (actually represents the maximum value of Guardrail Height or Handrail Height).

For Frame: Height of the rectangular frame.

For Panel: Height of the rectangular panel.

For Handrail: Height of Handrail (actually represents the value of Handrail Height).

For Guardrail: Height of Guardrail (actually represents the value of Guardrail Height).

For Face Post: Height of Post.

For Post: Height of Post.



#### __Height('brackets')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Height of the bracket subpart.



#### __Height('face posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the height of all face post subparts.



#### __Height('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the height of all frame subparts.



#### __Height('guardrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Height of the Guardrail (actually represents the value of Guardrail Height).



#### __Height('handrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Height of the Handrail (actually represents the value of Handrail Height).



#### __Height('panels')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the height of all panel subparts.



#### __Height('posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the height of all post subparts.



#### __Height('profile')__ ####

This function is applicable to the following subparts: Handrail, Guardrail, Frame, Bar Vertical, Bar Horizontal, Bracket, Post and Face Post.

QUANTITY DESCRIPTION:
Height of profile of the individual subpart.



#### __Count('corners')__ ####

This function is applicable to the Railing object and the following subparts: Guardrail and Handrail.

QUANTITY DESCRIPTION:
For Railing object: Number of vertices that change the direction or height of the path without the beginning and end.

For Guardrail: Number of vertices that change the direction or height of the path without the beginning and end in the Guardrail subpart.

For Handrail: If there is no Guardrail, then number of vertices that change the direction or height of the path without the beginning and end in the Guardrail subpart.



#### __Angle()__ ####

This function is applicable to the following subparts: Bar Vertical and Bar Horizontal.

QUANTITY DESCRIPTION:
For Bar Vertical: Angle of the vertical bars(if option Rotate bars to diagonals on then 45° if not 0°.).

For Bar Horizontal: Angle of the horizontal bars(if option Rotate bars to diagonals on then 45° if not 0°.).



#### __Angle('bar horizontal')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
For Railing object: Angle of the horizontal bars(if option Rotate bars to diagonals on then 45° if not 0°.).



#### __Angle('bar vertical')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
For Railing object: Angle of the vertical bars(if option Rotate bars to diagonals on then 45° if not 0°.).



#### __Area()__ ####

This function is applicable to the Railing object and the following subparts: Frame, Panel, Bracket and Face Post.

QUANTITY DESCRIPTION:
For Railing object: Area of the entire Railing object.

For subpart: Area of the individual subpart.



#### __Area('brackets')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Area of bracket subpart.



#### __Area('face posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Area of face post subpart.



#### __Area('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the area of all frame subparts.



#### __Area('panels')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the area of all panel subparts.



#### __Perimeter()__ ####

This function is applicable to the Frame subpart.

QUANTITY DESCRIPTION:
Frame: Perimeter of the Frame.



#### __Perimeter('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
For Railing object: Perimeter of all Frames.



#### __Length()__ ####

This function is applicable to the Railing object and the following subparts: Handrail, Guardrail, Frame, Bar Vertical, Bar Horizontal, Bracket and Face Post.

QUANTITY DESCRIPTION:
For Railing object: Length of the 3D object path.

For Handrail: Length of the 3D handrail.

For Guardrail: Length of the 3D guardrail.

For Frame: With of frame.

For Bar Vertical: Length of the bar vertical.

For Bar Horizontal: Length of the bar horizontal.

For Bracket: Handrail Offset + Bracket Height.

For Face Post: Width + height of face post.



#### __Length('bar horizontal')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the length of all bar horizontal subparts.



#### __Length('bar vertical')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the length of all bar vertical subparts.



#### __Length('brackets')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Length of the bracket subpart.



#### __Length('face posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Length of the face post subpart.



#### __Length('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Length of the frame subpart.



#### __Length('guardrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the length of all guardrail subparts.



#### __Length('handrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the length of all handrail subparts.



#### __Length('max support spacing')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Maximum distance between posts if there no posts then returns the maximum distance between brackets.



#### __SurfaceArea()__ ####

This function is applicable to the following subparts: Handrail, Guardrail, Post, Frame, Panel, Bar Vertical, Bar Horizontal, Bracket and Face Post.

QUANTITY DESCRIPTION:
Complete outer surface area of subpart.



#### __SurfaceArea('bar horizontal')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all bar horizontal subparts.



#### __SurfaceArea('bar vertical')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all bar vertical subparts.



#### __SurfaceArea('brackets')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Surface area of bracket.



#### __SurfaceArea('face posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all face post subparts.



#### __SurfaceArea('frame')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all frame subparts.



#### __SurfaceArea('guardrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all guardrail subparts.



#### __SurfaceArea('handrail')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all handrail subparts.



#### __SurfaceArea('panels')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all panel subparts.



#### __SurfaceArea('posts')__ ####

This function is applicable to the Railing object.

QUANTITY DESCRIPTION:
Sum of the surface area of all post subparts.



## Specialized for Railing/Fence


#### __Width()__ ####

Width([optional parameter])

This function is applicable to the following subparts: Wall Bracket, Face Mount, Frame and Panel.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Wall Bracket: Horizontal dimension of the Top Rails Wall Bracket.

For Face Mount: Horizontal dimension of the Face Mount Post.

For Frame: Width of the rectangular frame.

For Panel: Width of the panel in elevation.



#### __Width('profile')__ ####

Width('profile', [optional parameter])

This function is applicable to the following subparts: Top Rail, Post, Crossbar Top and Bottom, Bar Vertical and Horizontal, Frame.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Top Rail: Width of the Railings TopRail cross section profile. For round or octagonal shape of profile, width equals height. For custom profile (symbol), the bounding box is used to calculate this value.

For Post: Width of the Posts cross section profile.

For Crossbar Top and Crossbar Bottom: Width of the profile of the crossbar.

For Bar Vertical and Bar Horizontal: Width of the vertical bars profile.



#### __Height()__ ####

Height([optional parameter])

This function is applicable to the Railing object and the following subparts: Top Rail, Wall Bracket, Post, Face Mount, Frame, Panel.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Railing object: The height of the railing, measured as the vertical distance between the top of the floor or stair (which is Height Point 1 in the object info palette) and the top of the highest subpart of the Railing (Top Rail if available, Frame, Panel or Crossbar Top).
This value is written into the IFC-field Pset_RailingCommon.Height.

For Top Rail: Height of the TopRail, measured as the distance between the top of the floor or stair (which is Height Point 1 in the object info palette) and the top of the Railings Top Rail.

For Wall Bracket: Vertical dimension of the Top Rails Wall Bracket.

For Post: Height of the Post.

For Face Mount: Vertical dimension of the Face Mount Post.

For Frame: Height of the rectangular frame.

For Panel: Height of the panel in elevation.



#### __Height('profile')__ ####

Height('profile', [optional parameter])

This function is applicable to the following subparts: Top Rail, Post, Crossbar Top and Bottom, Bar Vertical and Horizontal, Frame.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Top Rail: Height of the Railings TopRail cross section profile. For round or octagonal shape of profile, width equals height. For custom profile (symbol), the bounding box is used to calculate this value.

For Post: Height of the Posts cross section profile.

For Crossbar Top and Crossbar Bottom: Height of the profile of the crossbar.

For Bar Vertical and Bar Horizontal: Height of the vertical bars profile.



#### __Count('angle')__ ####

Count('angle', [optional parameter])

This function is applicable to the Railing object and the Top Rail.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Railing: Number of vertices that change the path without the beginning and end. Or IOW: the number of angles in the path..

For Top Rail: Number of angles  in the Top Rail subpart.



#### __Angle()__ ####

Angle([optional parameter])

This function is applicable to the following subparts: Bar Vertical and Bar Horizontal.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Bar Vertical: Angle of the vertical bars. Vertical is 0°.

For Bar Horizontal: Angle of the horizontal bar. horizontal is 0°.



#### __Area()__ ####

Area([optional parameter])

This function is applicable to the Railing object and the Panel subpart.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Railing: Area of the Railing object measured by Railing Length multiplied by Railing Height. Length is the distance between the outer edges of the first and last post or between the infills, whichever results in the higher value. Extended handrails are excluded. This Length differs from buildingSMART standard which is stored in the Railing objects record field RailingLengthIFC. The height of the railing is measured as the vertical distance between the top of the floor or stair (which is Height Point 1 in the object info palette) and the top of the highest subpart of the Railing (Top Rail if available, Frame, Panel or Crossbar Top).

For Panel: Area of the panel (Width x Height).



#### __Perimeter()__ ####





#### __Length('')__ ####

Length([optional parameter])

This function is applicable to the Railing object and the following subparts: Top Rail, Crossbar Top, Crossbar Bottom, Bar Vertical, Bar Horizontal, Frame.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Railing object: It is the distance between the outer edges of the first and last post or between the infills, whichever results in the higher value. Extended handrails are excluded. This Length differs from buildingSMART standard which is stored in the Railing objects record field RailingLengthIFC and written into Qto_RailingBaseQuantities.Length and BaseQuantities.Length.

For Top Rail: Length of the 3D path object of the top rail including extensions of the Top Rail at beginning or end of the Railing object.

For Crossbar Top and Bottom: Length of the crossbar.

For Bar Vertical and Horizontal: Length of the bar.

For Frame: It is the same value as for Width when applied to a Frame.



#### __Length('max')__ ####

Maximum occuring distance between the axes of all instances of a subparts.
Eligible subparts are Wall Bracket, Post and Face Mount.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Wall Bracket: Returns the maximum distance between the axes of all Wall Brackets occuring anywhere in the Railing object.

For Post: Maximum occuring distance between the axes of all posts.

For Face Mount: Maximum Distance between the axes of all Face Mounts. 



#### __SurfaceArea()__ ####

SurfaceArea([optional parameter])

This function is applicable to the following subparts: Top Rail, Wall Bracket, Post, Face Mount, Crossbar Top and Bottom, Bar Vertical and Horizontal, Frame, Panel.

OPTIONAL PARAMETER:
'subpart=...': If provided, only the given subpart is included.

QUANTITY DESCRIPTION:
For Top Rail: Outer surface of the top rail on all sides including the two caps at beginning and end.

For Wall Bracket: Complete outer surface of the Top Rails Wall Bracket.

For Post: Complete Outer Surface of the Post including the sides which face the stair or wall or handrail.

For Face Mount: Complete Outer Surface of the Face Mount Post including the caps surfaces which are mounted against a wall, post, stair or other object.

For Crossbar Top and Bottom: Complete Surface of all sides of the crossbar.

Bar Vertical and Horizontal: Complete Surface of all sides of the bar.

For Frame: Complete Surface of the rectangular frame.

For Panel: Complete surface area of all sides of the panel.



## Specialized for Roof


#### __ObjectData('Component Name')__ ####

Returns the name of the wall, slab or roof component.



#### __ObjectData('Cost Index Code')__ ####





#### __ObjectData('Cost Index System')__ ####





#### __ObjectData('Description')__ ####





#### __ObjectData('Exterior')__ ####





#### __ObjectData('Fire Rating')__ ####





#### __ObjectData('Function')__ ####





#### __ObjectData('Lambda')__ ####

Returns the Lambda value of the object.



#### __ObjectData('Manufacturer')__ ####





#### __ObjectData('Mark')__ ####





#### __ObjectData('Model')__ ####





#### __ObjectData('RValue')__ ####

Returns the R-Value of the object.



#### __ObjectData('UValue')__ ####

Returns the U-Value of the object.



#### __RoofArea_Total()__ ####

Returns the total area along the slope of a roof.


```python
Database header cell:
=RoofArea_Total returns the total area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Total(st=roofface) returns the combined total area of all roof face objects in the drawing
```

#### __RoofArea_Heated()__ ####

Returns the heated area along the slope of a roof. 
The heated area is the area that does not include an overhang.


```python
Database header cell:
=RoofArea_Heated returns the heated area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Heated (st=roofface) returns the combined heated area of all roof face objects in the drawing

```

#### __RoofArea_TotalProj()__ ####

Returns the total area of a roof projected on the active layer plane.


```python
Database header cell:
=RoofArea_TotalProj returns the total area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_Totalproj(t=roof) returns the combined total area of all roof objects in the drawing, as projected to the layer plane

```

#### __RoofArea_HeatedProj()__ ####

Returns the heated area of a roof projected on the active layer plane. 
The heated area is the area that does not include an overhang.


```python
Database header cell:
=RoofArea_HeatedProj returns the heated area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_HeatedProj (t=roof) returns the combined heated area of all roof objects in the drawing, as projected to the layer plane

```

#### __RoofStyleName()__ ####

Returns the name the roof style used by the object.


```python
Database header cell:
=RoofStyleName returns the roof style name for each roof object in the database

Spreadsheet cell:
=RoofStyleName(n='roof-1') returns the roof style name for the object named “roof-1”

```

## Specialized for Site Model


#### __Depth()__ ####

Calculate the depth of the Landscape Area, Hardscape, or Site Model and their components.



#### __ProjectedArea()__ ####

Calculate the projected area of the Landscape Area, Hardscape, or Site Model and their components.



#### __ObjectData('component name')__ ####

Return the name of the component subpart for Landscape Area, Hardscape, and Site Model.



#### __Area()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __SurfaceArea()__ ####

Calculate the surface area of the Landscape Area, Hardscape, or Site Model and their components.



#### __SurfaceArea( 'existing' )__ ####

Calculate the existing surface area of the Site Model and their components.


```python
Database header cell:
=SURFACEAREA('Existing')     Returns the existing Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Existing')    Returns the existing Surface Area for the selected Site Model object.

```

#### __SurfaceArea( 'proposed' )__ ####

Calculate the proposed surface area of the Site Model and their components.


```python
Database header cell:
=SURFACEAREA('Proposed')     Returns the proposed Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Proposed')    Returns the proposed Surface Area for the selected Site Model object.

```

#### __Volume()__ ####

Calculate the volume of the Landscape Area, Hardscape, or Site Model and their components.



#### __Volume('existing')__ ####

Calculate the existing volume of the Site Model and their components.


```python
Database header cell:
=VOLUME('existing')     	Returns the existing volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'existing')    Returns the existing volume for the selected Site Model object.

```

#### __Volume('proposed')__ ####

Calculate the proposed volume of the Site Model and their components.


```python
Database header cell:
=VOLUME('proposed')     	Returns the proposed volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'proposed')    Returns the proposed volume for the selected Site Model object.

```

## Specialized for Slab


#### __Weight('gross', [optional parameters])__ ####

Returns the weight of a wall, wall component, slab or slab component. All openings are ignored.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.



#### __Weight('net', [optional parameters])__ ####

Returns the weight of a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.



#### __ObjectData('Acoustic Rating')__ ####





#### __ObjectData('Combustible Construction')__ ####





#### __ObjectData('Compartmentation')__ ####





#### __ObjectData('Component Name')__ ####

Returns the name of the wall, slab or roof component.



#### __ObjectData('Cost Index Code')__ ####





#### __ObjectData('Cost Index System')__ ####





#### __ObjectData('Description')__ ####





#### __ObjectData('Exterior')__ ####





#### __ObjectData('Fire Rating')__ ####





#### __ObjectData('Function')__ ####





#### __ObjectData('Lambda')__ ####

Returns the Lambda value of the object.



#### __ObjectData('Load Bearing')__ ####





#### __ObjectData('Manufacturer')__ ####





#### __ObjectData('Mark')__ ####





#### __ObjectData('Model')__ ####





#### __ObjectData('RValue')__ ####

Returns the R-Value of the object.



#### __ObjectData('UValue')__ ####

Returns the U-Value of the object.



#### __Width()__ ####

Returns the thickness of a wall, slab, roof or a roof face object or their components.



#### __Count('modifiers', [optional parameters])__ ####

Returns the number of modifiers in a slab or wall. For walls, recesses and projections are counted. For slabs, additions, subtractions and drains are counted.

'modifier type=...': If provided, only modifiers with any of the given types are counted. Multiple types can be delimited by a semicolon.

'exclude modifier type=...': If provided, modifiers with any of the given types will not be counted.



#### __Count('openings', [optional parameters])__ ####

Returns the number of openings in a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only openings in the components with the given material will be counted.

'component=...': If provided, only openings in the given components will be counted. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

opening criteria: If provided, only openings that satisfy all given criteria will be counted. If the values don't have any units specified, millimeters, square millimeters or cubic millimeters will be assumed. For slabs, the following criteria are available: min opening area top, max opening area top, min opening area bottom, max opening area bottom, min opening volume, max opening volume, min opening perimeter top, max opening perimeter top, min opening perimeter bottom, max opening perimeter bottom. For walls, the following criteria are available: min opening area left, max opening area left, min opening area right, max opening area right, min opening area facing core, max opening area facing core, min opening area avert core, max opening area avert core, min opening area center, max opening area center, min opening area footprint, max opening area footprint, min opening length footprint left, max opening length footprint left, min opening length footprint right, max opening length footprint right, min opening length footprint facing core, max opening length footprint facing core, min opening length footprint avert core, max opening length footprint avert core, min opening length footprint center, max opening length footprint center, min opening volume, max opening volume.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.

'height=...': Specifies the height relative to the layer plane at which the footprint area and length along footprint criteria are measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.


```python
=Count('openings') returns the number of openings in the wall, wall component, slab or slab component.

=Count('openings', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters.

=Count('openings', 'min opening area top=0.5 sq m', 'max opening area top=1 sq m') returns the number of openings with an area between 0.5 and 1 square meter on the top of the slab or slab component.

=Count('openings', 'min opening area bottom=1 sq ft', 'max opening volume=10 cu in') returns the number of openings with an area of at least 1 square foot on the bottom of the slab or slab component and a volume of at most 10 cubic inches.

=Count('openings', 'opening type=Window') returns the number of openings created by "Window" plug-in objects.

=Count('openings', 'opening type=Window;WinDoor 6.0') returns the number of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Count('openings', 'component=core', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters in the wall core component.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.
```

#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



#### __SlabThickness()__ ####

Returns the thickness of slab objects.


```python
Database header cell:
=SlabThickness returns the thickness for each object in the database

Spreadsheet cell:
=SlabThickness(PON=slab) returns the combined thickness of all slab objects in the drawing

```

#### __SlabStyleName()__ ####

Returns the name of the slab style used by the slab.


```python
Database header cell:
=SlabStyleName returns the name of the slab style for each slab object in the database

Spreadsheet cell:
=SlabStyleName(n='slab-1') returns the name of the slab style for the object named “slab-1”

```

#### __Area()__ ####

Returns the area of a wall, slab, roof or a roof face object or their components.



#### __Perim('bottom', [optional parameters])__ ####

Returns the perimeter of the bottom surface of a slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.



#### __Perim('openings bottom', [optional parameters])__ ####

Returns the sum of the opening perimeters on the bottom surface of a slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening perimeter=...' / 'max opening perimeter=...': If provided, only openings with a perimeter of at least min opening perimeter and at most max opening perimeter will be included. If the values don't have any units specified, millimeters will be assumed.



#### __Perim('openings top', [optional parameters])__ ####

Returns the sum of the opening perimeters on the top surface of a slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening perimeter=...' / 'max opening perimeter=...': If provided, only openings with a perimeter of at least min opening perimeter and at most max opening perimeter will be included. If the values don't have any units specified, millimeters will be assumed.



#### __Perim('top', [optional parameters])__ ####

Returns the perimeter of the top surface of a slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.



#### __SurfaceArea('bottom gross', [optional parameters])__ ####

Returns the area of the bottom surface of a slab or slab component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.


```python
=SurfaceArea('bottom gross') returns the gross area of the bottom face of the slab or slab component.

=SurfaceArea('bottom gross', 'component=top') returns the gross area of the bottom face of the top component of the slab.
```

#### __SurfaceArea('bottom net', [optional parameters])__ ####

Returns the area of the bottom surface of a slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.


```python
=SurfaceArea('bottom net') returns the area of the bottom face of the slab or slab component.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('bottom net', 'component=top') returns the area of the bottom face of the top component of the slab.
```

#### __SurfaceArea('openings bottom', [optional parameters])__ ####

Returns the area of the openings on the bottom surface of a slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.


```python
=SurfaceArea('openings bottom') returns the total area of openings on the bottom face of the slab or slab component.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings bottom', 'component=top') returns the total area of openings on the bottom face of the top component of the slab.
```

#### __SurfaceArea('openings top', [optional parameters])__ ####

Returns the area of the openings on the top surface of a slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.


```python
=SurfaceArea('openings top') returns the total area of openings on the top face of the slab or slab component.

=SurfaceArea('openings top', 'min opening area=0.5 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings top', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings top', 'component=bottom') returns the total area of openings on the top face of the bottom component of the slab.
```

#### __SurfaceArea('top gross', [optional parameters])__ ####

Returns the area of the top surface of a slab or slab component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.


```python
=SurfaceArea('top gross') returns the gross area of the top face of the slab or slab component.

=SurfaceArea('top gross', 'component=bottom') returns the gross area of the top face of the bottom component of the slab.
```

#### __SurfaceArea('top net', [optional parameters])__ ####

Returns the area of the top surface of a slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are top, bottom or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.


```python
=SurfaceArea('top net') returns the area of the top face of the slab or slab component.

=SurfaceArea('top net', 'min opening area=0.5 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('top net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('top net', 'component=bottom') returns the area of the top face of the bottom component of the slab.
```

#### __Volume()__ ####

Returns the volume of a wall, slab, roof or a roof face object or their components.



#### __Volume('gross', [optional parameters])__ ####

Returns the volume of a wall, wall component, slab or slab component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.


```python
=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.
```

#### __Volume('net', [optional parameters])__ ####

Returns the volume of a wall, wall component, slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

'min opening volume=...' / 'max opening volume=...': If provided, only openings with a volume of at least min opening volume and at most max opening volume will be included. If the values don't have any units specified, cubic millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls. 

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.


```python
=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.
```

#### __Volume('openings', [optional parameters])__ ####

Returns the volume of the openings in a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

'min opening volume=...' / 'max opening volume=...': If provided, only openings with a volume of at least min opening volume and at most max opening volume will be included. If the values don't have any units specified, cubic millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls. 

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.


```python
=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.
```

## Specialized for Socket


#### __ObjectData('eval socket circuits', '<RecordName>', '<FieldName>')__ ####

Get parameter values or attached record fields from the socket's connected circuits.



#### __ObjectData('eval socket device', '<RecordName>', '<FieldName>')__ ####

Get parameter value or attached record field from the socket's device.



## Specialized for Space


#### __GetSpaceNameForObj()__ ####

Returns the name of the space that surrounds the object.


```python
Database header cell:
=GetSpaceNameForObj returns the space name for each object in the database

Spreadsheet cell:
=GetSpaceNameForObj(n='chair-1') returns the space name for the object named “chair-1”

```

#### __GetSpaceNumForObj()__ ####

Returns the number of the space that surrounds the object.


```python
Database header cell:
=GetSpaceNumForObj returns the space number for each object in the database

Spreadsheet cell:
=GetSpaceNumForObj(n='chair-1') returns the space number for the object named “chair-1”
```

## Specialized for Structural Member


#### __ObjectData(criteria, 'cover bound bottom')__ ####

Returns the bottom bound of the structural member cover.


```python
Database header cell:
=OBJECTDATA('cover bound bottom')     Returns the bottom bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound bottom')    Returns the bottom bound of the Structural Member cover.

```

#### __ObjectData(criteria, 'cover bound top')__ ####

Returns the top bound of the Structural Member cover.


```python
Database header cell:
=OBJECTDATA('cover bound top')     Returns the top bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound top')    Returns the top bound of the Structural Member cover.

```

#### __ObjectData(criteria, 'cover physical length')__ ####

Returns the physical length of the structural member cover including its start and end conditions.


```python
Database header cell:
=OBJECTDATA('cover physical length')     Returns the physical length of the structural member cover including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover physical length')    Returns the physical length of the structural member cover including its start and end conditions.

```

#### __ObjectData(criteria, 'member bound bottom')__ ####

Returns the bottom bound of the Structural Member.


```python
Database header cell:
=OBJECTDATA('member bound bottom')     Returns the bottom bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound bottom')    Returns the bottom bound of the Structural Member.

```

#### __ObjectData(criteria, 'member bound top')__ ####

Returns the top bound of the Structural Member.


```python
Database header cell:
=OBJECTDATA('member bound top')     Returns the top bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound top')    Returns the top bound of the Structural Member.

```

#### __ObjectData(criteria, 'member physical length')__ ####

Returns the physical length of the structural member including its start and end conditions.


```python
Database header cell:
=OBJECTDATA('member physical length')     Returns the physical length of the structural member including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member physical length')    Returns the physical length of the structural member including its start and end conditions.

```

## Specialized for Wall


#### __Weight('gross', [optional parameters])__ ####

Returns the weight of a wall, wall component, slab or slab component. All openings are ignored.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.



#### __Weight('net', [optional parameters])__ ####

Returns the weight of a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.



#### __FootPrintArea('gross', [optional parameters])__ ####

Returns the footprint area of a wall or wall component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the area is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __FootPrintArea('net', [optional parameters])__ ####

Returns the footprint area of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the area is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __FootPrintArea('openings', [optional parameters])__ ####

Returns the area of the openings in the footprint of a wall or wall component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the area is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __ObjectData('Acoustic Rating')__ ####





#### __ObjectData('Combustible Construction')__ ####





#### __ObjectData('Compartmentation')__ ####





#### __ObjectData('Component Name')__ ####

Returns the name of the wall, slab or roof component.



#### __ObjectData('Cost Index Code')__ ####





#### __ObjectData('Cost Index System')__ ####





#### __ObjectData('Description')__ ####





#### __ObjectData('Exterior')__ ####





#### __ObjectData('Fire Rating')__ ####





#### __ObjectData('Function')__ ####





#### __ObjectData('Lambda')__ ####

Returns the Lambda value of the object.



#### __ObjectData('Load Bearing')__ ####





#### __ObjectData('Manufacturer')__ ####





#### __ObjectData('Mark')__ ####





#### __ObjectData('Model')__ ####





#### __ObjectData('Path Type')__ ####

Returns the path type of a wall. 0 is line, and 1 is arc.



#### __ObjectData('RValue')__ ####

Returns the R-Value of the object.



#### __ObjectData('UValue')__ ####

Returns the U-Value of the object.



#### __Width()__ ####

Returns the thickness of a wall, slab, roof or a roof face object or their components.



#### __Height('average')__ ####

Returns the average height of a wall, including wall peaks and different starting and ending heights.



#### __Height('overall')__ ####

Returns the overall height of a wall.



#### __Count('inserts', [optional parameters])__ ####

Returns the number of inserts (symbols and parametric objects) in a wall.

'insert type=...': If provided, only inserts with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude insert type=...': If provided, inserts with any of the given types will not be counted.


```python
=Count('inserts') returns the number of inserts in the wall object.

=Count('inserts', 'insert type=Window') returns the number of "Window" plug-in object inserts.

=Count('inserts', 'insert type=Window;WinDoor 6.0') returns the number of by "Window" and "WinDoor 6.0" plug-in object inserts.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.
```

#### __Count('modifiers', [optional parameters])__ ####

Returns the number of modifiers in a slab or wall. For walls, recesses and projections are counted. For slabs, additions, subtractions and drains are counted.

'modifier type=...': If provided, only modifiers with any of the given types are counted. Multiple types can be delimited by a semicolon.

'exclude modifier type=...': If provided, modifiers with any of the given types will not be counted.



#### __Count('openings', [optional parameters])__ ####

Returns the number of openings in a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be counted.

'component material=...': If provided, only openings in the components with the given material will be counted.

'component=...': If provided, only openings in the given components will be counted. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

opening criteria: If provided, only openings that satisfy all given criteria will be counted. If the values don't have any units specified, millimeters, square millimeters or cubic millimeters will be assumed. For slabs, the following criteria are available: min opening area top, max opening area top, min opening area bottom, max opening area bottom, min opening volume, max opening volume, min opening perimeter top, max opening perimeter top, min opening perimeter bottom, max opening perimeter bottom. For walls, the following criteria are available: min opening area left, max opening area left, min opening area right, max opening area right, min opening area facing core, max opening area facing core, min opening area avert core, max opening area avert core, min opening area center, max opening area center, min opening area footprint, max opening area footprint, min opening length footprint left, max opening length footprint left, min opening length footprint right, max opening length footprint right, min opening length footprint facing core, max opening length footprint facing core, min opening length footprint avert core, max opening length footprint avert core, min opening length footprint center, max opening length footprint center, min opening volume, max opening volume.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.

'height=...': Specifies the height relative to the layer plane at which the footprint area and length along footprint criteria are measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.


```python
=Count('openings') returns the number of openings in the wall, wall component, slab or slab component.

=Count('openings', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters.

=Count('openings', 'min opening area top=0.5 sq m', 'max opening area top=1 sq m') returns the number of openings with an area between 0.5 and 1 square meter on the top of the slab or slab component.

=Count('openings', 'min opening area bottom=1 sq ft', 'max opening volume=10 cu in') returns the number of openings with an area of at least 1 square foot on the bottom of the slab or slab component and a volume of at most 10 cubic inches.

=Count('openings', 'opening type=Window') returns the number of openings created by "Window" plug-in objects.

=Count('openings', 'opening type=Window;WinDoor 6.0') returns the number of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Count('openings', 'component=core', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters in the wall core component.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.
```

#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



#### __WallArea_Net()__ ####

Returns the average of the net area of the interior and exterior face of the wall. The net area is adjusted for holes in the wall.


```python
Database header cell:
=WallArea_Net returns the average of the net area of the interior and exterior face of the wall, for each wall in the database; the net area is adjusted for holes in the wall

Spreadsheet cell:
=WallArea_Net(t=wall) returns the average of the net area of the interior and exterior face of the wall, combined for all walls in the drawing; the net area is adjusted for holes in the wall

```

#### __WallArea_Gross()__ ####

Returns the average of the gross area of the interior and exterior face of the wall. The gross area ignores holes in the wall.


```python
Database header cell:
=WallArea_Gross returns the average of the gross area of the interior and exterior face of the wall, for each wall in the database; the gross area ignores holes in the wall

Spreadsheet cell:
=WallArea_Gross(t=wall) returns the average of the gross area of the interior and exterior face of the wall, combined for all walls in the drawing; the gross area ignores holes in the wall

```

#### __WallAverageHeight()__ ####

Returns the average wall height of a wall, including wall peaks and different starting and ending heights.


```python
Database header cell:
=WallAverageHeight returns the average height for each wall object in the database

Spreadsheet cell:
=WallAverageHeight((t=wall)&(sel=true)) returns the average height of all walls that are selected in the drawing

```

#### __WallThickness()__ ####

Returns the thickness of the wall.


```python
Database header cell:
=WallThickness returns the thickness for each wall object in the database

Spreadsheet cell:
=WallThickness(t=wall) returns the combined thickness of all walls in the drawing

```

#### __WallStyleName()__ ####

Returns the name of the wall style used by the wall.


```python
Database header cell:
=WallStyleName returns the name of the wall style for each wall object in the database

Spreadsheet cell:
=WallStyleName(n='wall-1') returns the name of the wall style for the object named “wall-1”

```

#### __Area()__ ####

Returns the area of a wall, slab, roof or a roof face object or their components.



#### __Length()__ ####

Returns the length of a wall or its components.



#### __Length('control line avert core', [optional parameters])__ ####

Returns the length of the control line of a wall component on the side that's oriented away from the core component. All openings, recesses, projections and peaks are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __Length('control line center', [optional parameters])__ ####

Returns the length of the central control line of a wall or wall component. All openings, recesses, projections and peaks are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __Length('control line facing core', [optional parameters])__ ####

Returns the length of the control line of a wall component on the side that's oriented towards the core component. All openings, recesses, projections and peaks are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __Length('control line left', [optional parameters])__ ####

Returns the length of the left control line of a wall or wall component. All openings, recesses, projections and peaks are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __Length('control line right', [optional parameters])__ ####

Returns the length of the right control line of a wall or wall component. All openings, recesses, projections and peaks are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __Length('avert core gross', [optional parameters])__ ####

Returns the length of a wall component along the bottom of the side that's oriented away from the core component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('avert core net', [optional parameters])__ ####

Returns the length of a wall component along the bottom of the side that's oriented away from the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('center gross', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the center line. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('center net', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the center line.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('facing core gross', [optional parameters])__ ####

Returns the length of a wall component along the bottom of the side that's oriented towards the core component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('facing core net', [optional parameters])__ ####

Returns the length of a wall component along the bottom of the side that's oriented towards the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('left gross', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the left face. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('left net', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the left face.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('right gross', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the right face. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('right net', [optional parameters])__ ####

Returns the length of a wall or wall component along the bottom of the right face.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('openings avert core', [optional parameters])__ ####

Returns the total length of wall or wall component openings along the side of the footprint that's oriented away from the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('openings center', [optional parameters])__ ####

Returns the total length of openings along the center line of the footprint of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('openings facing core', [optional parameters])__ ####

Returns the total length of wall or wall component openings along the side of the footprint that's oriented towards the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('openings left', [optional parameters])__ ####

Returns the total length of openings along the left side of the footprint of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __Length('openings right', [optional parameters])__ ####

Returns the total length of openings along the right side of the footprint of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening length=...' / 'max opening length=...': If provided, only openings with a length of at least min opening length and at most max opening length will be included. If the values don't have any units specified, millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.

'height=...': Specifies the height relative to the layer plane at which the length is measured. A height of 0 is used by default. If the value doesn't have any units specified, millimeters will be assumed.



#### __SurfaceArea('avert core gross', [optional parameters])__ ####

Returns the area of a wall component's surface that's oriented away from the core component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __SurfaceArea('avert core net', [optional parameters])__ ####

Returns the area of a wall component's surface that's oriented away from the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.



#### __SurfaceArea('center gross', [optional parameters])__ ####

Returns the area along the center line of a wall or wall component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.


```python
=SurfaceArea('center gross') returns the gross area along the center line of the wall or wall component.

=SurfaceArea('center gross', 'component=core') returns the gross area along the center line of the core component of the wall.
```

#### __SurfaceArea('center net', [optional parameters])__ ####

Returns the area along the center line of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('center net') returns the area along the center line of the wall or wall component.

=SurfaceArea('center net', 'min opening area=0.5 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('center net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('center net', 'opening type=Window') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('center net', 'exclude opening type=Window') returns the area along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('center net', 'opening type=Window;WinDoor 6.0') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('center net', 'component=core') returns the area along the center line of the core component of the wall.
```

#### __SurfaceArea('facing core gross', [optional parameters])__ ####

Returns the area of a wall component's surface that's oriented towards the core component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.



#### __SurfaceArea('facing core net', [optional parameters])__ ####

Returns the area of a wall component's surface that's oriented towards the core component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.



#### __SurfaceArea('left gross', [optional parameters])__ ####

Returns the area of the left surface of a wall or wall component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.


```python
=SurfaceArea('left gross') returns the gross area of the left side of the wall or wall component.

=SurfaceArea('left gross', 'component=core') returns the gross area of the left side of the core component of the wall.
```

#### __SurfaceArea('left net', [optional parameters])__ ####

Returns the area of the left surface of a wall or wall component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('left net') returns the area of the left side of the wall or wall component.

=SurfaceArea('left net', 'min opening area=0.5 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('left net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('left net', 'opening type=Window') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('left net', 'exclude opening type=Window') returns the area of the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('left net', 'opening type=Window;WinDoor 6.0') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('left net', 'component=core') returns the area of the left side of the core component of the wall.
```

#### __SurfaceArea('openings avert core', [optional parameters])__ ####

Returns the area of the openings on a wall component's surface that's oriented away from the core component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.



#### __SurfaceArea('openings center', [optional parameters])__ ####

Returns the area of the openings along the center line of a wall or wall component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('openings center') returns the total area of openings along the center line of the wall or wall component.

=SurfaceArea('openings center', 'min opening area=0.5 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings center', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings center', 'opening type=Window') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings center', 'exclude opening type=Window') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings center', 'opening type=Window;WinDoor 6.0') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings center', 'component=core') returns the total area of openings along the center line of the core component of the wall.
```

#### __SurfaceArea('openings facing core', [optional parameters])__ ####

Returns the area of the openings on a wall component's surface that's oriented towards the core component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.



#### __SurfaceArea('openings left', [optional parameters])__ ####

Returns the area of the openings on the left surface of a wall or wall component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('openings left') returns the total area of openings on the left side of the wall or wall component.

=SurfaceArea('openings left', 'min opening area=0.5 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings left', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings left', 'opening type=Window') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings left', 'exclude opening type=Window') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings left', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings left', 'component=core') returns the total area of openings on the left side of the core component of the wall.
```

#### __SurfaceArea('openings right', [optional parameters])__ ####

Returns the area of the openings on the right surface of a wall or wall component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('openings right') returns the total area of openings on the right side of the wall or wall component.

=SurfaceArea('openings right', 'min opening area=0.5 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings right', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings right', 'opening type=Window') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings right', 'exclude opening type=Window') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings right', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings right', 'component=core') returns the total area of openings on the right side of the core component of the wall.
```

#### __SurfaceArea('right gross', [optional parameters])__ ####

Returns the area of the right surface of a wall or wall component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.


```python
=SurfaceArea('right gross') returns the gross area of the right side of the wall or wall component.

=SurfaceArea('right gross', 'component=core') returns the gross area of the right side of the core component of the wall.
```

#### __SurfaceArea('right net', [optional parameters])__ ####

Returns the area of the right surface of a wall or wall component.

'component name=...': If provided, components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core or a number indicating the component index.

'min opening area=...' / 'max opening area=...': If provided, only openings with an area of at least min opening area and at most max opening area will be included. If the values don't have any units specified, square millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon.

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted.


```python
=SurfaceArea('right net') returns the area of the right side of the wall or wall component.

=SurfaceArea('right net', 'min opening area=0.5 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('right net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('right net', 'opening type=Window') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('right net', 'exclude opening type=Window') returns the area of the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('right net', 'opening type=Window;WinDoor 6.0') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('right net', 'component=core') returns the area of the right side of the core component of the wall.
```

#### __Volume()__ ####

Returns the volume of a wall, slab, roof or a roof face object or their components.



#### __Volume('gross', [optional parameters])__ ####

Returns the volume of a wall, wall component, slab or slab component. All openings are ignored.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.


```python
=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.
```

#### __Volume('net', [optional parameters])__ ####

Returns the volume of a wall, wall component, slab or slab component.

'component name=...': If provided, only components with the given name will be included.

'component material=...': If provided, only components with the given material will be included.

'component=...': If provided, only the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

'min opening volume=...' / 'max opening volume=...': If provided, only openings with a volume of at least min opening volume and at most max opening volume will be included. If the values don't have any units specified, cubic millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls. 

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.


```python
=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.
```

#### __Volume('openings', [optional parameters])__ ####

Returns the volume of the openings in a wall, wall component, slab or slab component.

'component name=...': If provided, only openings in the components with the given name will be included.

'component material=...': If provided, only openings in the components with the given material will be included.

'component=...': If provided, only openings in the given components will be included. Possible values are left, right, core (for walls), top, bottom (for slabs) or a number indicating the component index.

'min opening volume=...' / 'max opening volume=...': If provided, only openings with a volume of at least min opening volume and at most max opening volume will be included. If the values don't have any units specified, cubic millimeters will be assumed.

'opening type=...': If provided, only openings created by objects with any of the given names will be counted. Multiple names can be delimited by a semicolon. Only applicable for walls. 

'exclude opening type=...': If provided, openings created by objects with any of the given names will not be counted. Only applicable for walls.


```python
=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.
```

#### __WallOverallHeight()__ ####

Returns the overall height of walls.


```python
Database header cell:
=WallOverallHeight returns the average overall height for each wall object in the database

Spreadsheet cell:
=WallOverallHeight((t=wall)&(sel=true)) returns the average overall height of all walls that are selected in the drawing

```

## Specialized for WinDoor 6.0


#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



## Specialized for Window


#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



#### __Volume(criteria, 'glazing all')__ ####

Returns the total volume of all glazing.


```python
Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.

```

#### __Volume(criteria, 'glazing for sashes')__ ####

Returns the volume of glazing for all sashes except the transom.


```python
Database header cell:
=VOLUME('glazing for sashes')     Returns the volume of glazing for all sashes except the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sashes')    Returns the volume of glazing for all sashes except the transom.

```

#### __Volume(criteria, 'glazing for transom')__ ####

Returns the volume of glazing for the transom.


```python
Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.

```

#### __Volume(criteria, 'window jamb')__ ####

Returns the volume of all geometry that makes up the Jamb and Mullions.


```python
Database header cell:
=VOLUME('window jamb')     Returns the volume of all geometry that makes up the Jamb and Mullions.

Spreadsheet cell:
=VOLUME(SEL, 'window jamb')   Returns the volume of all geometry that makes up the Jamb and Mullions.

```

#### __Volume(criteria, 'window sashes')__ ####

Returns the total volume the all sashes (including the transom sash).


```python
Database header cell:
=VOLUME('window sashes')     Returns the total volume the all sashes (including the transom sash).

Spreadsheet cell:
,VOLUME(SEL, 'window sashes')    Returns the total volume the all sashes (including the transom sash).

```

## Specialized for Window CW


#### __Angle('energos')__ ####

Get the orientation from the north used in the Energos calculations for this object.



## Text


#### __concat(text1, text2,...)__ ####

Joins several text strings into one text string.


```python
=concat(B3,', ',B4) returns the contents of cells B3 and B4 as a single string, separated by a comma and a space

```

#### __SubString(text, delimiter, index)__ ####

Splits a single string into an array of strings using a delimiter, and returns the string at the specified index.


```python
=SUBSTRING('kitchen;bedroom;bathroom;basement', ';', 2) returns “bedroom,” which is the second substring in the specified string

```

#### __txt(value, ToUnit, [Param1], [Param2], ...)__ ####

Converts a numeric value from document units to the specified units and returns a string representation using the options to control formatting. More information is available in the example.


```python
The first parameter must be <ToUnit> and then a list of optional parameters to fine tune the conversion.

Parameter Details:
 - <ToUnit> - the units in which the value will be converted from the current document units
	Possible options are for using the current document units:
		Dim		- linear dimension 
		Area	- area dimension
		Volume	- volume dimension
		Angle	- angular dimension
		
	General purpose options:
		General	- as a general number
		Sci		- as a scienific number
		Percent	- as a percent number
	
	Linear specific units options (one of the list):
		FeetNInches, Inches, Feet, Miles, Yards, Microns, Millimeters, Centimeters, Meters, Kilometers, Degrees, Ares
	
	Area specific units options (one of the list):
		SquareInches, SquareFeet, SquareYards, SquareMiles, Acres, SquareMicrons, SquareMillimeters, SquareCentimeters, SquareMeters, SquareKilometers, Hectares
	
	Volume specific units options (one of the list):
		CubicInches, CubicFeet, CubicYards, Gallons, CubicMillimeters, CubicCentimeters, CubicMeters, Litres

 - <optional param> - rounding style
		Dec		- decimal representation of the number
		Frac	- fractional representation of the number
		Auto	- will use fractional representation if rounds up to one, or decimal representation if not

 - <optional param> - rounding format
	Decimal rounding represented by the number of digits after the decimal dot.
	Examples:
		0.000	- would round up three digits. e.g. 0.356 if the number is 0.3556678
		0.0		- would round up one digit. e.g. 0.4 if the number is 0.3556678
		0.		- would round up to no digits. e.g. 0 if the number is 0.3556678
	
	Fractional rounding represented by the number after the / symbol, from 1/1 to 1/64 max.
	Examples:
		1/8		- would round to 1/8th
		1/64	- would round to 1/64th
		1/1		- would round to integer number

- <optional param> - rounding base using multiples of tenths, quarters, or halves
		RoundTenth
		RoundQuarter
		RoundHalf

- <optional param> - Units display
		NoUnits
		Units

- <optional param> - thousands separator display
		ThousandsSeparator
		NoThousandsSeparator

- <optional param> - trailing zero display
		NoTrailingZero
		TrailingZero

- <optional param> - leading zero
		NoLeadingZeroes
		LeadingZeroes

Examples:
=TXT(2.45, 'Dim') - returns the number in the documents linear dimensions
=TXT(2.45, 'Feet', 'Frac', '1/16') - returns the number in feet as fraction with 1/16 rounding

```

#### __isalnum(text)__ ####

True if all characters in the string are letters and/or digits and there is at least one character or digit, false otherwise. Real numbers will return False.


```python
=isalnum('word123') returns True

```

#### __isalpha(text)__ ####

True if all characters in the string are alphabetic and there is at least one character, false otherwise.


```python
=isalpha('word') returns True

```

#### __isdigit(text)__ ####

True if all characters in the string are digits and there is at least one digit, false otherwise. Real numbers will return False.


```python
=isdigit('1234') returns True

```

#### __islower(text)__ ####

True if all cased characters in the string are lowercase and there is at least one cased character, false otherwise. Non-alphabetic characters don't have a case and will return true.


```python
=islower('does not have upper char') returns True

```

#### __isspace(text)__ ####

True if there are only whitespace characters in the string and there is at least one character, false otherwise.


```python
=isspace('      ') returns True

```

#### __istitle(text)__ ####

True if the string is a titlecased string and there is at least one character, for example uppercase characters may only follow uncased characters and lowercase characters only cased ones. False otherwise.


```python
=isTitle('This Is Title Text') returns True

```

#### __isupper(text)__ ####

True if all cased characters in the string are uppercase and there is at least one cased character, false otherwise. Non-alphabetic characters don't have a case and will return true.


```python
=isUpper('DOES NOT HAVE LOWER CHARS') returns True

```

#### __TextJoin(delimiter, text1, text2, …)__ ####

The string which is the concatenation of the strings in the sequence seq. The separator between elements is the string providing this method.


```python
=textJoin(', ', 1, 2, 3) returns '1, 2, 3'

```

#### __Lower(text)__ ####

Converts all characters in a text string to lowercase.


```python
=lower('MAKE THIS LOWER') returns 'make this lower'

```

#### __TrimLeft(text, [chars])__ ####

Removes leading characters from a text string. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed.


```python
=trimLeft('abbcwordabbc', 'abc') returns 'wordabbc'

```

#### __Replace(string, oldString, newString, [count])__ ####

Replaces occurrences of a substring in a text with a different substring. If the optional argument count is given, only the first count occurrences are replaced.


```python
=replace('my car is your car', 'car', 'ball', 2) returns 'my car is your ball'

```

#### __TrimRight(text, [chars])__ ####

Removes trailing characters from a text string. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed.


```python
=trimRight('abbcwordabbc', 'abc') returns 'abbcword'

```

#### __Trim(text, [chars])__ ####

Removes leading and trailing characters from a text string. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed.


```python
=trim('abbcwordabbc', 'abc') returns 'word'

```

#### __Proper(text)__ ####

Converts a text string to titlecase. The first letter in each word starts with uppercase characters, all remaining characters are lowercase.


```python
=proper('make this title text') returns 'Make This Title Text'

```

#### __Upper(text)__ ####

Converts all characters in a text string to uppercase.


```python
=upper('make this upper') returns 'MAKE THIS UPPER'

```

#### __Len(text)__ ####

The number of characters in the (text) string.


```python
=len('hello there') returns 11

```

#### __Insert(text, index, textToInsert)__ ####

Inserts a text (textToInsert) into an existing text string (text) at specified index position.


```python
=insert('hey, this is ok', 12, ' not') returns 'hey, this is not ok'

```

#### __Left(text, count)__ ####

Returns a string with the specified number of characters from the start of the text value.


```python
=left('this is sample', 4) returns 'this'

```

#### __Right(text, count)__ ####

Returns a string with the specified number of characters from the end of the text value.


```python
=right('this is sample', 6) returns 'sample'

```

#### __Mid(text, index, count)__ ####

Returns a string with the specified number of characters starting at a given position in the text value


```python
=mid('apple', 2, 3) returns 'ppl'
=mid('apple', -4, 3) looking the index backwards, returns 'ppl'
=mid('apple', 4, -3) getting characters backward from the index, returns 'ppl
```

#### __Delete(text, index, count)__ ####

Removes the specified number (count) of characters from the text string starting at a given position (index).


```python
=delete('this is sample', 4, 3) returns 'this sample'. Here 3 characters after the 4th are deleted.

```

#### __Quote(text)__ ####

Returns a the text enclosed in quotation marks.


```python
=quote('quote this') returns "quote this" (The text, in double quotes)

```

#### __Rept(text, num)__ ####

Repeats text a given number of times.


```python
=rept('Line ', 3) returns 'Line Line Line '

```

#### __Fixed(num, [decimals])__ ####

Formats a number as text with a fixed number of decimals.


```python
=fixed(10.12345, 3) returns 10.123 (up to the 3rd digit after the decimal point)

```

#### __JustNum(num, width)__ ####

Returns a numeric string of the specified size (width) with leading zeros appended to the number. The original string is returned if width is less than the original string length.


```python
=justNum(10.123, 8) returns '0010.123'

```

#### __Char(number)__ ####

Returns the Unicode character or text representation (U+1234) referenced by the given number .


```python
=char(8734) returns the symbol ∞
=char('U+221E') also returns ∞

```

#### __Code(text)__ ####

Returns the number (Unicode code point) for the first character of the text.


```python
=code('∞') returns 8734. The unicode codepoint for ∞

```

#### __Find(subtext, text, [caseSensitive])__ ####

The lowest index in the (text) where substring (subtext) is found. If the optional argument (case) is set to true, case-sensitive search is performed. Index of -1 if (subtext) is not found.


```python
=find('text', 'this is text') returns 8

```

#### __FindPattern(pattern, text, [caseSensitive])__ ####

The lowest index in the (text) where the regular expression provided in (pattern)  is found.  If the optional argument (case) is set to true, case-sensitive search is performed. Index of -1 if (subtext) is not found. Regular expression is a sequence of characters that specifies a search pattern. Uses ECMAScript syntax for the pattern: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


```python
=findPattern('(Soft)(.*)', 'soft Software', True) returns 5

```

#### __value(text)__ ####

Converts a text string that represents a number to a number.


```python
=value('2e3') returns the numeric value of 2 times 10 raised to the power of 3

```

