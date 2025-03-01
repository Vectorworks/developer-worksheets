{{LocationMain|category=LocationWorksheetsSpecial|specific=}}
<div class="rightmenu">
__TOC__
</div>

## Vectorworks 2022

### Value functions

Vectorworks 2022 introduced a set of new Worksheet functions to cover all Data Manager functions and overall cover more value operations.

Here is a table that lists the Existing (prior to Vectorworks 2021) functions, the Data Manager functions, and the newly added Vectorworks 2022 functions:

| Existing WS | Existing Data Manager | New WS | Category and description |
|-------------|-----------------------|--------|--------------------------|
|             | ABS (number)          | Abs(number) | The absolute value of a number. |
|             |                       | Quotient(numerator, denominator) | Computes the quotient and the remainder of an integer division. |
| #There is already a MOD operator | | Mod(number, divisor) | The remainder after a number is divided by a divisor. |
| max(number1, number2,...) | | | The largest number in the list of arguments. Number is 1–14 numbers for which the maximum value is to be found. Related function: min |
| min(number1, number2,...) | | | The smallest number in the list of arguments. Number is 1–14 numbers for which the minimum value is to be found. Related function: max |
| average(number1, number2,...) | | | The average (mean) of all numbers in the list of arguments. The returned value is the number(s), or quantities, added together and their total then divided by the number of quantities. Related function: sum |
|             |                       | gcd(number1, number2, …) | The greatest common divisor of a group of numbers. |
|             |                       | lcm(number1, number2, …) | The least common multiple of a group of numbers. |
|             |                       | median(number1, number2, ...) | The median (middle number) of a group of numbers. |
| exp(number) |                       | | e raised to the power of number. The constant e equals 2.71828182845904, the base of the natural logarithm. Number is the exponent applied to the base e. |
|             |                       | LOGx(number, base) | The natural logarithm of a number with specified base. Number is the positive real number for which the logarithm is calculated. Related function: Power |
| ln(number)  |                       | | The natural logarithm (base e). Number is the positive real number for which the logarithm is calculated. Related function: exp |
| log(number) |                       | | The base 10 logarithm. Number is the positive real number for which the logarithm is calculated. Related function: ln |
|             |                       | Power(number, power) | Raises a number to the given power. The function works like an exponent in a standard math equation. |
| sqrt(number)| SQRT (number)         | | A positive square root. Number is the number for which the square root is calculated. |
|             |                       | sqrtpi(number) | The square root of (number * pi). |
|             |                       | sumsq(number1, number2, …) | The sum of the squares of the arguments. |
| cos(number) | COS (radians)         | | The cosine of a given angle. Number is the angle in radians for which the cosine is calculated. Related function: acos |
| sin(number) | SIN (radians)         | | The sine of a given angle. Number is the angle in radians for which the sine is calculated. Related function: asin |
| tan(number) |                       | | The tangent of the given angle. Number is the angle in radians for which the tangent is calculated. Related function: atan |
| acos(number)|                       | | The arccosine of a number. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 to pi. Number is the cosine of the angle, and must be from -1 to 1. Related function: cos |
| asin(number)|                       | | The arcsine of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, use the rad2deg function (or multiply the result by 180/pi). Number is the sine of the angle and must be from -1 to 1. Related function: sin |
| atan(number)|                       | | The arctangent of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, use the rad2deg function (or multiply the result by 180/pi). Number is the tangent of the angle and must be from -1 to 1. Related function: tan |
|             |                       | Ceiling(number, [significance]) | The nearest integer not less than the given value. The optional significance is used as a multiple when rounding. |
|             |                       | FloorNum(number, [significance]) | The nearest integer not greater than the given value. The optional significance is used as a multiple when rounding. |
|             |                       | Truncate(number, [num digits]) | A number truncated to the specified number of decimal places. |
| round(number)|                      | | Rounds the specified number to the nearest whole number. Related function: int |
| rounddown(number, digits)|          | | Rounds the specified number down to the specified number of decimal digits. Related functions: round, roundup |
| roundup(number, digits)|            | | Rounds the specified number up to the specified number of decimal digits. Related functions: round, rounddown |
| int(number) | INT (number)          | | Rounds a number down to the nearest integer. Number is the real number to be changed to an integer. Related functions: round, rounddown |
| deg2rad(number)|                    | | Converts a number from degrees to radians. Number is the value in degrees to be converted to radians. |
| rad2deg(number)|                    | | Converts a number from radians to degrees. Number is the value in radians to be converted to degrees. |
|             |                       | Rand() | A number between 0 and 1, including 0 but not including 1. |
|             |                       | RandBetween(number, number) | A number between bottom and top, including bottom but not including top. |
| sum(number1, number2,...)|          | | The sum of all numbers in the list of arguments. Number is 1–14 numbers for which the sum is calculated. Related function: Average |

