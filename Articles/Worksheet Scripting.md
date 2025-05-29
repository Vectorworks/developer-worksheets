Vectorworks Worksheet are very powerful feature to report any data from the Vectorworks drawing. However, sometimes there are limits which can be overcome by creating a script (a.k.a. code) that solves the problem. Note, scripting is very powerful, but it requires deeper understanding of the Vectorworks data model. Also scripting would add to the complexity of the Worksheet affecting the performance of the worksheet refresh.

Some of the limitations that often need scripting are:
* The data is not readily available but needs to be calculated;
* The value needs to be calculated after summarize or sum of the columns;

# General

The Worksheet scripting can be used via two ways:
* Script that generates the contents of a cell - function [RunScript](../Worksheet%20Functions/Vectorworks%202025%20US.md#runscript-scriptPath----functionName--) and [RunScriptEdit](../Worksheet%20Functions/Vectorworks%202025%20US.md#runscriptedit-scriptPath----functionName--);
* Script that generates the rows of a "Database" row - function [DatabaseByScript](../Worksheet%20Functions/Vectorworks%202025%20US.md#databasebyscript--scriptPath---scriptName-----params----)

The scripts can be located in the current drawing, then they need to be referenced by name. Vectorworks will find them regardless in what folder they are located in the resource manager.

```python
=RunScript('MyScript')
	# execute the script named “MyScript,” found in the current document, regardless of folder structure
```

Or scripts can be executed from the folder structure of Vectorworks.

```python
=RunScript(120, 'Landmark Schedules/SaveLandscapeAreaBeforePlants.py')
	# the first parameter is standard folder identifier
	# the second paramer is relative path to the file containing the script to be executed
```

Note: The available folder identifies can be found in [the scripting help here](https://github.com/Vectorworks/developer-scripting/blob/750939f77fe0bf9d1f3fa762b74dfe47b7cacff2/Function%20Reference/Functions/BuildResourceList.md).

# How it works

Generally, the idea is that Vectorworks will execute the script, pass in parameters, and the script will output the data to be used as cell value or as rows.

Anytime, the additional parameters of the Worksheet function will be passed along to the script. This way you can setup multi functional scripts that can be used in different situations.

## Cell Scripts

A script can be used in a cell formula along side any other functions. Essentially the function __RunScript__ can be used with in a formula to execute a script and produce a value. __RunScriptEdit__ can be used as a single function on a cell, then the script will be execute to get the cell value, but also when a cell value is changed by the user, it will be executed to push the value back into the drawing.

Note, these can be used on any cell, including Database row cells, then the script will be executed for each row independently for the object that represents the row.

### RunScript

For a cell with formula:

```python
=RunScript('MyScript', 1, 2, 'hello')
	# execute the script named “MyScript,” found in the current document, regardless of folder structure
	# pass in the parameters to the script
```

Whenever the cell value is being calculated, the __RunScript__ function will execute the script (from the current file or external, [see above](#general)) and the parameters will be passed along to the script, alongside the handle of the object that corresponds of the row, if this is a database row.

Here is an example of the script. The main points are that the script reads the input, calculates something, and provides one output:

```python
h = vs.WSScript_GetObject()
prm0 = vs.WSScript_GetPrmInt(0)
prm1 = vs.WSScript_GetPrmReal(1)
prm2 = vs.WSScript_GetPrmStr(2)

result = f"{prm2}: {prm0}:{prm1} of {repr(h)}"

vs.WSScript_SetResStr(result)
```

The script will read the input parameters, produce result, and return it back to the cell.

Access the inputs of the script. Note, the type of the parameter is important to call the correct function:

* [WSScript_GetObject() -> HANDLE](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_GetObject.md) - return the handle of the object for this row. Applicable only when executed on a database row cell.
* [WSScript_GetPrmInt(paramIndex) -> INTEGER](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_GetPrmInt.md) - return the integer value of the parameter by index.
* [WSScript_GetPrmReal(paramIndex) -> REAL](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_GetPrmReal.md) - return the real value of the parameter by index.
* [WSScript_GetPrmStr(paramIndex) -> STRING](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_GetPrmStr.md) - return the string value of the parameter by index.


Provide output of the script. Only one of these should be used at the end of the script. Note the type determines the type of the cell value:

* [WSScript_SetResStr(value)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_SetResStr.md) - return a string value
* [WSScript_SetResReal(value)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_SetResReal.md) - return a real value
* [WSScript_SetResInt(value)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_SetResInt.md) - return an integer value
* [WSScript_SetResImage(handle)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_SetResImage.md) - return a handle to an image to be used in the cell. This handle must already exist in the drawing, typically it's a handle to an image inside the object (handle) of this row, i.e. the one being proceeed.

### RunScriptEdit

For a cell with formula:

```python
=RunScriptEdit('MyScript', 1, 2, 'hello')
	# execute the script named “MyScript,” found in the current document, regardless of folder structure
	# pass in the parameters to the script
```

This function will enable the cell for editing. Essentially the script would be identical, only it can be also executed when the cell value changes. You can use [WSScript_GetEdit() -> isEdit, newValue](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_GetEdit.md) to check why the script is being executed.

```python
prm0 = vs.WSScript_GetPrmInt(0)
prm1 = vs.WSScript_GetPrmReal(1)
prm2 = vs.WSScript_GetPrmStr(2)

# check why the script is executed
# and get the new value if the cell is being edited
isEdit, newValue = vs.WSScript_GetEdit()
if not isEdit:
	# we are reading information to determine the cell value
	h = vs.WSScript_GetObject()
	result = f"{prm2}: {prm0}:{prm1} of {repr(h)}"

	vs.WSScript_SetResStr(result)
else:
	# the cell is being edited
	# loop all objects that might be under this cell, this is when a column is summarized
	# which produces several objects/handles for a single row, here we list them all to push the new value
	# this is important as the new value needs to be provided when determining the cell value in this script
	i = 0
	while True:
		ok, h = vs.WSScript_GetEditObj( i )
		if not ok:
			break;
			
		vs.AlrtDialog( f"change the value of object {repr(h)} to '{newValue}'" )
		i += 1
		
	# indicate correct edit completed
	# return 0 would indicate failure and the value will be reverted in the cell
	# return 1 would cause this script to be executed again, to determine the new value of the cell
	# NOTE: This example will always revert because we don't really read or change actual data
	#       i.e. the read here always returns a fixed value
	vs.WSScript_SetResInt( 1 )
```

__Note:__ This example will not actually work, becaue the read always returns the same value, so the write doesn't really do anything, even though an OK is returned.


## Database Row Scripts

The use case for this function is when a Criteria is not enough to determine the sub-rows of a database row. Typically, when you make a row database (by rightclick on the row), you will provide a criteria that will list objects. Each object will represent a sub-row. With this script you can manually specify the list of handles that represent the sub-rows.

This formula must be used on a database row. So:
+ right-click on a row, and run "Database" menu command
+ just lick ok in the dialog
+ right-click again on the same row, and run "Edit Database Formula" menu command.
+ now you can specify the row formula in the formula bar

```python
=DataBaseByScript('MyRowsScript', 1, 2, 'hello')
	# execute the script named “MyRowsScript,” found in the current document, regardless of folder structure
	# pass in the parameters to the script
```
The idea is similar only this time the script is expected to provide a list of handles via the functions:
* [WSScript_AddHandle(handle)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_AddHandle.md) - provide a handle for a row
* [WSScript_AddHandleId(handle, id)](https://github.com/Vectorworks/developer-scripting/blob/main/Function%20Reference/Functions/WSScript_AddHandleId.md) - provide a handle for a row identifying it, so sorting would keep the rows with the same id together

```python
prm0 = vs.WSScript_GetPrmInt(0)
prm1 = vs.WSScript_GetPrmReal(1)
prm2 = vs.WSScript_GetPrmStr(2)

arrObject = []
def collectAllObj(h):
    arrObject.append(h)
   
vs.ForEachObject(collectAllObj, "(L='Design Layer-1')")

for h in arrObject:
	vs.WSScript_AddHandle(h)
```

This script uses a criteria to list objects via a callback, collect them and report them back, so Vectorworks will create database rows for each object. Note, the handle that is provided will be used by all cell functions on this row, as if it was produced by the normal cirteria. So this example is not really different from a regular criteria, but it would allow logic to control the list.

# Useful Code Snippets

## Provide plant style images by plant objects

```python
# Cell Formula
#
# Given plant object from a Landscape Area
# Extracts the image of the plant from the Landscape Area object
#
# Example: =RUNSCRIPT('MyScript')
#
imgObj = vs.Handle()

h = vs.WSScript_GetObject()
if h != vs.Handle():
	# get the name of the symbol associated with this plant
	objName = vs.GetRField( h, 'Plant Record', 'Plantlist Name' )
	hDef = vs.GetObject( objName )
	if hDef != vs.Handle():
		# provide the parametric as an image to the cell from the style symbol
		if hDef.type == 16:
			imgObj = hDef.first
		else:
			imgObj = hDef

vs.WSScript_SetResImage( imgObj )
```

## List Plants

```python
# Database Row Formula
#
# Run a local python script for the database to save the landscape area before plants.
# The default sequence is to save the plants first and then the landscape area.
# This script will save the landscape area first and then the plants. As a result in the worksheet, the landscape area will be listed before the plants in it.
#
# Example: =DATABASEBYSCRIPT('MyRowsScript')
# Example: =DATABASEBYSCRIPT('MyRowsScript', 1) # list dividers too
#
arrObject = []
def collectAllObj(h):
    arrObject.append(h)

def check_h_is_la(h):
	if ( vs.GetObjectVariableInt(h, 1165) == 191):
		return True
	else:
		return False

# depending on a parameter, it would list divider records or not
listDividers = vs.WSScript_GetPrmInt(0)
if listDividers:
	vs.ForEachObject(collectAllObj, "(((R IN ['Landscape Area']) | (R IN ['Plant Record']) | (R IN ['Divider Record'])) & (NOT (R IN ['Plant'])))")
else:
	vs.ForEachObject(collectAllObj, "(((R IN ['Landscape Area']) | (R IN ['Plant Record'])) & (NOT (R IN ['Plant'])))")

arrPlants = []
id = 1
# traverse the found objects, and report the landscape areas first, and then their plants
# the id will be kept the same for all plants in a landscape area, so they get sorted together, i.e. it would mix the plants between the different Landscape Area objects
for h in arrObject:
	if check_h_is_la(h):
		vs.WSScript_AddHandleId(h, id)
		for plant in arrPlants:
			vs.WSScript_AddHandleId(plant, id)
		arrPlants.clear()
		id += 1
	else:
		arrPlants.append(h)
```

## Extract information from the Landscape Area

This information is stored in complicated format, so we need a script to decode it.
Note: This is for demonstration, Vectorworks already has convenient functions for this.

```python
# Cell Formula
#
# Given plant object from a Landscape Area
# Extracts the percentage of the plant from the Landscape Area object
#
# Example: =RUNSCRIPTEDIT('MyScript')
#
isEdit, newValue = vs.WSScript_GetEdit()
if isEdit == False:
	h = vs.WSScript_GetObject()

	strResult = ''
	hParent = h.parent
	if h != vs.Handle():
		# Get the array of rates from the object
		strRate = vs.GetRField( hParent, 'Landscape Area', 'hiddenPercentage' )
		
		# for some reason '\n' on Japanese mac doesn't match with the strRate delimited when run in WS
		arrRate = strRate.split(bytes([10]).decode())

		strResult = ''

		# Loop to find which rate corresponds to the current data
		i = 0
		hCurrent = hParent.first
		while hCurrent != vs.Handle() and i < len(arrRate):
			if hCurrent.type == 2:
				if h == hCurrent:
					strResult = arrRate[ i ]
					break
				i += 1

			hCurrent = hCurrent.next

	vs.WSScript_SetResStr( strResult )
elif int(newValue) >= 0 and int(newValue) <= 100: # validate the input
	iObj = 0
	while True:
		ok, h = vs.WSScript_GetEditObj( iObj )
		if not ok:
			break;
		
		if vs.SetLAField( h, 0, newValue ):
			vs.WSScript_SetResInt( 1 ) # commit to the new value
		
		iObj += 1
	
```