## Search Criteria Format

### Syntax

Search criteria in scripts are composed of two parts: the **search attribute type specifier** and the **search value**. The search attribute specifier indicates which attribute will be used to filter objects in the document; the search value specifies the value to be found and matched by the search operation. For example, the search criteria term:

```pascal
(C=’Edged’)
```

indicates that a search should be performed for any objects whose class is *Edged*. In the criteria term, the C attribute type indicates that the search should be performed on the class attribute of objects in the document. The search value *Edged* indicates what class will be a match in the search operation.

The general syntax for search criteria terms is:

```pascal
(<search attribute type> = <search value>)
```

Parentheses are traditionally used to enclose and indicate individual search terms; they are not required.

### Multiple Search Terms

Multiple criteria terms may be specified in order to narrow the search operation to a more specific subset of objects.
Multiple search criteria are created using the & operator to chain individual search criteria terms. In the term

```pascal
((L='New Construction') & (C='Phase 1'))
```

two search terms are combined to filter for a specific set of objects, in this case any objects on the layer *New Construction* whose class is *Phase 1*. To narrow the search even further, simply add additional search terms:

```pascal
((L='New Construction') & (C='Phase 1') & (SEL=TRUE))
```

In the example, the selection status attribute type was added, so now only selected objects in the *Phase 1* class on layer *New Construction* will match the search.

### Multiple Search Values

It is also possible to filter for multiple match values using search criteria. Multiple match values use the following syntax:

```pascal
(<attribute type> IN [<search value>,<search value>,...])
```

When a search term is specified in this fashion, objects matching any value in the comma delimited value list will be included in the list of objects matching the search. For example:

```pascal
(R IN ['Part Data','Subassembly Data','Assembly Data'])
```

A search using the above term will match any objects with an attached record matching one of the records in the search list.

## Attribute Types

These standard attribute types are available for use in search terms.