### Text functions

| Existing WS | Existing Data Manager | New WS | Category and description |
|-------------|-----------------------|--------|--------------------------|
|             | FIND (subtext, text)  | Find(subtext, text, [case]) | The lowest index in the (text) where substring (subtext) is found. If the optional argument (case) is set to true, case-sensitive search is performed. Index of -1 if (subtext) is not found. |
|             |                       | FindPattern(pattern, text, [case]) | The lowest index in the (text) where the regular expression provided in (pattern) is found. If the optional argument (case) is set to true, case-sensitive search is performed. Index of -1 if (subtext) is not found. Regular expression is a sequence of characters that specifies a search pattern. |
|             |                       | isalnum(text) | True if all characters in the string are alphanumeric and there is at least one character, false otherwise. |
|             |                       | isalpha(text) | True if all characters in the string are alphabetic and there is at least one character, false otherwise. |
|             |                       | isdigit(text) | True if all characters in the string are digits and there is at least one character, false otherwise. |
|             |                       | islower(text) | True if all cased characters in the string are lowercase and there is at least one cased character, false otherwise. |
|             |                       | isspace(text) | True if there are only whitespace characters in the string and there is at least one character, false otherwise. |
|             |                       | istitle(text) | True if the string is a titlecased string and there is at least one character, for example uppercase characters may only follow uncased characters and lowercase characters only cased ones. False otherwise. |
|             |                       | isupper(text) | True if all cased characters in the string are uppercase and there is at least one cased character, false otherwise. |
|             |                       | TextJoin(delimiter, text1, text2, …) | The string which is the concatenation of the strings in the sequence seq. The separator between elements is the string providing this method. |
|             | MAKELOWER (string)    | Lower(text) | A copy of the string converted to lowercase. |
|             | TRIMLEFT (string)     | TrimLeft(text, [chars]) | A copy of the string with leading characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed. |
|             | REPLACE (string1, string2, string3) | Replace(string1, string2, string3, [count]) | Return a copy of the string with all occurrences of substring old replaced by new. If the optional argument count is given, only the first count occurrences are replaced. |
|             | TRIMRIGHT (string)    | TrimRight(text, [chars]) | Return a copy of the string with trailing characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed. |
| Substring(text/function, delimiter, index) | | | Splits a single string into an array of strings using a delimiter, and outputs each string at the specified index. |
|             |                       | Trim(text, [chars]) | A copy of the string with the leading and trailing characters removed. The chars argument is a string specifying the set of characters to be removed. If omitted or None, whitespaces will be removed. |
|             |                       | Proper(text) | A titlecased version of the string: words start with uppercase characters, all remaining cased characters are lowercase. |
|             | MAKEUPPER (string)    | Upper(text) | A copy of the string converted to uppercase. |
|             | LEN (string)          | Len(text) | The number of characters in the (text) string. |
|             | INSERT (string1, index, string2) | Insert(text, index, textToInsert) | A copy of (text) with (textToInsert) inserted at given index. |
|             | LEFT (text, count)    | Left(text, count) | The leftmost characters from the (text) value. |
|             | RIGHT (text, count)   | Right(text, count) | The rightmost characters from the (text) value. |
|             | MID (text, index, count) | Mid(text, index, count) | The specific number of characters from the (text) string starting at the position you specify. |
|             | DELETE (string, index, count) | Delete(text, index, count) | A copy of the string with removed (count) characters from (index) position. |
| concat(text1, text2, text3) | + | | Joins several text strings into one text string. |
|             |                       | Char(number) | The character for the Unicode code points in the number or a text representation (U+1234). |
|             |                       | Code(text) | The Unicode code point for the first character in the text. |
|             |                       | Quote(text) | A copy of the text enclosed in quotation marks. |
|             |                       | Rept(text, num) | Repeats text a given number of times. |
|             |                       | txt(val, format code1, [format code2, [...]]) | Converts a numeric value from document units to the specified units and returns a string representation using the options to control formatting. More information is available in the example. |
| value(text) | REAL (number)         | | Converts a text string that represents a number to a number. |
|             |                       | Fixed(num, [decimals]) | Formats a number as text with a fixed number of decimals. |
|             |                       | JustNum(num, width) | The numeric string left filled with zeros in a string of given width. The original string is returned if width is less than len(s). |

### Logical functions

| Existing WS | Existing Data Manager | New WS | Category and description |
|-------------|-----------------------|--------|--------------------------|
| if ((logical_test), value_if_true, value_if_false) | IF (logical_expression, value_expression1, value_expression2) | | Use value_if_true if logical_test is true, value_if_false if logical_test is false. Use this function to conduct conditional tests on values and formulas and to branch based on the results of that test. The outcome of the test determines the value returned by the If function. The logical_test can be any value or expression that can be evaluated to true or false. Up to seven If statements can be nested as value_if_true, value_if_false arguments. Boolean statements within an if statement must be in parentheses. Text within an if statement should be enclosed within quotation marks. |
|             | SELECT1 (number_expression, value_expression1, value_expression2, …, value_expressionN) | Switch(number, value1, value2, ..., value_no_match) | Use value1, or value2, or value3, etc depending on the (number). When no value is available, then use value_no_match. |
|             | SELECT2 (logical_expression1, value_expression1, logical_expression2, value_expression2, …, logical_expressionN, value_expressionN) | IFS((logic1), value1, (logic2), value2, ..., (logicN), valueN) | Returns one of several possible results based on a series of tests. |
|             |                       | Exact(value1, value2) | True when the two values are exactly the same. It will perform a case-sensitive comparison if the values are strings. |
|             | ... ELSE ... ELSE ... | FirstNonEmpty(value1, value2, value3, ...) | Use value1 if not empty, otherwise use value2 if not empty, otherwise use value3 if not empty, etc. Will result in N/A if none match. |
|             |                       | IfNA(value, value_when_na) | Use value_when_na when value N/A, otherwise it will use the value itself. |
|             |                       | IsNA(value) | True when the value is N/A. |

### General functions

| Existing WS | Existing Data Manager | New WS | Category and description |
|-------------|-----------------------|--------|--------------------------|
| DatabasebyScript(scriptName, param1, param2,...) | | | Use this function to create database rows based on the specified script. This function is similar to Database, but it uses a script instead of criteria to determine the list of objects for the database. The order of objects in the database can be defined in the script. The script can be a VectorScript or Python script. Optional parameters for the script can be specified after the script name. An optional parameter before the script name specifies the script’s folder path within the Vectorworks installation. For a list of folder path values, see the developer-oriented documentation here (internet access required): developer.vectorworks.net/index.php/VS:GetFolderPath To input the DatabasebyScript formula, use the Edit Database Formula command. Related functions: Database, RunScript |
| RunScript(scriptName, param1, param2,...) | | | Runs the specified VectorScript or Python script, passing the parameters that follow the script name to the script. An optional parameter before the script name specifies the script’s folder path within the Vectorworks installation. For a list of folder path values, see the developer-oriented documentation here (internet access required): developer.vectorworks.net/index.php/VS:GetFolderPath |
| FormatField(format_name, format_field) | | | The default value of a record format field for all objects that meet the specified criteria with the specified record format. |
| MaterialProperty(materialName, propertyName) | | | The named property for the object’s named material. |

### Lookup functions

| Existing WS | Existing Data Manager | New WS | Category and description |
|-------------|-----------------------|--------|--------------------------|
|             |                       | VLOOKUP (value, [use_pattern], result_col_index, not_found_value, table) | Find a value in the table range, looking at the first column, and returning the value at the result_col_index of that row. |
|             |                       | XLOOKUP (value, [use_pattern], not_found_value, table_lookup, table_result) | Find a value in the table_lookup range, and return the value from the table_result range at the found row, first column. |

### Criteria functions

The following criteria functions were added as Quantity Take Off functions, to allow more standardized data access:

* Angle(criteria, [option1, [option2], ...])
* Count(criteria, [option1, [option2], ...])
* Length(criteria, [option1, [option2], ...])
* Perim(criteria, [option1, [option2], ...])
* Width(criteria, [option1, [option2], ...])
* Height(criteria, [option1, [option2], ...])
* Depth(criteria, [option1, [option2], ...])
* Weight(criteria, [option1, [option2], ...])
* Area(criteria, [option1, [option2], ...])
* SurfaceArea(criteria, [option1, [option2], ...])
* ProjectedArea(criteria, [option1, [option2], ...])
* FootPrintArea(criteria, [option1, [option2], ...])
* CrossSectionArea(criteria, [option1, [option2], ...])
* SpecialArea(criteria, [option1, [option2], ...])
* Volume(criteria, [option1, [option2], ...])
* ObjData(criteria, [option1, [option2], ...])

[[Category:Worksheets]]