| Attribute | Shortcut | Description | Notes |
|-----------|----------|-------------|-------|
| All objects | (ALL) | This specifier will search for all objects in the document. | |
| Descend into plug‐in objects | (INOBJECT) | This traversal specifier instructs the search to look inside plug-in object containers. | |
| Descend into viewport annotations | (INVIEWPORT) | This traversal specifier instructs the search to look inside viewport annotations. | |
| Do not descend into referenced design layer viewports | (NOTINREFDLVP) | This traversal specifier instructs the search to ignore the content of referenced design layer viewports. | |
| Do not descend into non-referenced design layer viewports | (NOTINDLVP) | This traversal specifier instructs the search to ignore the content of non-referenced design layer viewports. | |
| Attached Record | (R) | The record attribute specifier will search for objects that have the indicated record attached. The record attribute specifier requires the use of the multiple criteria format to specify the record name. For example, to search for objects having the Part Data record attached, the search term would be: ```pascal (R IN ['Part Data']) ``` The record name must be a literal *STRING* value. | |
| Class | (C) | The class attribute type will search for objects assigned to the specified class. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Layer | (L) | The layer attribute type will search for objects on the specified layer. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Object Type | (T) | The object type attribute specifier will search for objects that match the specified object type. The search value must be one of the predefined object type selectors (see table at the end of this section for a complete listing). | |
| Story | (STO) | (Design Series required) The story attribute specifier will search for objects on the specified layer. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Object Name | (N) | The object name attribute specifier will search for the object which is assigned the specified object name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Symbol Name | (S) | The symbol name attribute specifier will search for symbol instances based on the specified symbol name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Fill Background | (FB) | The fill background attribute type will search for objects that have the specified fill background. The search value should be a standard Vectorworks color index value (which can be obtained with [RGBToColorIndex](VS:RGBToColorIndex)). | |
| Fill Foreground | (FF) | The fill foreground attribute type will search for objects that have the specified fill foreground. The search value should be a standard Vectorworks color index value (which can be obtained with [RGBToColorIndex](VS:RGBToColorIndex)). | |
| Fill Pattern | (FP) | The fill pattern attribute type will search for objects that have the specified fill pattern. The search value should be the standard Vectorworks fill pattern selector value (in a range of 0 – 71). | |
| Gradient Fill | (GFI) | The gradient fill attribute specifier will search for objects that have the gradient fill with the specified name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Hatch Fill | (HFI) | The hatch fill attribute specifier will search for objects that have the hatch fill with the specified name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Image Fill | (IFI) | The image fill attribute specifier will search for objects that have the image fill with the specified name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Tile Fill | (TFI) | The tile fill attribute specifier will search for objects that have the tile fill with the specified name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Texture | (TX) | The texture attribute specifier will search for objects that have the texture with the specified name. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Pen Background | (PB) | The pen background attribute specifier will search for objects that have the specified pen background. The search value should be a standard Vectorworks color index value (which can be obtained with [RGBToColorIndex](VS:RGBToColorIndex)). | |
| Pen Foreground | (PF) | The pen foreground attribute specifier will search for objects that have the specified pen foreground. The search value should be a standard Vectorworks color index value (which can be obtained with [RGBToColorIndex](VS:RGBToColorIndex)). | |
| Pen Pattern | (PP) | The pen pattern attribute specifier will search for objects that have the indicated pen pattern. The search value should be a standard pen pattern selector value. | |
| Line Style | (LS) | The line style attribute specifier will search for objects that have the indicated pen style (solid, pattern, line type, etc.). The search value should be a standard line style selector value. | |
| Line Type | (LT) | The line type attribute specifier will search for objects that have the indicated line type. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Line Weight | (LW) | The line weight attribute specifier will search for objects that have the indicated line weight. The search value should be an *INTEGER* value specifying the line weight. | |
| Opacity | (OPA) | The opacity specifier will search for objects with the specified opacity percentage (in a range of 0 to 100). | |
| Marker Style | (AR) | The marker style attribute specifier will search for objects using the indicated marker style. The search value should be one of the supported marker style flag selector values (see marker styles constants [Function Reference Appendix](VS:Function_Reference_Appendix#appx_i)). | |
| Marker Size | (ASZ) | The marker size attribute specifier will search for objects using a marker of the specified size. The search value is the size of the marker in inches (marker size value in inches). | |
| Material | (MAT) | The material attribute specifier will search for objects that have the specified material. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Sketch Style | (SST) | The sketch style attribute specifier will search for objects that use the specified sketch style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Wall Style | (WST) | (Design Series required) The wall style attribute specifier will search for walls that have the specified wall style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Slab Style | (SLST) | (Design Series required) The slab style attribute specifier will search for slabs that have the specified slab style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Roof Style | (RST) | (Design Series required) The roof style attribute specifier will search for roofs/roof faces that have the specified roof style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Component | (COMP) | The component attribute specifier will search for walls, roofs, slabs, hardscapes that have components with the specified name. The search value should be a *STRING* value (literals and variables are supported). | |
| Plug-in Style | (PST) | The plug-in style attribute specifier will search for plug-in objects that have the specified style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Font | (FOT) | The font attribute specifier will search for objects that have text with the specified font. The search value should be a *STRING* value (literals and variables are supported). | |
| Font Size | (FSZ) | The font size attribute specifier will search for objects that have text with the specified font size. The search value is the font size value in points (font size in points). | |
| Text Style | (TSTY) | The text style attribute specifier will search for objects that have text with the specified text style. The search value should be a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |
| Selection | (SEL) | The selection specifier will search for selected or deselected objects. The search value is a *BOOLEAN* value indicating the selection state (*TRUE* for selected, *FALSE* for deselected). | |
| Visible Selection | (VSEL) | The visible selection specifier will search for selected objects that are visibly selected in the document and indicated on the object info palette. The search value is a *BOOLEAN* value indicating the selection state (*TRUE* for selected, *FALSE* for deselected). | |
| Visibility | (V) | The visibility attribute specifier will search for objects based on their visibility status. The search value is a *BOOLEAN* value indicating the visibility state (*TRUE* for visible, *FALSE* for invisible). | |
| Plane | (PLA) | The plane specifier will search for objects that belong to the specified plane. The search value should be a *STRING* value indicating the name of the plane (literals and variables are supported). | |
| Flipped Status | (ISFLIPPED) | The flipped status specifier will search for objects based on their flipped state. | |
| Location | (LOC) | The location specifier will search for objects that are within the boundary of the specified named object. The search value is a *STRING* value which is up to 64 characters in length (literals and variables are supported). | |

## Specialized Searches

In addition to the standard attribute types available for use in search terms, scripts also provide specialized search attribute types for additional flexibility in searching a file.

### Record Field Values

Record fields may be searched for specific matching values using a specialized attribute type to query the field value.
The syntax for querying record fields is:

```pascal
(<record name>.<field name>[< = |<> |> |>= |< |<= ><search value>])
```

The record and field names are STRING values and should be enclosed in single quotes. Any one of the optional comparison operators can be used to focus the search on a specific subset of items which have the attached record. For example:

```pascal
('Assembly Data'.'Base Cost' < 250.00)
```

will search for any items with the attached record whose base cost is less than 250.00 dollars.

[CMP] undocumented but very useful feature: wildcards ? and * can be used in search values. e.g.

```pascal
('Device'.'Name' = 'VJF_*')
```

will match all fields whose values begin with VJF_. My tests show that you can have multiple instances of * and ? in a search term and they behave quite intelligently. So you can search for strings containing a sub string for example.

### Search Symbol Instances (INSYMBOL)

The *INSYMBOL* attribute specifier will cause the search to enter any symbols encountered and perform a search on the symbols’ definition. For example, suppose you are laying out a large office and wish to count the total number of desk components that will need to be purchased. Your document contains a mixture of individual desk and desk return symbols, plus symbols which are comprised of a combination of the two desk components. A search using the term

```pascal
(S IN ['3660 Desk','3660 LH Return'])
```

will return an inaccurate count, as it does not include instances of those symbols which are themselves inside another symbol. Adding the INSYMBOL type specifier to the term:

```pascal
((S IN ['3660 Desk','LH Return']) & (INSYMBOL))
```

will force the search to enter any symbols encountered and detect any nested instances of the symbols in the search term.

### Search Plug-in Objects (INOBJECT)

The *INOBJECT* specifier causes the search to enter plug‐in objects and also evaluate their component objects.
Normally, components of plug‐in objects and symbols are ignored by search criteria. The INSYMBOL and INOBJECT specifiers affect the traversal of the drawing and cause more objects to be evaluated against the search criteria.

For example, to count the number of rectangles in the drawing, including rectangles that are inside symbols and plug‐in objects, use the following:

```pascal
COUNT(INSYMBOL & INOBJECT & (T=RECT))
```

### Search Viewport Instances (INVIEWPORT)

The *INVIEWPORT* attribute specifier will cause the search to enter the annotation space of any viewports encountered and perform a search. For example, you may wish to search for drawing labels, or perhaps dimensions, within the annotation space. A search using the term

```pascal
(S IN [T=DIMENSION])
```

will return an inaccurate count, as it does not include viewport instances. Adding the *INVIEWPORT* type specifier to the term:

```pascal
(S IN (INVIEWPORT)&(T=DIMENSION))
```

will force the search to detect any dimensions in the annotation space of viewports.

In a similar way, you can exclude non‐referenced design layer viewports with the specifier *NOTINDLVP* and exclude referenced design layer viewports with *NOTINREFDLVP*.

```pascal
(S IN (NOTINDLVP)&(PON='Door'))
```
finds all doors that are not in non‐referenced design layer viewports.

```pascal
(S IN (NOTINREFDLVP)&(PON='Door'))
```
finds all doors that are not in referenced design layer viewports.

### Location (LOC)

The *LOC* specifier finds objects that are located within the bounds of a named object, like a fence.

### Symbol Flip Status (ISFLIPPED)

The *ISFLIPPED* attribute specifier will check the flipped status of symbols or other objects. For example, to perform a count of all flipped instances of a particular symbol:

```pascal
((S=’3680 Door’) & (ISFLIPPED))
```

will find only those instances of the symbol which have been flipped. The *ISFLIPPED* specifier is useful for determining orientation of objects for editing or related tasks.

### Project Sharing criteria

Working Files may be searched for object ownership or modification status.

#### Ownership (OWN)

The owner criteria will test the userid that has checked out an object. The special string '#' will match objects checked out to the current user in the current file. 
```pascal
(OWN=’rberge’)
(OWN='#')
```

The special string '*' will match objects checked out by anyone and exclude objects available to check out. An empty string can be used to match objects available to check out. 
```pascal
(OWN=’*’)
(OWN=’’)
```

#### Modification status (MODIFIED)

The modification status will match objects that have been modified in the current working file and will be submitted in the next commit. 
```pascal
(MODIFIED=TRUE) | (MODIFIED=FALSE)
```

#### Container modification status (MOCMODIFIED)

The container modification status will match objects that have been modified directly. It will also match containers like layers or groups that have contents that have been modified. 
```pascal
(MOCMODIFIED=TRUE)
```

### All Objects (ALL)

Using the *ALL* attribute type specifier will select all the objects in the document.

## Search Criteria Tables

The script criteria attribute specifiers are listed in the following table.

| Attribute Type | Type Selector | Example |
|----------------|---------------|---------|
| All objects | ALL | n/a |
| Descend into plug‐in objects | INOBJECT | (T=RECT) & INOBJECT |
| Descend into symbols | INSYMBOL | & (INSYMBOL) |
| Descend into viewport annotations | INVIEWPORT | & (INVIEWPORT) |
| Do not descend into non‐referenced design layer viewports | NOTINDLVP | & (NOTINDLVP) |
| Do not descend into referenced design layer viewports | NOTINREFDLVP | & (NOTINREFDLVP) |
| Attached Record | R | R IN ['Part Data'] |
| Class | C | C='Millwork' |
| Layer | L | L='First Floor' |
| Object Type | T | Type selector (see table) |
| Story | STO | STO = 'Second Floor' |
| Object Name | N | N = 'Name-1' |
| Symbol Name | S | S = 'My Symbol' |
| Fill Background | FB | Color index value |
| Fill Foreground | FF | Color index value |
| Fill Pattern | FP | FP=4 |
| Gradient Fill | GFI | GFI='Fall' |
| Hatch Fill | HFI | HFI='Stipple Dark' |
| Image Fill | IFI | IFI='Stones' |
| Tile Fill | TFI | TFI='Tile‐1' |
| Texture | TX | TX='Glass' |
| Pen Background | PB | Color index value |
| Pen Foreground | PF | Color index value |
| Pen Pattern | PP | PP=3 |
| Line Style | LS | INTEGER value |
| Line Type | LT | LT='Line Type‐1' |
| Line Weight | LW | INTEGER value |
| Marker | AR | INTEGER selector value |
| Marker Size | ASZ | ASZ=0.125 |
| Opacity | OPA | OPA=70 |
| Material | MAT | MAT='Wood' |
| Sketch Style | SST | SST='Rough' |
| Wall Style | WST | WST='Wallstyle‐1' |
| Slab Style | SLST | SLST='SlabStyle‐1' |
| Roof Style | RST | RST='RoofStyle‐1' |
| Component | COMP | COMP='Brick Veneer' |
| Plug-in Style | PST | PST='WindowStyle‐1' |
| Font | FOT | FOT='Arial' |
| Font Size | FSZ | FSZ=10 |
| Text Style | TSTY | TSTY='Text Style‐1' |
| Location is contained within boundary of a named object | LOC | (LOC='MyRoom') |
| Plane | PLA | PLA='Layer Plane' |
| Selected status | SEL | BOOLEAN value |
| Visible Selected status | VSEL | BOOLEAN value |
| Visibility status | V | BOOLEAN value |
| Flipped status | ISFLIPPED | n/a |
| Owner in Project Sharing | OWN | String for userid, #, *, or empty string. |
| Modification status in Project Sharing | MODIFIED | BOOLEAN value |
| Object or contents modification status in Project Sharing | MOCMODIFIED | BOOLEAN value |

| Object Type | Type Selector | Example |
|-------------|---------------|---------|
| 2D Locus | LOCUS | T=LOCUS |
| 3D Locus | LOCUS3D | T=LOCUS3D |
| 3D Polygon | POLY3D | T=POLY3D |
| Arc | ARC | T=ARC |
| Bitmap Image | BITMAP | T=BITMAP |
| Component Index<br>(objects that have components;<br>available only in IFC mapping formulas) | INDEX | T=INDEX |
| Cone, Sphere, Pyramid | SOLID | T=SOLID |
| CSG Solid | CSGSOLID | T=CSGSOLID |
| Dimension | DIMENSION | T=DIMENSION |
| Extrude | XTRD | T=XTRD |
| Freehand | FHAND | T=FHAND |
| Group | GROUP | T=GROUP |
| Layer Link | LAYERLINK | T=LAYERLINK |
| Line | LINE | T=LINE |
| Mesh | MESH | T=MESH |
| Multiple Extrude | MXTRD | T=MXTRD |
| Oval | OVAL | T=OVAL |
| PICT Image | PICT | T=PICT |
| Plug-in Object | PLUGINOBJECT | T=PLUGINOBJECT |
| Polygon | POLY | T=POLY |
| Polyline | POLYLINE | T=POLYLINE |
| Quarter Arc | QARC | T=QARC |
| Rectangle | RECT | T=RECT |
| Roof | ROOF | T=ROOF |
| Roof Element | ROOFELEMENT | T=ROOFELEMENT |
| Roof Face, Floor, Column | SLAB | T=SLAB |
| Round Wall | ROUNDWALL | T=ROUNDWALL |
| Rounded Rectangle | RRECT | T=RRECT |
| Sub Type<br>(all objects except plug-in objects; <br>available sub types are listed in<br>[Search Criteria Sub Types](VS:Search_Criteria#Search Criteria Sub Types) ) | ST | ST=CONE |
| Sub Type (plug-in object names only) | PON | PON=“DOOR” |
| Sweep | SWEEP | T=SWEEP |
| Symbol | SYMBOL | T=SYMBOL |
| Text | TEXT | T=TEXT |
| Wall | WALL | T=WALL |
| Worksheet | SPRDSHEET | T=SPRDSHEET |

### Search Criteria Sub Types

When using the ST object type selector for objects other than plug‐in objects, the following sub types are available.

| Object Sub Type | Object Type | Sub Type Selector | Example |
|----------------|-------------|-------------------|---------|
| Directional Light | Light | DIRLIGHT | ST=DIRLIGHT |
| Spot Light | Light | SPOTLIGHT | ST=SPOTLIGHT |
| Point Light | Light | POINTLIGHT | ST=POINTLIGHT |
| Custom Light | Light | CUSTLIGHT | ST=CUSTLIGHT |
| Area Light | Light | AREALIGHT | ST=AREALIGHT |
| Line Light | Light | LINELIGHT | ST=LINELIGHT |
| Regular Viewport | Viewport | REGVIEWPORT | ST=REGVIEWPORT |
| Section Viewport | Viewport | SECTVIEWPORT | ST=SECTVIEWPORT |
| Floor | Floor | FLOOR | ST=FLOOR |
| Roof Face | Roof face | ROOFFACE | ST=ROOFFACE |
| Pillar | Pillar | PILLAR | ST=PILLAR |
| Cone | Solid | CONE | ST=CONE |
| Sphere | Solid | SPHERE | ST=SPHERE |
| Hemisphere | Solid | HEMISPHERE | ST=HEMISPHERE |
| Circle | Arc | CIRCLE | ST=CIRCLE |
| Opened Arc | Arc | OPENEDARC | ST=OPENEDARC |
| Solid Subtraction | CSG Solid | CSGSUBTR | ST=CSGSUBTR |
| Solid Addition | CSG Solid | CSGADD | ST=CSGADD |
| Solid Intersection | CSG Solid | CSGINTER | ST=CSGINTER |
| Solid Section | CSG Solid | CSGSECT | ST=CSGSECT |
| Shell | CSG Solid | CSGSHELL | ST=CSGSHELL |
| Chamfer | CSG Solid | CSGCHAMFER | ST=CSGCHAMFER |
| Fillet | CSG Solid | CSGFILLET | ST=CSGFILLET |
| Control Point Based NURBS Surface | NURBS Surface | NURBSSURFCTRLP | ST=NURBSSURFCTRLP |
| Interpolated NURBS Surface | NURBS Surface | NURBSSURFINTERP | ST=NURBSSURFINTERP |
