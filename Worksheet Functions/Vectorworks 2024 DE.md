Tabellenfunktionen

Based on Vectorworks 2024 Update 7 (773964)

== Allgemein ==

{| border=0
| colspan="3" | <big>RunScript(ScriptName [; Parameter])</big>
|-
| style="width: 10pt;" |  || valign="top" | Führt ein Script mit Namen ScriptName und optionalen Parametern (Funktionen) aus und gibt das Ergebnis zurück.<p>(Schweiz: RunScript(ScriptName [, Parameter]))
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RunScript('My Script') executes the VectorScript script named “My Script” and returns a value for each object in the database

Spreadsheet cell:
=RunScript(2, 'ScriptFile.py', 2, 1) executes the Python script “ScriptFile.py” in the Vectorworks Plug-Ins folder, passing the parameters “2” and “1,” and returns a value
</pre>
|-
| colspan="3" | <big>Feldformat(Datenbank; Feldname)</big>
|-
|  || valign="top" | Gibt den Wert des angegebenen Felds der Datenbank zurück.<p>(Schweiz: Feldformat(Datenbank, Feldname))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=FormatField(‘Door’, ‘Width’), where “Door” is the name of a record format, returns the default value for the “Width” field.

</pre>
|-
| colspan="3" | <big>ScriptbearbAusführen(ScriptName [; Parameter])</big>
|-
|  || valign="top" | Führt ein Script aus und gibt das Ergebnis zurück. Die Zellen lassen sich bearbeiten und das Script wird danach erneut ausgeführt.<p>(Schweiz: ScriptbearbAusführen(ScriptName [, Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Datenbank(Filter)</big>
|-
|  || valign="top" | Erzeugt eine Datenbank von Objekten, auf die mit dem Filter verwiesen wird.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=DATABASE((L='Floor-1')) creates a worksheet database of all objects on layer “Floor-1.”
</pre>
|-
| colspan="3" | <big>DatenbankDurchScript([scriptPfad]; scriptName; ...params...)</big>
|-
|  || valign="top" | Führt ein Skript aus, um eine Datenbank mit Objekten zu erstellen.<p>(Schweiz: DatenbankDurchScript([scriptPfad], scriptName, ...params...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=DataBaseByScript('MyScript.py', 2, 1) creates a worksheet database by executing the script named “My Script.py,” passing the parameters “2” and “1” to the script.
</pre>
|}

== Funktionen für Adapter ==

{| border=0
| colspan="3" | <big>Objektdaten('eval adapter plug device'; '<Datenbank>'; '<Feldname>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Parameter oder den Datenbankeintrag von Steckvorrichtung des Adapters.<p>(Schweiz: Objektdaten('eval adapter plug device', '<Datenbank>', '<Feldname>'))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('eval adapter plug socket'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag von der Buchse des Adapters.<p>(Schweiz: Objektdaten('eval adapter plug socket', '<Datenbank>', '<Feldname>'))
|-
|  || 
|}

== Funktionen für Anschluss ==

{| border=0
| colspan="3" | <big>Objektdaten('eval socket circuits'; '<Datenbank>'; '<Feldname>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Parameter oder den Datenbankeintrag von den mit dem Anschluss verbundenen Schaltkreisen.<p>(Schweiz: Objektdaten('eval socket circuits', '<Datenbank>', '<Feldname>'))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('eval socket device'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Gerät, das mit dem Anschluss verbunden ist.<p>(Schweiz: Objektdaten('eval socket device', '<Datenbank>', '<Feldname>'))
|-
|  || 
|}

== Funktionen für Belag/Weg ==

{| border=0
| colspan="3" | <big>Tiefe()</big>
|-
| style="width: 10pt;" |  || valign="top" | Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>ProjizierteFläche()</big>
|-
|  || valign="top" | Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
|  || valign="top" | Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.
|-
|  || 
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche()</big>
|-
|  || valign="top" | Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|}

== Funktionen für Boden/Decke ==

{| border=0
| colspan="3" | <big>Gewicht('Brutto'; [optionale Parameter])</big>
|-
| style="width: 10pt;" |  || valign="top" | Gewicht von Boden/Decke oder Boden/Deckenschicht in kg. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Gewicht(Filter, 'Brutto', [optionale Parameter]))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Gewicht('Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Gewicht von Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Gewicht(Gewicht, 'Netto', [optionale Parameter])
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schalldämmung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Brennbare Konstruktion')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Brandmauer')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
|  || valign="top" | Der Name der Wand-, Boden/Decke- oder Dachschicht.<p>(Schweiz: Objektdaten(Filter, 'Schichtname'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-Code')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-System')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Beschreibung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Aussenseite')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Feuerwiderstand')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Funktion')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Lambda')</big>
|-
|  || valign="top" | Der Lambdawert des Objekt.<p>(Schweiz: Objektdaten(Filter, 'Lambda'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Tragend')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Hersteller')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Bezeichnung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Modell')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('R-Wert')</big>
|-
|  || valign="top" | Der R-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'R-Wert'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('U-Wert')</big>
|-
|  || valign="top" | Der U-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'U-Wert'))
|-
|  || 
|-
| colspan="3" | <big>Breite()</big>
|-
|  || valign="top" | Die Dicke einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Modifikatoren'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Anzahl der Modifikatoren in einem Boden oder Decke oder einer Wand. Bei einer Wand sind das Vorsprung und Nische, für Boden/Decke sind Volumenaddition und -subtraktion, sowie Entwässerung.

'Modifikatortyp=...': Es werden nur Modifikatoren mit den angegebenen Typen berücksichtigt. Mehrere Typen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Modifikatortyp ausschließen': Es werden die Modifikatoren mit dem angegebenen Typen nicht gezählt.<p>(Schweiz: Anzahl(Filter, 'Modifikatoren', [optionale Parameter])
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Öffnungen'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen in den Schichten gezählt, die dem Filter entsprechen.

'Schichtmaterial=...': Es werden nur Bauteile mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (für Wände), oben, unten (für Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Öffnungskriterien: Es werden nur Öffnungen gezählt, die alle angegebenen Kriterien erfüllen. Wenn für die Werte keine Einheiten angegeben sind, wird von Millimetern, Quadratmillimetern oder Kubikmillimetern ausgegangen. Für Böden/Decken stehen folgende Kriterien zur Verfügung: minimale Öffnungsfläche oben, maximale Öffnungsfläche oben, minimale Öffnungsfläche unten, maximale Öffnungsfläche unten, minimales Öffnungsvolumen, maximales Öffnungsvolumen, minimaler Öffnungsumfang oben, maximaler Öffnungsumfang oben, minimaler Öffnungsumfang unten, maximaler Öffnungsumfang unten. Für Wände stehen die folgenden Kriterien zur Verfügung: Min Öffnungsfläche links, Max Öffnungsfläche links, Min Öffnungsfläche rechts, Max Öffnungsfläche rechts, Min Öffnungsfläche dem Kern zugewandt, Max Öffnungsfläche dem Kern zugewandt, Min Öffnungsfläche dem Kern abgewandt, Max Öffnungsfläche dem Kern abgewandt, Min Öffnungsfläche Mitte, Max Öffnungsfläche Mitte, Min Öffnungsfläche der Grundfläche, Max Öffnungsfläche der Grundfläche, Min Öffnungslänge der Grundfläche links, Max Öffnungslänge der Grundfläche links, Min Öffnungslänge der Grundfläche rechts, Max Öffnungslänge der Grundfläche rechts, Min Öffnungslänge der Grundfläche dem Kern zugewandt, Max Öffnungslänge der Grundfläche dem Kern zugewandt, Min Öffnungslänge der Grundfläche dem Kern abgewandt, Max. Öffnungslänge der Grundfläche dem Kern abgewandt, Min Öffnungslänge der Grundfläche Mitte, Max Öffnungslänge der Grundfläche Mitte, Min Öffnungsvolumen, Max Öffnungsvolumen. 

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden. Gilt nur für Wände.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Gilt nur für Wände.

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -länge anhand der Filterkriterien gemessen werden. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Anzahl(Filter, 'Öffnungen', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Count('openings') returns the number of openings in the wall, wall component, slab or slab component.

=Count('openings', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters.

=Count('openings', 'min opening area top=0.5 sq m', 'max opening area top=1 sq m') returns the number of openings with an area between 0.5 and 1 square meter on the top of the slab or slab component.

=Count('openings', 'min opening area bottom=1 sq ft', 'max opening volume=10 cu in') returns the number of openings with an area of at least 1 square foot on the bottom of the slab or slab component and a volume of at most 10 cubic inches.

=Count('openings', 'opening type=Window') returns the number of openings created by "Window" plug-in objects.

=Count('openings', 'opening type=Window;WinDoor 6.0') returns the number of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Count('openings', 'component=core', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters in the wall core component.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.</pre>
|-
| colspan="3" | <big>Winkel('Energos')</big>
|-
|  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
|  || 
|-
| colspan="3" | <big>DickeDachflStützeBoden()</big>
|-
|  || valign="top" | Dicke von Dachflächen, Profilstützen und Böden.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SlabThickness returns the thickness for each object in the database

Spreadsheet cell:
=SlabThickness(PON=slab) returns the combined thickness of all slab objects in the drawing
</pre>
|-
| colspan="3" | <big>BodenDeckenstilName()</big>
|-
|  || valign="top" | Name eines Boden/Deckenstils.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SlabStyleName returns the name of the slab style for each slab object in the database

Spreadsheet cell:
=SlabStyleName(n='slab-1') returns the name of the slab style for the object named “slab-1”
</pre>
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Berechnet die Fläche einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Umfang('Unten'; [optionale Parameter])</big>
|-
|  || valign="top" | Umfang der Unterseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Umfang(Filter, 'unten', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Umfang('Öffnungen unten'; [optionale Parameter])</big>
|-
|  || valign="top" | Summe der Umfänge der einzelnen Öffnungen in der Unterseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsumfang=...' / 'Max Öffnungsumfang=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsumfang liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.<p>(Schweiz: Umfang(Filter, 'Öffnungen unten', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Umfang('Öffnungen oben'; [optionale Parameter])</big>
|-
|  || valign="top" | Summe der Umfänge der einzelnen Öffnungen in der Oberseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsumfang=...' / 'Max Öffnungsumfang=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsumfang liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.<p>(Schweiz: Umfang(Filter, 'Öffnungen oben', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Umfang('Oben'; [optionale Parameter])</big>
|-
|  || valign="top" | Umfang der Oberseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Umfang(Filter, 'oben', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Unten Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Unten Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('bottom gross') returns the gross area of the bottom face of the slab or slab component.

=SurfaceArea('bottom gross', 'component=top') returns the gross area of the bottom face of the top component of the slab.</pre>
|-
| colspan="3" | <big>Oberfläche('Unten Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.<p>(Schweiz: Oberfläche(Filter, 'Unten Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('bottom net') returns the area of the bottom face of the slab or slab component.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('bottom net', 'component=top') returns the area of the bottom face of the top component of the slab.</pre>
|-
| colspan="3" | <big>Oberfläche('Öffnungen unten'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Öffnungen auf der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen unten', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('openings bottom') returns the total area of openings on the bottom face of the slab or slab component.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings bottom', 'component=top') returns the total area of openings on the bottom face of the top component of the slab.</pre>
|-
| colspan="3" | <big>Oberfläche('Öffnungen oben'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Öffnungen auf der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen in Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen oben', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('openings top') returns the total area of openings on the top face of the slab or slab component.

=SurfaceArea('openings top', 'min opening area=0.5 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings top', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings top', 'component=bottom') returns the total area of openings on the top face of the bottom component of the slab.</pre>
|-
| colspan="3" | <big>Oberfläche('Oben Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Gibt die Fläche der Obererseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Oben Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('top gross') returns the gross area of the top face of the slab or slab component.

=SurfaceArea('top gross', 'component=bottom') returns the gross area of the top face of the bottom component of the slab.</pre>
|-
| colspan="3" | <big>Oberfläche('Oben Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.<p>(Schweiz: Oberfläche(Filter, 'Oben Netto', [optionale Parameter])
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('top net') returns the area of the top face of the slab or slab component.

=SurfaceArea('top net', 'min opening area=0.5 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('top net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('top net', 'component=bottom') returns the area of the top face of the bottom component of the slab.</pre>
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Volumen(Filter, 'Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.</pre>
|-
| colspan="3" | <big>Volumen('Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.<p>(Schweiz: Volumen(Filter, 'Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.</pre>
|-
| colspan="3" | <big>Volumen('Öffnungen'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen der Öffnungen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.<p>(Schweiz: Volumen(Filter, 'Öffnungen', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.</pre>
|}

== Funktionen für Dach ==

{| border=0
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
| style="width: 10pt;" |  || valign="top" | Der Name der Wand-, Boden/Decke- oder Dachschicht.<p>(Schweiz: Objektdaten(Filter, 'Schichtname'))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-Code')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-System')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Beschreibung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Aussenseite')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Feuerwiderstand')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Funktion')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Lambda')</big>
|-
|  || valign="top" | Der Lambdawert des Objekt.<p>(Schweiz: Objektdaten(Filter, 'Lambda'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Hersteller')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Bezeichnung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Modell')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('R-Wert')</big>
|-
|  || valign="top" | Der R-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'R-Wert'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('U-Wert')</big>
|-
|  || valign="top" | Der U-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'U-Wert'))
|-
|  || 
|-
| colspan="3" | <big>DachflKompl()</big>
|-
|  || valign="top" | Gesamtfläche von Dächern.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RoofArea_Total returns the total area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Total(st=roofface) returns the combined total area of all roof face objects in the drawing</pre>
|-
| colspan="3" | <big>DachflOhneÜberst()</big>
|-
|  || valign="top" | Fläche von Dächern ohne die Fläche des Überstands.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RoofArea_Heated returns the heated area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Heated (st=roofface) returns the combined heated area of all roof face objects in the drawing
</pre>
|-
| colspan="3" | <big>DachflKomplProj()</big>
|-
|  || valign="top" | Gesamtfläche von Dächern auf die aktive Konstruktionsebene projiziert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RoofArea_TotalProj returns the total area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_Totalproj(t=roof) returns the combined total area of all roof objects in the drawing, as projected to the layer plane
</pre>
|-
| colspan="3" | <big>DachflOhneÜberstProj()</big>
|-
|  || valign="top" | Fläche von Dächern ohne die Fläche des Überstands auf die aktive Konstruktionsebene projiziert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RoofArea_HeatedProj returns the heated area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_HeatedProj (t=roof) returns the combined heated area of all roof objects in the drawing, as projected to the layer plane
</pre>
|-
| colspan="3" | <big>Dachstilname()</big>
|-
|  || valign="top" | Name des Dachstils.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RoofStyleName returns the roof style name for each roof object in the database

Spreadsheet cell:
=RoofStyleName(n='roof-1') returns the roof style name for the object named “roof-1”
</pre>
|}

== Funktionen für Door ==

{| border=0
| colspan="3" | <big>Winkel('Energos')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Volume(criteria, 'door jamb')</big>
|-
|  || valign="top" | Returns the volume the jamb.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('door jamb')     Returns the volume the jamb.

Spreadsheet cell:
=VOLUME(SEL, 'door jamb')    Returns the volume the jamb.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'door sashes')</big>
|-
|  || valign="top" | Returns the total volume all sashes (including sidelight and transom sashes).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('door sashes')     Returns the total volume all sashes (including sidelight and transom sashes).

Spreadsheet cell:
=VOLUME(SEL, 'door sashes')    Returns the total volume all sashes (including sidelight and transom sashes).
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing all')</big>
|-
|  || valign="top" | Returns the total volume of all glazing.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing for leaves')</big>
|-
|  || valign="top" | Returns the volume of glazing for all leaves (including vision panels).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing for leaves')     Returns the volume of glazing for all leaves (including vision panels).

Spreadsheet cell:
=VOLUME(SEL, 'glazing for leaves')    Returns the volume of glazing for all leaves (including vision panels).
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing for sidelights')</big>
|-
|  || valign="top" | Returns the volume of glazing for all sidelights.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing for sidelights')     Returns the volume of glazing for all sidelights.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sidelights')    Returns the volume of glazing for all sidelights.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing for transom')</big>
|-
|  || valign="top" | Returns the volume of glazing for the transom.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'leaf panels')</big>
|-
|  || valign="top" | Returns the total volume of the leaf panels.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('leaf panels')     Returns the total volume of the leaf panels.

Spreadsheet cell:
=VOLUME(SEL, 'leaf panels')    Returns the total volume of the leaf panels.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'leaf stiles and rails')</big>
|-
|  || valign="top" | Returns the total volume of the leaf rails, and stiles.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('leaf stiles and rails')     Returns the total volume of the leaf rails and stiles.

Spreadsheet cell:
=VOLUME(SEL, 'leaf stiles and rails')    Returns the total volume of the leaf rails and stiles.
</pre>
|}

== Funktionen für Fenster ==

{| border=0
| colspan="3" | <big>Tiefe('Sill')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt die Tiefe der äußeren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmenaußenkante.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Tiefe('Stool')</big>
|-
|  || valign="top" | Gibt die Tiefe der inneren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmeninnenkante.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('CornerWindowType')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, ob das Fenster ein ein- oder beidseitiges Eckfenster ist.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('FallProtection')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Fenster eine Absturzsicherung (Geländer) hat, andernfalls falsch. Ob das Fenster ein Geländer hat, kann im Reiter 'Geländer' des Fensterdialogs festgelegt werden.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsArchitecturalversion')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt ein Komplettes Fenster ist, andernfalls falsch. Komplette Fenster sind Bestandteil des Architekturmoduls und benötigen eine entsprechende Seriennummer, um die volle Funktionalität freizuschalten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsBasicversion')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt ein Einfaches Fenster ist, andernfalls falsch. Einfache Fenster sind Bestandteil aller Module, haben aber nur wenige Optionen und Einstellmöglichkeiten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsInsertedInWall')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt in eine Wand eingefügt ist, andernfalls falsch.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Material'; <Fensterbestandteil>)</big>
|-
|  || valign="top" | Gibt den Namen des Objektmaterials eines Bestandteils des Fensters zurück.

Aufruf: =Objektdaten('Material';<Fensterbestandteil>)

Liste der unterstützten Fensterbestandteile:

  Fensterbank aussen
  Fensterbank innen
  Fensterladen
  Geländeroberkante
  Geländerpfosten
  Geländerrahmen
  Geländerstäbe
  Geländerunterkante
  Glas
  Griff
  Rahmen
  Rollladen
  Rollladenkastenabschluss
  Rollladenkastensymbol
  Rollladenkasten

Beispiel: =Objektdaten('Material';'Rollladen')

Groß-/Kleinschreibung spielt keine Rolle.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeHeightAutoDimension')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeSelectedHeight')</big>
|-
|  || valign="top" | Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Höhe an der Innenseite oder an der Außenseite definiert wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeSelectedWidth')</big>
|-
|  || valign="top" | Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeWidthAutoDimension')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung bemaßt wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('UseWallClosure')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt die Laibungseinstellungen der Wand verwendet, andernfalls falsch.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('WindowHandleType'; <Nr. des Flügels>)</big>
|-
|  || valign="top" | Gibt den Typ des Fenstergriffs eines Fensterflügels zurück.

Aufruf: =Objektdaten('WindowHandleType'[;<Nummer des Flügels>])
Beispiel: =Objektdaten('WindowHandleType';'2')

Die Flügel werden von innen aus gesehen von links nach rechts nummeriert.
Die Flügelnummer braucht nicht angegeben zu werden, wenn alle Flügel den gleichen Grifftyp haben.
Bei unterschiedlichen Grifftypen und fehlender Flügelnummer wird 'Verschiedene' zurückgegeben.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ZPositionDefinedBy')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, ob die Z-Position des Fensters über die Brüstungs- oder die Sturzhöhe festgelegt ist und ob für diese Höhen die innere oder die äußere Wandseite maßgeblich ist.
|-
|  || 
|-
| colspan="3" | <big>Breite()</big>
|-
|  || valign="top" | Gibt diejenige Breite des Fensters zurück, die im Reiter 'Fenstergröße' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.
|-
|  || 
|-
| colspan="3" | <big>Breite('BottomFrame')</big>
|-
|  || valign="top" | Gibt die Breite des unteren Fensterrahmens zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FinishedWidthInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Breite Innen zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FinishedWidthOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Breite Außen zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('Frame')</big>
|-
|  || valign="top" | Gibt die Breite des Fensterrahmens zurück. Dieser Wert entspricht dem IFC-Wert 'Lining Thickness'. Bei asymmetrischen Fenstern wird die Breite des linken Rahmens zurückgegeben.
|-
|  || 
|-
| colspan="3" | <big>Breite('FrameClearWidth')</big>
|-
|  || valign="top" | Gibt das Rahmenlichtmaß Breite zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FrameTotalWidth')</big>
|-
|  || valign="top" | Gibt das Rahmenaußenmaß Breite zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('LeftFrame')</big>
|-
|  || valign="top" | Gibt die Breite des von der rechten Wandseite (innen) aus gesehen linken Fensterrahmens zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('RightFrame')</big>
|-
|  || valign="top" | Gibt die Breite des von der rechten Wandseite (innen) aus gesehen rechten Fensterrahmens zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('Sill')</big>
|-
|  || valign="top" | Gibt die Breite der äußeren Fensterbank (gemessen längs der Wand) zurück, sofern eine solche existiert.
|-
|  || 
|-
| colspan="3" | <big>Breite('Stool')</big>
|-
|  || valign="top" | Gibt die Breite der inneren Fensterbank (gemessen längs der Wand) zurück, sofern eine solche existiert.
|-
|  || 
|-
| colspan="3" | <big>Breite('TopFrame')</big>
|-
|  || valign="top" | Gibt die Breite des oberen Fensterrahmens zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('UnfinishedWidth')</big>
|-
|  || valign="top" | Gibt das Rohmaß Breite zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Größe' des Fensterdialogs.
|-
|  || 
|-
| colspan="3" | <big>Höhe()</big>
|-
|  || valign="top" | Gibt diejenige Höhe des Fensters zurück, die im Reiter 'Fenstergröße' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Höhe ist, die in Bemaßungen oder Beschriftungen angezeigt wird.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightObjectInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Fenster innen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightObjectOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Fenster außen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightWallInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Wand innen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightWallOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Wand außen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FrameTotalHeight')</big>
|-
|  || valign="top" | Gibt das Rahmenaußenmaß Höhe zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('HeadHeightDefinedBySettings')</big>
|-
|  || valign="top" | Gibt die Sturzhöhe gemäß Einstellungen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('HeadHeightFromOrigin')</big>
|-
|  || valign="top" | Gibt die Sturzhöhe ab Nullpunkt zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('RoughSizeBottomFromOrigin')</big>
|-
|  || valign="top" | Gibt den Abstand zwischen Unterkante Rohmaß und Nullpunkt zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('RoughSizeTopFromOrigin')</big>
|-
|  || valign="top" | Gibt den Abstand zwischen Oberkante Rohmaß und Nullpunkt zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('SillHeightDefinedBySettings')</big>
|-
|  || valign="top" | Gibt die Brüstungshöhe gemäß Einstellungen zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('SillHeightFromOrigin')</big>
|-
|  || valign="top" | Gibt die Brüstungshöhe ab Nullpunkt zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Stool')</big>
|-
|  || valign="top" | Gibt die Höhe der inneren Fensterbank zurück, sofern eine solche existiert.
|-
|  || 
|-
| colspan="3" | <big>Höhe('UnfinishedHeight')</big>
|-
|  || valign="top" | Gibt das Rohmaß Höhe zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Größe' des Fensterdialogs.
|-
|  || 
|-
| colspan="3" | <big>Winkel('Energos')</big>
|-
|  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
|  || 
|}

== Funktionen für Flächenpflanzung ==

{| border=0
| colspan="3" | <big>Tiefe()</big>
|-
| style="width: 10pt;" |  || valign="top" | Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>ProjizierteFläche()</big>
|-
|  || valign="top" | Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
|  || valign="top" | Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Trennlinie')</big>
|-
|  || valign="top" | Der Trennlinientext der Pflanzen innerhalb der Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen und Trennlinien von Flächenpflanzungen aufgelistet sind. 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Flächenpflanzung'; <Feld>)</big>
|-
|  || valign="top" | Ermöglicht den Zugriff auf Datenfelder der Flächenpflanzung, sofern der Stil dies zulässt.<p>(Schweiz: Objektdaten('Flächenpflanzung', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Anteil')</big>
|-
|  || valign="top" | Der Anteil einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Plant Record'; <Feld>)</big>
|-
|  || valign="top" | Ermöglicht den Zugriff auf Datenfelder der Pflanzen innerhalb der Flächenpflanzung, sofern der Stil dies zulässt.<p>(Schweiz: Objektdaten('Plant Record', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>ObjektDaten('Dichte')</big>
|-
|  || valign="top" | Die Dichte einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Mengeneinheit')</big>
|-
|  || valign="top" | Die Mengeneinheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Dichte mit Einheit')</big>
|-
|  || valign="top" | Die Dichte mit Einheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind.
|-
|  || 
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche()</big>
|-
|  || valign="top" | Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|}

== Funktionen für Geländemodell ==

{| border=0
| colspan="3" | <big>Tiefe()</big>
|-
| style="width: 10pt;" |  || valign="top" | Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>ProjizierteFläche()</big>
|-
|  || valign="top" | Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
|  || valign="top" | Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.
|-
|  || 
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche()</big>
|-
|  || valign="top" | Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche( 'Ist-Zustand' )</big>
|-
|  || valign="top" | Berechnet die Oberfläche des Ist-Zustands des Geländemodell und dessen Schichten.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SURFACEAREA('Existing')     Returns the existing Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Existing')    Returns the existing Surface Area for the selected Site Model object.
</pre>
|-
| colspan="3" | <big>Oberfläche( 'Soll-Zustand' )</big>
|-
|  || valign="top" | Berechnet die Oberfläche des Soll-Zustands des Geländemodell und dessen Schichten.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SURFACEAREA('Proposed')     Returns the proposed Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Proposed')    Returns the proposed Surface Area for the selected Site Model object.
</pre>
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Ist-Zustand')</big>
|-
|  || valign="top" | Berechnet das Volumen des Ist-Zustands des Geländemodell und dessen Schichten.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('existing')     	Returns the existing volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'existing')    Returns the existing volume for the selected Site Model object.
</pre>
|-
| colspan="3" | <big>Volumen('Soll-Zustand')</big>
|-
|  || valign="top" | Berechnet das Volumen des Soll-Zustands des Geländemodell und dessen Schichten.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('proposed')     	Returns the proposed volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'proposed')    Returns the proposed volume for the selected Site Model object.
</pre>
|}

== Funktionen für Geländer ==

{| border=0
| colspan="3" | <big>Breite()</big>
|-
| style="width: 10pt;" |  || valign="top" | Diese Funktion kann auf folgende Unterobjekte angewandt werden: Rahmen, Platten, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Rahmen: Breite des rechteckigen Rahmens.

Für Platte: Breite der rechteckigen Platte.

:Für Halterung: Breite der Handlaufhalterung (entspricht dem Abstand des Handlaufs ).

Für Pfosten seitliche Montage: Breite Pfosten mit seitlicher Montage (entspricht der Auskragung).
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Breite('Halterungen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Breite der Handlaufhalterungen.
|-
|  || 
|-
| colspan="3" | <big>Breite('Pfosten seitliche Montage')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Breite der Pfosten mit seitlicher Montage.
|-
|  || 
|-
| colspan="3" | <big>Breite('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Breite der Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Breite('Platten/Fertigelemente')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtbreite aller Platten.
|-
|  || 
|-
| colspan="3" | <big>Breite('Profil')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Unterobjekte angewandt werden: Handlauf, Geländer, Pfosten, Rahmen, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Breite des entsprechenden Unterobjekts.
|-
|  || 
|-
| colspan="3" | <big>Höhe()</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Geländer, Handlauf, Rahmen, Platte, Halterung, Pfosten und Pfosten seitliche Montage

BESCHREIBUNG:
Für Geländer-Objekt: Höhe des Geländer-Objekts (Maximalhöhe von Geländer oder Handlauf).

Für Rahmen: Höhe des rechteckigen Rahmens.

Platte: Höhe der rechteckigen Platte.

Für Handlauf: Höhe des Handlaufs.

Für Geländer: Höhe des Geländerhandlaufs.

Für Pfosten seitliche Montage: Höhe des Pfostens.

Für Pfosten: Höhe des Pfostens.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Halterung')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Beschreibung:
Höhe der Handlaufhalterung.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Pfosten seitliche Montage')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Höhe aller Unterobjekte der Pfosten mit seitlicher Montage.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Höhe aller Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Geländer')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Höhe des Geländers.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Handlauf')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Höhe des Handlaufs.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Höhe der Fertigelemente und N/A, wenn gemischte Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Pfosten')</big>
|-
|  || valign="top" | Diese Funktion ist identisch mit Länge('Pfosten').
|-
|  || 
|-
| colspan="3" | <big>Höhe('Profil')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Unterobjekte des Geländer-Objekts angewandt werden: Geländer, Handlauf, Rahmen, vertikale und horizontale Geländerstäbe, Pfosten und Pfosten seitliche Montage.

BESCHREIBUNG:
Höhe des Profils des entsprechenden Unterobjekts.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Ecken')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Geländer und Handlauf

BESCHREIBUNG:
Für Geländer-Objekt: Anzahl der Richtungsänderungen (links, rechts, nach oben, nach unten) im Geländer-Objekt.

Für Geländer:  Anzahl der Richtungsänderungen (links, rechts, nach oben, nach unten) im Geländer.

Für Handlauf: Wenn es keinen Handlauf gibt, dann die Richtungsänderungen (links, rechts, nach oben, nach unten) des Pfadverlaufs des Geländer-Objekts.
|-
|  || 
|-
| colspan="3" | <big>Winkel()</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Unterobjekte angewandt werden:

Vertikale und horizontale Stäbe.

Für vertikale Stäbe: Winkel der vertikalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.

Für horizontale Stäbe: Winkel der horizontalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.
|-
|  || 
|-
| colspan="3" | <big>Winkel('Horizontale Stäbe')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekte: Winkel der horizontalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.
|-
|  || 
|-
| colspan="3" | <big>Winkel('Vertikale Geländerstäbe')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekte: Winkel der vertikalen Stäbe. Wenn in den Einstellungen diagonal ausgerichtet, dann 45°, andernfalls 0°.
|-
|  || 
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Rahmen, Platten, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Für Geländer-Objekt: Gesamtfläche des Geländer-Objekts.

:Für Unterobjekt: Fläche des betreffenden Unterobjekts.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Halterungen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Fläche der Handlaufhalterungen.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Pfosten seitliche Montage')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Fläche der Pfosten mit seitlicher Montage.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtfläche der Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Platten/Fertigelemente')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtfläche der Platten.
|-
|  || 
|-
| colspan="3" | <big>Umfang()</big>
|-
|  || valign="top" | Diese Funktion kann auf das Unterobjekt Rahmen angewandt werden:

BESCHREIBUNG:
Rahme: Umfang des Rahmens.
|-
|  || 
|-
| colspan="3" | <big>Umfang('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekt: Gesamtumfang aller Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Länge()</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Handlauf, Geländer, Rahmen, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Für Geländer-Objekt: Länge des 3D-Pfadverlaufs des Geländers.

Für Handlauf: Länge des 3D-Handlaufs.

Für Geländer: Länge des 3D-Geländers.

Für Rahmen: Breite des Rahmens.

Für vertikale oder horizontale Geländerstäbe: Länge der Stäbe.

Für Halterung: Versatz Geländer + Höhe Halterung.

Für Pfosten seitliche Montage: Höhe Pfosten plus Auskragung.
|-
|  || 
|-
| colspan="3" | <big>Länge('Horizontale Geländerstäbe')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Unterobjekte horizontale Geländerstäbe.
|-
|  || 
|-
| colspan="3" | <big>Länge('Vertikale Geländerstäbe')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Unterobjekte vertikale Geländerstäbe.
|-
|  || 
|-
| colspan="3" | <big>Länge('Halterungen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge der Halterungen.
|-
|  || 
|-
| colspan="3" | <big>Länge('Pfosten seitliche Montage')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge des Pfostens mit seitlicher Montage.
|-
|  || 
|-
| colspan="3" | <big>Länge('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge der Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Länge('Geländer')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Geländer.
|-
|  || 
|-
| colspan="3" | <big>Länge('Handlauf')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Handläufe.
|-
|  || 
|-
| colspan="3" | <big>Länge('Max Befestigungsabstand')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Maximaler Abstand der Pfosten. Wenn keine Pfosten, dann Abstand der Befestigungen.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche()</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Unterobjekte des Geländer-Objekts angewandt werden: Geländer, Handlauf, Pfosten, Rahmen, Platten, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Vollständige Außenfläche des Unterobjekts.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Geländerstäbe horizontal')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller horizontalen Geländerstäbe.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Geländerstäbe vertikal')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller vertikalen Geländerstäbe.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Halterungen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Oberfläche der Geländerhalterungen.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Pfosten seitliche Montage')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Pfosten mit seitlicher Montage.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Rahmen')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Rahmen.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Geländer')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Geländer.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Handlauf')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Handläufe.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtoberfläche aller Fertigelemente.

Unterobjekt Zaunfeld: Oberfläche des Fertigelements und N/A bei gemischten Zaunfeldern.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Pfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Pfosten mit seitlicher Montage.
|-
|  || 
|}

== Funktionen für Geländer/Zaun Classic ==

{| border=0
| colspan="3" | <big>Breite()</big>
|-
| style="width: 10pt;" |  || valign="top" | Breite([optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Wandkonsole, seitliche Konsole, Rahmen und Platte.

OPTIONALER PARAMETER:Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Wandkonsole: Horizontale Abmessung der Wandkonsole des Handlaufs.

Seitliche Konsole: Abmessung der Seitlichen Konsole in horizontaler Richtung.

Rahmen: Breite des rechteckigen Rahmens

Platte: Breite der Platte in Ansicht.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Breite('Profil')</big>
|-
|  || valign="top" | Breite('Profil'; [optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Handlauf oben, Pfosten, Ober- und Untergurt, Stab vertikal und horizontal, Rahmen.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Handlauf oben: Breite des Querschnittprofils des Handlaufs. Für runde und achteckige Profile ist die Breite gleich der Höhe. Für Eigene Profile (2D- Symbol), wird die Bounding Box verwendet, um die Breite zu ermitteln.

Pfosten: Breite des Querprofils des Pfostens.

Ober- und Untergurt: Breite des Querprofils des Gurts.

Stab vertikal und horizontal: Höhe des Profils der vertikalen Stäbe.<p>(Schweiz: Breite('Profil', [optionaler Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Höhe()</big>
|-
|  || valign="top" | Höhe([optionaler Parameter])

Die Funktion kann auf das Geländerobjekt oder einer der folgenden Unterobjekte angewandt werden: Handlauf oben, Wandkonsole, Pfosten, seitliche Konsole, Rahmen, Platte.

OPTIONAL PARAMETER:Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländerobjekt: Oberkante des obersten Unterobjekts (Handlauf falls vorhanden, Rahmen, Füllung oder Obergurt) über dem Boden oder der Treppe. In Vectorworks entspricht der Boden dem Wert 'Höhe Punkt 1' in der Objektinfopalette. Dieser Wert wird in das IFC-Feld Pset_RailingCommon.Height geschrieben.

Handlauf oben: Vertikaler Abstand zwischen Boden oder Treppe (in Vectorworks Höhe Punkt 1) und der Oberkante des Handlaufs.

Wandkonsole: Vertikale Abmessung der Wandkonsole des Handlaufs.

Pfosten: Höhe des Pfosten.

Seitliche Konsole: Abmessung der seitlichen Konsole in vertikaler Richtung.

Rahmen: Höhe des rechteckigen Rahmens.

Panel: Höhe der Platte in Ansicht.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Profil')</big>
|-
|  || valign="top" | Höhe('Profil'; [optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Handlauf oben, Pfosten, Ober- und Untergurt, Stab vertikal  und horizontal, Rahmen.

OPTIONALER PARAMETER:Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Höhe des Querschnittprofils des Handlaufs. Für runde und achteckige Profile ist die Breite gleich der Höhe. Für Eigene Profile (2D- Symbol), wird die Bounding Box verwendet, um die Höhe zu ermitteln.

Ober- und Untergurt: Höhe des Profils des Gurts.

Stab vertikal und horizontal: Höhe des Profils der vertikalen Stäbe.<p>(Schweiz: Höhe('Profil', [optionaler Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Winkel')</big>
|-
|  || valign="top" | Anzahl('Winkel'; [optionaler Parameter])

Die Funktion kann auf das Geländerobjekt und den Handlauf oben angewandt werden.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer: Anzahl der vertikalen Winkel  und horizontalen Ecken im Geländerpfad.

Handlauf oben: Anzahl der Winkelstücke im Handlauf.<p>(Schweiz: Anzahl('Winkel', [optionaler Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Winkel()</big>
|-
|  || valign="top" | Winkel([optionaler Parameter])

Diese Funktion kann mit folgenden Unterobjekte verwendet werden: Stab vertikal and Stab horizontal.

OPTIONALER PARAMETER:
'Unterobjekt=...': Falls angegeben, wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Für Stab vertikal: Winkel der vertikalen Stäbe. Vertikal is 0°.

Für Stab horizontal: Winkel der horizontalen Stäbe. horizontal is 0°.
|-
|  || 
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Fläche([optionaler Parameter])

Die Funktion kann auf das Geländerobjekt und die folgenden Unterobjekte angewandt werden.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer: Geländerfläche als Geländerlänge multipliziert mit Geländerhöhe. Dabei wird die Länge zwischen den beiden Aussenkanten des ersten und letzten Pfostens gemessen oder zwischen den Aussenkanten der Geländerfüllungen. Die Länge des Handlaufs ist dabei irrelevant. Diese Längendefinition unterscheidet sich vom buildingSMART- Standard, der im Datenbankfeld RailingLengthIFC des Geländerobjekts gesichert ist. Die Höhe ist Oberkante des obersten Unterobjekts (Handlauf falls vorhanden, Rahmen, Füllung oder Obergurt) über dem Boden oder der Treppe. In Vectorworks entspricht der Boden dem Wert 'Höhe Punkt 1' in der Objektinfopalette.

Platte: Fläche der Platte (Breite x Höhe).
|-
|  || 
|-
| colspan="3" | <big>Umfang()</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Länge('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Geländerobjekt und die folgenden Unterobjekte angewandt werden: Handlauf oben, Obergurt, Untergurt, Stab vertikal, Stab horizontal, Platte.

OPTIONALE PARAMETER:Unterobjekt=...': Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländerobjekt: Länge des Geländerobjekts zwischen den beiden Aussenkanten des ersten und letzten Pfostens oder zwischen den Aussenkanten der Geländerfüllungen. Die länge des Handlaufs ist dabei irrelevant. Diese Längendefinition unterscheidet sich vom buildingSMART- Standard, welcher im Datenfeld RailingLengthIFC gesichert und in die Felder Qto_RailingBaseQuantities.Length und BaseQuantities.Length geschrieben wird. 

Handlauf oben: Länge des 3D-Pfadobjekts des Handlaufs oben einschließlich der Verlängerungen des Handlaufs oben am Anfang oder Ende des Geländerobjekts.

Ober- und Untergurt: Länge des Gurts.

Stab vertikal und horizontal: Länge des Stabs.

Platte: Derselbe Wert, als wenn die Funktion Breite auf Rahmen angewendet wird.
|-
|  || 
|-
| colspan="3" | <big>Länge('Max')</big>
|-
|  || valign="top" | Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen allen Instanzen eines Unterobjekts an.
Wählbare Unterobjekte sind Wandkonsole, Pfosten und seitliche Konsole.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Wandkonsole: Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen Wandkonsolen an.

Pfosten: Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen Pfosten an.

Seitliche Konsole: Maximaler Abstand zwischen den seitlichen Konsolen, gemessen auf deren Mittelachse.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche()</big>
|-
|  || valign="top" | Oberfläche(Filter; [optionale Parameter])

Die Funktion kann auf das Geländerobjekt und die folgenden Unterobjekte angewandt werden: Handlauf oben, Wandkonsole, Pfosten, seitliche Konsole, Ober- und Untergurt, Stab vertikal und horizontal, Rahmen, Platte.

OPTIONALE PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Handlauf oben: Außenfläche des Handlaufs oben aller Seiten einschließlich der beiden Kappen am Anfang und Ende.

Wandkonsole: Gesamte Außenfläche der Wandkonsole des Handlauf oben.

Pfosten: Gesamte Außenfläche des Pfostens einschließlich der Treppe, Wand oder Handlauf zugewandte Seiten.

Seitliche Konsole: Gesamte Außenfläche des Pfostens der seitliche Konsole einschließlich der Kappenflächen, die an einer Wand, einem Pfosten, einer Treppe oder einem anderen Objekt befestigt sind.

Ober- und Untergurt: Gesamte Oberfläche aller Seiten der Gurte.

Stab vertikal und horizontal: Gesamte Oberfläche aller Seiten der Stäbe.

Rahmen: Gesamte Oberfläche des rechteckigen Rahmens.

Platte: Gesamte Oberfläche aller Seiten der Platte.<p>(Schweiz: Oberfläche(Filter, [optionale Parameter]))
|-
|  || 
|}

== Funktionen für Gerät ==

{| border=0
| colspan="3" | <big>Objektdaten('eval equipment item'; '<Datenbank>'; '<Feldname>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom entsprechenden Equipment-Objekt des Geräts.<p>(Schweiz: Objektdaten('eval equipment item', '<Datenbank>', '<Feldname>'))
|-
| style="width: 10pt;" |  || 
|}

== Funktionen für Hecke ==

{| border=0
| colspan="3" | <big>Objektdaten('Anteil')</big>
|-
| style="width: 10pt;" |  || valign="top" | Der Anteil einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. 
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('Plant Record'; <Feld>)</big>
|-
|  || valign="top" | Ermöglicht den Zugriff auf Datenfelder der Pflanzen innerhalb der Flächenpflanzung, sofern der Stil dies zulässt.<p>(Schweiz: Objektdaten('Plant Record', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>ObjektDaten('Dichte')</big>
|-
|  || valign="top" | Die Dichte einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Mengeneinheit')</big>
|-
|  || valign="top" | Die Mengeneinheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Dichte mit Einheit')</big>
|-
|  || valign="top" | Die Dichte mit Einheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind.
|-
|  || 
|}

== Funktionen für Lichtschacht ==

{| border=0
| colspan="3" | <big>Tiefe('')</big>
|-
| style="width: 10pt;" |  || valign="top" | Tiefe des Gitters/Wanddicke
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Tiefe('Innen')</big>
|-
|  || valign="top" | Innere Tiefe des Lichtschachtkörpers orthogonal zur Gebäudeaußenwand.
|-
|  || 
|-
| colspan="3" | <big>Tiefe('Außen')</big>
|-
|  || valign="top" | Äußere Tiefe des Lichtschachtkörpers orthogonal zur Gebäudeaußenwand.
|-
|  || 
|-
| colspan="3" | <big>FlächeSpezial('')</big>
|-
|  || valign="top" | Oberfläche der Wände und des Bodens auf deren Außenseiten.
|-
|  || 
|-
| colspan="3" | <big>Breite('')</big>
|-
|  || valign="top" | Breite des Gitters.
|-
|  || 
|-
| colspan="3" | <big>Breite('Innen')</big>
|-
|  || valign="top" | Innere Breite des Lichtschachtkörpers parallel zur Gebäudeaußenwand.
|-
|  || 
|-
| colspan="3" | <big>Breite('Außen')</big>
|-
|  || valign="top" | Äußere Breite des Lichtschachtkörpers parallel zur Gebäudeaußenwand.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Innen')</big>
|-
|  || valign="top" | Innere vertikale Höhe des Lichtschachtkörpers.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Außen')</big>
|-
|  || valign="top" | Äußere vertikale Höhe des Lichtschachtkörpers.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('')</big>
|-
|  || valign="top" | Summe aller äußeren Oberflächen des Lichtschachtkörpers.
|-
|  || 
|-
| colspan="3" | <big>Volumen('')</big>
|-
|  || valign="top" | Volumen des Lichtschachtkörpers bestehend aus Lichtschachtboden und -wänden.
|-
|  || 
|}

== Funktionen für Marionette Object ==

{| border=0
| colspan="3" | <big>ObjectData('parameter', '<OIP FieldName>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Get parameter values or attached record fields from Marionette objects.
|-
| style="width: 10pt;" |  || 
|}

== Funktionen für Panel ==

=== Verbinder ===

{| border=0
| colspan="3" | <big>Objektdaten('eval panel connector circuit', '<Datenbank>', '<Feldname>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Eigenschaftswert oder verbundene Datenbank des Schaltkreises, der mit dem Verbinderpanel verbunden ist.
|-
| style="width: 10pt;" |  || 
|}

== Funktionen für Pflanze ==

{| border=0
| colspan="3" | <big>Anzahl('Pflanzaushubschicht')</big>
|-
| style="width: 10pt;" |  || valign="top" | Die Anzahl der Schichten des Pflanzaushubs.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Volumen('Pflanzaushubschicht'; <index>)</big>
|-
|  || valign="top" | Das Volumen der Schicht des Pflanzaushubs, auf die mit <index> verwiesen wird.<p>(Schweiz: Volumen('Pflanzaushubschicht', <index>))
|-
|  || 
|-
| colspan="3" | <big>Pflanzenbild(Index)</big>
|-
|  || valign="top" | Bild des Objekts, auf das mit dem Index verwiesen wird.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=PlantImage(2) displays the image specified for Image Detail in the More Data pane of the plant symbol definition

Spreadsheet cell:
=PlantImage((‘Plant’.’plant ID’=’TaxfR’), 4) displays the image specified for Custom Image in the More Data pane of the plant symbol definition with a plant ID of TaxfR
</pre>
|}

== Funktionen für Pfosten ==

=== Riegel ===

==== Fassade ====

{| border=0
| colspan="3" | <big>FassadePRLänge(Klassenname)</big>
|-
| style="width: 10pt;" |  || valign="top" | Länge aller Pfosten und Riegel einer Fassade, die in der mit Klassenname bezeichneten Klasse liegen.
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CurtWallFrameLength('') returns the combined length of the curtain wall frames for each curtain wall in the database

Spreadsheet cell:
=CurtWallFrameLength(t=wall, '') returns the combined length of the curtain wall frames for all curtain walls in the drawing
</pre>
|-
| colspan="3" | <big>FassadeFüllFlächeBrt(Klassenname)</big>
|-
|  || valign="top" | Bruttofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CurtWallPnlAreaGross('') returns the combined gross area of the curtain wall panels for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaGross(t=wall, '') returns the combined gross area of the curtain wall panels for all curtain walls in the drawing
</pre>
|-
| colspan="3" | <big>FassadeFüllFlächeNet(Klassenname)</big>
|-
|  || valign="top" | Nettofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CurtWallPnlAreaNet ('Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaNet(t=wall, 'Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for all curtain walls in the drawing
</pre>
|}

== Funktionen für Profillinie ==

{| border=0
| colspan="3" | <big>Länge()</big>
|-
| style="width: 10pt;" |  || valign="top" | 
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Länge('Profil')</big>
|-
|  || valign="top" | Gesamtlänge eines Profils.
|-
|  || 
|-
| colspan="3" | <big>Länge('Profil links')</big>
|-
|  || valign="top" | Länge der linken Seite eines Profils.
|-
|  || 
|-
| colspan="3" | <big>Länge('Profil Stationierung')</big>
|-
|  || valign="top" | Die Kilometrierung bzw. Stationierung eines Profils.
|-
|  || 
|-
| colspan="3" | <big>Länge('Profil rechts')</big>
|-
|  || valign="top" | Länge der rechten Seite eines Profils.
|-
|  || 
|}

== Funktionen für Querprofile ==

{| border=0
| colspan="3" | <big>Objektdaten('Profillinienname')</big>
|-
| style="width: 10pt;" |  || valign="top" | Name der Achse.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('Index')</big>
|-
|  || valign="top" | Index des Profils.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Stationierung')</big>
|-
|  || valign="top" | Die Texbasierte Stationierung eines Profils.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Anmerkung')</big>
|-
|  || valign="top" | Zusätzliche Anmerkungen.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Profile')</big>
|-
|  || valign="top" | Anzahl der Querprofile.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Auftrag')</big>
|-
|  || valign="top" | Auftragsfläche des Profils.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Abtrag')</big>
|-
|  || valign="top" | Abtragsfläche des Profils.
|-
|  || 
|-
| colspan="3" | <big>Länge('Abstand')</big>
|-
|  || valign="top" | Abstand zur Stationierung des vorherigen Profils.
|-
|  || 
|-
| colspan="3" | <big>Länge('Stationierung')</big>
|-
|  || valign="top" | Stationierung eines Profils.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Masse Auftrag')</big>
|-
|  || valign="top" | Masse Auftragsfläche des Profils.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Masse Abtrag')</big>
|-
|  || valign="top" | Masse Abtragsfläche des Profils.
|-
|  || 
|}

== Funktionen für Rampe ==

{| border=0
| colspan="3" | <big>Tiefe('')</big>
|-
| style="width: 10pt;" |  || valign="top" | Rampenlaufkörper 1: Breite des Rampenlaufkörpers quer zur Laufrichtung.

Rampenpodestkörper: Breite des Rampenpodestkörpers quer zur Laufrichtung

Rampenbelag: Breite des Belags. Bei unterschiedlicher Breite von Lauf 1, Podest und Lauf 2 wird kein Wert ausgegeben. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>ProjizierteFläche('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Projizierte Grundfläche des Rampenlaufkörpers 

Rampenpodestkörper: Projizierte Grundfläche des Rampenpodestkörpers.

|-
|  || 
|-
| colspan="3" | <big>Grundfläche('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Projizierte Grundfläche des Rampenlaufkörpers 

Rampenpodestkörper: Projizierte Grundfläche des Rampenpodestkörpers.
|-
|  || 
|-
| colspan="3" | <big>Breite('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Radabweiser links/rechts: Breite des Radabweisers bezogen auf dessen vertikalen Querschnitt.

Rampenlaufkörper 1: Breite des Rampenlaufkörpers quer zur Laufrichtung.

Rampenpodestkörper: Breite des Rampenpodestkörpers quer zur Laufrichtung

Rampenbelag: Breite des Belags. Bei unterschiedlicher Breite von Lauf 1, Podest und Lauf 2 wird kein Wert ausgegeben. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben. 
|-
|  || 
|-
| colspan="3" | <big>Profil('Profil')</big>
|-
|  || valign="top" | Durchmesser des Handlaufs des Geländers.
|-
|  || 
|-
| colspan="3" | <big>Höhe('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Oberkante des Geländers über dem Boden oder der Treppe.Dieser Wert wird ins IFC-Feld  des Sekundär-Objekts IfcRailing Pset_RailingCommon.Height geschrieben. 

Gehweg links/rechts: Höhe des Gehwegs bezogen auf dessen vertikalen Querschnitt. 

Radabweiser links/rechts: Höhe des Radabweisers bezogen auf dessen vertikalen Querschnitt.

Rampenbelag: Dicke des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.
|-
|  || 
|-
| colspan="3" | <big>Winkel('')</big>
|-
|  || valign="top" | Gesamtsteigung über alle Läufe und Podeste in Grad.
|-
|  || 
|-
| colspan="3" | <big>Fläche('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Geländerlänge multipliziert mit Geländerhöhe. Geländerlänge beginnt und endet mit der Geländerfüllung (Rahmen/Panel). Die Geländerhöhe ist der vertikale Abstand zwischen Höhenpunkt 1 oder 2 und der Oberkante des höchsten Unterobjekts (oberer Handlauf, Rahmen, Panel oder Querprofil oben).

Rampenlaufkörper 1: Bruttofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Bruttofläche des Rampenpodestkörpers.

Rampenbelag: Bruttofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Brutto')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Bruttofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Bruttofläche des Rampenpodestkörpers.

Rampenbelag: Bruttofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.
|-
|  || 
|-
| colspan="3" | <big>Fläche('Netto')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Nettofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Nettofläche des Rampenpodestkörpers.

Rampenbelag: Nettofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.
|-
|  || 
|-
| colspan="3" | <big>Länge('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Gesamtlänge des 3D- Pfadkörpers des Geländers. Dieser Wert wird in die IFC-Felder  des Sekundär-Objekts IfcRailing Qto_RailingBaseQuantities.Length und BaseQuantities.Length geschrieben.

Gehweg links/rechts: Länge des Gehwegs, gemessen auf dessen mittleren Lauflinie.

Radabweiser links/rechts: Länge des Radabweisers entlang dessen Mittelachse.

Rampenlaufkörper 1: Lauflänge des Rampenkörpers.

Rampenpodestkörper: Lauflänge des Rampenpodestkörpers.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Gehweg links/rechts: Abgewickelte (= tatsächliche) und exponierte Hüllfläche des Gehwegs. Die Kontaktflächen zwischen den Unterobjekten (z.B. zwischen Gehweg und Rampenkörper oder zwischen Radabweiser und Gehweg) und die vertikale Fläche, die Teil der Rampenseitenfläche außen ist, gehören nicht dazu. Praktischer Anwendungsfall: ein Anstrich. Oberflächen von Belag und Gehweg können über die Unterobjekte separat ermittelt werden.

Radabweiser links/rechts: Abgewickelte (= tatsächliche) und exponierte Hüllfläche des Radabweisers. Die Kontaktflächen zwischen den Unterobjekten (z.B. zwischen Gehweg und Radabweiser) und die vertikale Fläche, die Teil der Rampenseitenfläche außen ist, gehören nicht dazu. Praktischer Anwendungsfall: ein Anstrich. Oberflächen von Belag und Gehweg können über die Unterobjekte separat ermittelt werden.
|-
|  || 
|-
| colspan="3" | <big>Volumen('')</big>
|-
|  || valign="top" | Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Gehweg links/rechts: Bruttovolumen des Gehwegs (Summe der Volumina des Gehwegs auf Lauf 1, Podest, Lauf 2)

Radabweiser links/rechts: Bruttovolumen des Radabweisers (Summe der Volumina des Radabweisers auf Lauf 1, Podest, Lauf 2)

Rampenlaufkörper 1: Volumen des Rampenlaufkörpers

Rampenpodestkörper: Volumen des Rampenpodestkörpers.

Rampenbelag: Bruttovolumen des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben. 
|-
|  || 
|}

== Funktionen für Raum ==

{| border=0
| colspan="3" | <big>RaumNameVonObj()</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Namen des Raums zurück, in dem das Objekt sich befindet.
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=GetSpaceNameForObj returns the space name for each object in the database

Spreadsheet cell:
=GetSpaceNameForObj(n='chair-1') returns the space name for the object named “chair-1”
</pre>
|-
| colspan="3" | <big>RaumNumVonObj()</big>
|-
|  || valign="top" | Gibt die Nummer des Raums zurück, in dem sich das Objekt befindet.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=GetSpaceNumForObj returns the space number for each object in the database

Spreadsheet cell:
=GetSpaceNumForObj(n='chair-1') returns the space number for the object named “chair-1”</pre>
|}

== Funktionen für Schaltkreis ==

{| border=0
| colspan="3" | <big>Objektdaten('eval circuit destination adapter'; '<Datenbank>'; '<Feldname>')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Zieladapter des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit destination adapter', '<Datenbank>', '<Feldname>'))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit destination device'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Zielgerät des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit destination device', '<Datenbank>', '<Feldname>'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit destination socket'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Zielanschluss des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit destination socket', '<Datenbank>', '<Feldname>'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit drop points', ['<Datenbank>'], ['<Feldname>'], ['AbschlüsseIgnorieren'])</big>
|-
|  || valign="top" | Auflistung der ID's von dazwischenliegenden Drop Points, Eigenschaftswerten oder angehängten Datenfeldern, durch die ein Stromkreis verläuft. Fügen Sie AbschlüsseIgnorieren hinzu, um die Drop Points am Anfang oder am Ende der Strecke nicht aufzulisten. Die Zeichnung muss analysiert werden.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit route'; ['<Datenbank>']; ['<Feldname>'])</big>
|-
|  || valign="top" | Gibt die Pfad-IDs, den Parameter oder den Datenbankeintrag von den Kabelpfaden, die vom Schaltkreis verwendet werden. Die Zeichnung muss zuvor mit dem entsprechenden Befehl überprüft werden.<p>(Schweiz: Objektdaten('eval circuit route', ['<Datenbank>]', '[<Feldname>]'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit source adapter'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Quellgerät des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit source adapter', '<Datenbank>', '<Feldname>'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit source device'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Quellgerät des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit source device', '<Datenbank>', '<Feldname>'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('eval circuit source socket'; '<Datenbank>'; '<Feldname>')</big>
|-
|  || valign="top" | Gibt den Parameter oder den Datenbankeintrag vom Quellanschluss des Schaltkreises.<p>(Schweiz: Objektdaten('eval circuit source socket', '<Datenbank>', '<Feldname>'))
|-
|  || 
|}

== Funktionen für Scheinwerfer ==

{| border=0
| colspan="3" | <big>Gewicht(Filter)</big>
|-
| style="width: 10pt;" |  || valign="top" | Das Gesamtgewicht des Scheinwerfers mit allem Zubehör. 
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Gerätetyp des Scheinwerferzubehörs. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Daten des Scheinwerferzubehörs. Als Parameter kann eine Eigenschaft des Scheinwerfers eingegeben werden. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Symbolnamen des Scheinwerferzubehörs. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Einstellungen der Scheinwerfer, wobei Zubehör ignoriert wird. Als Parameter kann eine Eigenschaft des Scheinwerfers eingegeben werden.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Pultkanal der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Lichtfarben der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Scheinwerfer'; <Feld>)</big>
|-
|  || valign="top" | Einstellungen der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.<p>(Schweiz: Objektdaten('Scheinwerfer', <Feld>))
|-
|  || 
|}

== Funktionen für Symbollinie Classic ==

{| border=0
| colspan="3" | <big>OBJEKTDATEN('xplanung'; [Objekt]; [Attribut; Index]; Attribut[:Format]; [Index])</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt Attributswerte von XPlanung-Objekten zurück. PARAMETER:
Objekt: (Optional) Das XPlanung-Objekt in dem sich das XPlanung-Attribut befindet.

Attribut: Das XPlanung-Attribute von dem der Wert zurückgegeben wird. Bei einer komplexen Datenstruktur muss zuerst das Übergeordnete Attribute als eigener Parameter angegeben werden.

Format: (Optional) Das Format des zurückzugebenden Werts. Bsp.: 'dachform:kurz'. Wird kein Format angegeben, wird der vollständige Wert zurückgegeben. Bsp.: 'Walmdach (3200)'
...:name oder ...:text: Gibt nur den entsprechenden Textwert zurück. Bsp.: 'Walmdach'.
...:value oder ...:wert: Gibt nur den entsprechenden numerischen Wert zurück. Bsp.: '3200'.
...:short oder ...:kurz: Gibt nur die entsprechende Kurzfom zurück. Bsp.: 'WD'.
...:roman oder ...:römisch: Zahlenwerte werden als Römische Zahl ausgegeben. Bsp.: 'XII' (12).

Index: (Optional) Welcher Wert zurückgegeben wird, wenn mehrere Werte definiert sind. Der erste Wert ist '0', der zweite Wert ist '1' usw. Wird kein Index angegeben (oder '-1') werden alle Werte als Text und durch ';' getrennt zurückgegeben. Bsp.: 'Pultdach (2100); Pultdach (3200)'.

Übersicht der XPlanung-Objekte und Attribute: https://xleitstelle.de/xplanung/releases
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=OBJEKTDATEN('xplanung'; 'BP_BaugebietsTeilFlaeche'; 'dachform') Gibt den Werts des Attributs 'dachform' im XPlanung-Objekt 'BP_BaugebietsTeilFlaeche' zurück.

=OBJEKTDATEN('xplanung'; 'dachform') Gibt den Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform'; 1) Gibt den zweiten Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform:kurz') Gibt die Kurzform des Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 'h') Gibt den Wert des Attributs 'h' aller Hoehenangaben zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 0; 'h') Gibt den Wert des Attributs 'h' der ersten Hoehenangabe zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 2; 'hoehenbezug:kurz')	Gibt die Kurzform des Werts des Attributs 'hoehenbezug' der dritten Hoehenangabe zurück.
</pre>
|}

== Funktionen für Tragwerkselement ==

{| border=0
| colspan="3" | <big>Objektdaten(Filter; 'Unterkante Ummantelung')</big>
|-
| style="width: 10pt;" |  || valign="top" | Die Unterkante der Ummantelung des Tragwerkselements.<p>(Schweiz: Objektdaten(Filter, 'Unterkante Ummantelung'))
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('cover bound bottom')     Returns the bottom bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound bottom')    Returns the bottom bound of the Structural Member cover.
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Oberkante Ummantelung')</big>
|-
|  || valign="top" | Die Oberkante der Ummantelung des Tragwerkselements.<p>(Schweiz: Objektdaten(Filter, 'Oberkante Ummantelung'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('cover bound top')     Returns the top bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound top')    Returns the top bound of the Structural Member cover.
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Physische Länge Ummantelung')</big>
|-
|  || valign="top" | Die physische Länge der Ummantelung des Tragwerkselements inklusive der Abschlüsse.<p>(Schweiz: Objektdaten(Filter, 'Länge Ummantelung'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('cover physical length')     Returns the physical length of the structural member cover including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover physical length')    Returns the physical length of the structural member cover including its start and end conditions.
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Unterkante Element')</big>
|-
|  || valign="top" | Die Unterkante des Tragwerkselements.<p>(Schweiz: Objektdaten(Filter, 'Unterkante Element'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('member bound bottom')     Returns the bottom bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound bottom')    Returns the bottom bound of the Structural Member.
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Oberkante Element')</big>
|-
|  || valign="top" | Die Oberkante des Tragwerkselements.<p>(Schweiz: Objektdaten(Filter, 'Oberkante Element'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('member bound top')     Returns the top bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound top')    Returns the top bound of the Structural Member.
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Länge Tragwerkselement')</big>
|-
|  || valign="top" | Die Länge des Tragwerkselements inklusive der Abschlüsse.<p>(Schweiz: Objektdaten(Filter, 'Länge Tragwerkselement'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=OBJECTDATA('member physical length')     Returns the physical length of the structural member including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member physical length')    Returns the physical length of the structural member including its start and end conditions.
</pre>
|}

== Funktionen für Tür ==

{| border=0
| colspan="3" | <big>Objektdaten('DoorCasingBasicType')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Grundtyp der Zarge zurück, falls die Tür eine Zarge besitzt.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Objektdaten('FloorRecessHeight')</big>
|-
|  || valign="top" | Gibt den Bodeneinstand der Tür zurück. Der Bodeneinstand ist definiert als Ebenenbasishöhe - UK Rahmen/Zarge, wenn die Laibungseinstellungen der Wand verwendet werden, sonst undefiniert.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsArchitecturalversion')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt eine Komplette Tür ist, andernfalls falsch. Komplette Türen sind Bestandteil des Architekturmoduls und benötigen eine entsprechende Seriennummer, um die volle Funktionalität freizuschalten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsBasicversion')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt eine Einfache Tür ist, andernfalls falsch. Einfache Türen sind Bestandteil aller Module, haben aber nur wenige Optionen und Einstellmöglichkeiten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('IsInsertedInWall')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt in eine Wand eingefügt ist, andernfalls falsch.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Material'; <Türbestandteil>)</big>
|-
|  || valign="top" | Gibt den Namen des Objektmaterials eines Bestandteils der Tür zurück.

Aufruf: =Objektdaten('Material';<Türbestandteil>)

Liste der unterstützten Türbestandteile:

  Beschlag
  Rahmen
  Rahmenfüllung
  Schwelle
  Stäbe Türblattfüllung
  Türblatt
  Türblattfüllung
  Zarge


Beispiel: =Objektdaten('Material';'Türblatt')

Groß-/Kleinschreibung spielt keine Rolle.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeHeightAutoDimension')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeSelectedHeight')</big>
|-
|  || valign="top" | Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird N/A zurückgegeben.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeSelectedWidth')</big>
|-
|  || valign="top" | Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('ModeWidthAutoDimension')</big>
|-
|  || valign="top" | Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung bemaßt wird.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('UseWallClosure')</big>
|-
|  || valign="top" | Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt die Laibungseinstellungen der Wand verwendet, andernfalls falsch.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('windoorhandletype'[;<Nr. des Türblatts>][; <Side>])</big>
|-
|  || valign="top" | Gibt den Typ des Türgriffs eines Türblatts zurück. Falls in 3D ein Symbol als Türgriff angezeigt wird, wird der Name des Symbols zurückgegeben.

Aufruf: =Objektdaten('Grifftyp'[; <Nr. des Türblatts>][; <Türseite>]])

      Nr. des Türblatts: von innen gesehen von links nach rechts.

      Türseite: 'Innen' (Innenseite) oder 'Aussen' (Außenseite).
Beispiel: =Objektdaten('Grifftyp';'1';'innen')

Wird die Nummer des Türblatts weggelassen und die Türblätter haben verschiedene Grifftypen, kann kein eindeutiger Grifftyp ermittelt werden.
Falls auch noch die Türseite weggelassen wird, müssen alle Tügrifftypen innen und außen an allen Türblättern gleich sein, um einen eindeutigen Rückgabewert zu erhalten.
|-
|  || 
|-
| colspan="3" | <big>Breite()</big>
|-
|  || valign="top" | Gibt diejenige Breite der Tür zurück, die im Reiter 'Türbreite' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.
|-
|  || 
|-
| colspan="3" | <big>Breite('FinishedWidthInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Breite Rechts zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FinishedWidthOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Breite Links zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FittingsClearWidth')</big>
|-
|  || valign="top" | Gibt die Lichte Breite Beschlag zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FrameClearWidth')</big>
|-
|  || valign="top" | Gibt das Lichte Durchgangsmaß Breite zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('FrameTotalWidth')</big>
|-
|  || valign="top" | Gibt das Zargen-/Rahmenaußenmaß Breite zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('NinetyDegreesClearWidth')</big>
|-
|  || valign="top" | Gibt die Lichte Breite 90° zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('RebateWidth')</big>
|-
|  || valign="top" | Gibt das Zargen-/Rahmenfalzmaß zurück.
|-
|  || 
|-
| colspan="3" | <big>Breite('UnfinishedWidth')</big>
|-
|  || valign="top" | Gibt das Rohmaß Breite zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türbreite' des Türendialogs.
|-
|  || 
|-
| colspan="3" | <big>Höhe()</big>
|-
|  || valign="top" | Gibt diejenige Höhe der Tür zurück, die im Reiter 'Türhöhe' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Höhe ist, die in Bemaßungen oder Beschriftungen angezeigt wird.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightObjectInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Tür rechts zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightObjectOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Tür links zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightWallInside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Wand rechts zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FinishedHeightWallOutside')</big>
|-
|  || valign="top" | Gibt das Fertigmaß Höhe Wand links zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FrameClearHeight')</big>
|-
|  || valign="top" | Gibt das Lichte Durchgangsmaß Höhe zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('FrameTotalHeight')</big>
|-
|  || valign="top" | Gibt das Zargen-/Rahmenaußenmaß Höhe zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('ThresholdHeightFromOrigin')</big>
|-
|  || valign="top" | Gibt die Schwellenhöhe ab Nullpunkt der Zeichnung zurück. Falls die Checkbox 'Schwelle in 3D erzeugen' ausgeschaltet ist: bei eingeschalteter Checkbox 'Rahmen unter Tür' entspricht OK Schwelle der Höhe 'UK Türblatt' aus dem Reiter 'Türhöhe', andernfalls der Höhe 'UK Rahmen' bzw. 'UK Zarge'.
|-
|  || 
|-
| colspan="3" | <big>Höhe('ThresholdHeightFromStory')</big>
|-
|  || valign="top" | Gibt die Schwellenhöhe ab Geschoss zurück. Falls die Checkbox 'Schwelle in 3D erzeugen' ausgeschaltet ist: bei eingeschalteter Checkbox 'Rahmen unter Tür' entspricht OK Schwelle der Höhe 'UK Türblatt' aus dem Reiter 'Türhöhe', andernfalls der Höhe 'UK Rahmen' bzw. 'UK Zarge'.
|-
|  || 
|-
| colspan="3" | <big>Höhe('UnfinishedHeight')</big>
|-
|  || valign="top" | Gibt das Rohmaß Höhe Tür zurück. Das Rohmaß Tür ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türhöhe' des Türendialogs.
|-
|  || 
|-
| colspan="3" | <big>Höhe('UnfinishedHeightWall')</big>
|-
|  || valign="top" | Gibt das Rohmaß Höhe Wand zurück. Das Rohmaß Wand ist definiert als Abstand von UK Wandöffnung bis OK Rohmaß Höhe Tür (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türhöhe' des Türendialogs.
|-
|  || 
|-
| colspan="3" | <big>Winkel('Energos')</big>
|-
|  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
|  || 
|}

== Funktionen für Wand ==

{| border=0
| colspan="3" | <big>Gewicht('Brutto'; [optionale Parameter])</big>
|-
| style="width: 10pt;" |  || valign="top" | Gewicht von Boden/Decke oder Boden/Deckenschicht in kg. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Gewicht(Filter, 'Brutto', [optionale Parameter]))
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Gewicht('Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Gewicht von Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Gewicht(Gewicht, 'Netto', [optionale Parameter])
|-
|  || 
|-
| colspan="3" | <big>Grundfläche('Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Grundfläche einer Wand oder einer Wandschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Grundfläche(Filter, 'Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=FootprintArea('gross') returns the gross area of the footprint of the wall or wall component.

=FootprintArea('gross', 'component=core') returns the gross area of the footprint of the core component of the wall.

=FootprintArea('gross', 'height=100mm') returns the gross area of the footprint of the wall or wall component, but measured at 100mm from the layer.</pre>
|-
| colspan="3" | <big>Grundfläche('Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Grundfläche einer Wand oder Wandschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.
Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht in der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Grundfläche(Filter, 'Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=FootprintArea('net') returns the area of the footprint of the wall or wall component.

=FootprintArea('net', 'min opening area=0.5 sq m') returns the area of the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters.

=FootprintArea('net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=FootprintArea('net', 'opening type=Door') returns the area of the footprint of the wall or wall component, but only taking openings created by "Door" plug-in objects into account.

=FootprintArea('net', 'exclude opening type=Door') returns the area of the footprint of the wall or wall component, but ignoring any openings that are created by "Door" plug-in objects.

=FootprintArea('net', 'opening type=Door;WinDoor 6.0') returns the area of the footprint of the wall or wall component, but only taking openings created by "Door" or "WinDoor 6.0" plug-in objects into account.

=FootprintArea('net', 'component=core') returns the area of the footprint of the core component of the wall.

=FootprintArea('net', 'height=100mm') returns the area of the footprint of the wall or wall component, but measured at 100mm from the layer.</pre>
|-
| colspan="3" | <big>Grundfläche('Öffnungen'; [optionale Parameter])</big>
|-
|  || valign="top" | Gibt die Fläche der Öffnungen in der Grundfläche einer Wand oder Wandschicht zurück.

'Schichtname=...': Es werden nur Öffnungen in den Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Grundfläche(Filter, 'Öffnungen', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=FootprintArea('openings') returns the total area of openings on the footprint of the wall or wall component.

=FootprintArea('openings', 'min opening area=0.5 sq m') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters.

=FootprintArea('openings', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=FootprintArea('openings', 'opening type=Door') returns the total area of openings on the footprint of the wall or wall component, but only taking openings created by "Door" plug-in objects into account.

=FootprintArea('openings', 'exclude opening type=Door') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings that are created by "Door" plug-in objects.

=FootprintArea('openings', 'opening type=Door;WinDoor 6.0') returns the total area of openings on the footprint of the wall or wall component, but only taking openings created by "Door" or "WinDoor 6.0" plug-in objects into account.

=FootprintArea('openings', 'component=core') returns the total area of openings on the footprint of the core component of the wall.

=FootprintArea('openings', 'height=100mm') returns the total area of openings on the footprint of the wall or wall component, but measured at 100mm from the layer.</pre>
|-
| colspan="3" | <big>Objektdaten('Schalldämmung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Brennbare Konstruktion')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Brandmauer')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schichtname')</big>
|-
|  || valign="top" | Der Name der Wand-, Boden/Decke- oder Dachschicht.<p>(Schweiz: Objektdaten(Filter, 'Schichtname'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-Code')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Kostenindex-System')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Beschreibung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Aussenseite')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Feuerwiderstand')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Funktion')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Lambda')</big>
|-
|  || valign="top" | Der Lambdawert des Objekt.<p>(Schweiz: Objektdaten(Filter, 'Lambda'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Tragend')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Hersteller')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Bezeichnung')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Modell')</big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Pfadtyp')</big>
|-
|  || valign="top" | Gibt den Leitlinientyp der Wand. 0 ist Linie und 1 ist Bogen.<p>(Schweiz: Objektdaten(Filter, 'Leitlinie'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('R-Wert')</big>
|-
|  || valign="top" | Der R-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'R-Wert'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('U-Wert')</big>
|-
|  || valign="top" | Der U-Wert des Objekts.<p>(Schweiz: Objektdaten(Filter, 'U-Wert'))
|-
|  || 
|-
| colspan="3" | <big>Breite()</big>
|-
|  || valign="top" | Die Dicke einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Durchschnitt')</big>
|-
|  || valign="top" | Berechnet die durchschnittliche Höhe einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.<p>(Schweiz: Höhe(Filter, 'Durchschnitt'))
|-
|  || 
|-
| colspan="3" | <big>Höhe('Insgesamt')</big>
|-
|  || valign="top" | Die Gesamthöhe einer Wand.<p>(Schweiz: Höhe(Filter, 'Gesamt'))
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Einsätze'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Anzahl der in der Wand eingefügten Objekte (Symbole und intelligente Objekte).

'Einfügungstyp=...': Es werden nur eingefügte Objekte mit den angegebenen Namen berücksichtigt. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Einfügungstyp ausschließen': Es werden die angegebenen Objekte in Wände nicht gezählt.<p>(Schweiz: Anzahl(Filter, 'Einsätze', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Count('inserts') returns the number of inserts in the wall object.

=Count('inserts', 'insert type=Window') returns the number of "Window" plug-in object inserts.

=Count('inserts', 'insert type=Window;WinDoor 6.0') returns the number of by "Window" and "WinDoor 6.0" plug-in object inserts.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.</pre>
|-
| colspan="3" | <big>Anzahl('Modifikatoren'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Anzahl der Modifikatoren in einem Boden oder Decke oder einer Wand. Bei einer Wand sind das Vorsprung und Nische, für Boden/Decke sind Volumenaddition und -subtraktion, sowie Entwässerung.

'Modifikatortyp=...': Es werden nur Modifikatoren mit den angegebenen Typen berücksichtigt. Mehrere Typen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Modifikatortyp ausschließen': Es werden die Modifikatoren mit dem angegebenen Typen nicht gezählt.<p>(Schweiz: Anzahl(Filter, 'Modifikatoren', [optionale Parameter])
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Öffnungen'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen in den Schichten gezählt, die dem Filter entsprechen.

'Schichtmaterial=...': Es werden nur Bauteile mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (für Wände), oben, unten (für Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Öffnungskriterien: Es werden nur Öffnungen gezählt, die alle angegebenen Kriterien erfüllen. Wenn für die Werte keine Einheiten angegeben sind, wird von Millimetern, Quadratmillimetern oder Kubikmillimetern ausgegangen. Für Böden/Decken stehen folgende Kriterien zur Verfügung: minimale Öffnungsfläche oben, maximale Öffnungsfläche oben, minimale Öffnungsfläche unten, maximale Öffnungsfläche unten, minimales Öffnungsvolumen, maximales Öffnungsvolumen, minimaler Öffnungsumfang oben, maximaler Öffnungsumfang oben, minimaler Öffnungsumfang unten, maximaler Öffnungsumfang unten. Für Wände stehen die folgenden Kriterien zur Verfügung: Min Öffnungsfläche links, Max Öffnungsfläche links, Min Öffnungsfläche rechts, Max Öffnungsfläche rechts, Min Öffnungsfläche dem Kern zugewandt, Max Öffnungsfläche dem Kern zugewandt, Min Öffnungsfläche dem Kern abgewandt, Max Öffnungsfläche dem Kern abgewandt, Min Öffnungsfläche Mitte, Max Öffnungsfläche Mitte, Min Öffnungsfläche der Grundfläche, Max Öffnungsfläche der Grundfläche, Min Öffnungslänge der Grundfläche links, Max Öffnungslänge der Grundfläche links, Min Öffnungslänge der Grundfläche rechts, Max Öffnungslänge der Grundfläche rechts, Min Öffnungslänge der Grundfläche dem Kern zugewandt, Max Öffnungslänge der Grundfläche dem Kern zugewandt, Min Öffnungslänge der Grundfläche dem Kern abgewandt, Max. Öffnungslänge der Grundfläche dem Kern abgewandt, Min Öffnungslänge der Grundfläche Mitte, Max Öffnungslänge der Grundfläche Mitte, Min Öffnungsvolumen, Max Öffnungsvolumen. 

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden. Gilt nur für Wände.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Gilt nur für Wände.

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -länge anhand der Filterkriterien gemessen werden. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Anzahl(Filter, 'Öffnungen', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Count('openings') returns the number of openings in the wall, wall component, slab or slab component.

=Count('openings', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters.

=Count('openings', 'min opening area top=0.5 sq m', 'max opening area top=1 sq m') returns the number of openings with an area between 0.5 and 1 square meter on the top of the slab or slab component.

=Count('openings', 'min opening area bottom=1 sq ft', 'max opening volume=10 cu in') returns the number of openings with an area of at least 1 square foot on the bottom of the slab or slab component and a volume of at most 10 cubic inches.

=Count('openings', 'opening type=Window') returns the number of openings created by "Window" plug-in objects.

=Count('openings', 'opening type=Window;WinDoor 6.0') returns the number of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Count('openings', 'component=core', 'min opening volume=10 cu cm') returns the number of openings with a volume of at least 10 cubic centimeters in the wall core component.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.</pre>
|-
| colspan="3" | <big>Winkel('Energos')</big>
|-
|  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
|  || 
|-
| colspan="3" | <big>WandflächeNetto()</big>
|-
|  || valign="top" | 2D-Wandfläche einer Wand ohne Tür- und Fensterflächen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallArea_Net returns the average of the net area of the interior and exterior face of the wall, for each wall in the database; the net area is adjusted for holes in the wall

Spreadsheet cell:
=WallArea_Net(t=wall) returns the average of the net area of the interior and exterior face of the wall, combined for all walls in the drawing; the net area is adjusted for holes in the wall
</pre>
|-
| colspan="3" | <big>WandflächeBrutto()</big>
|-
|  || valign="top" | 2D-Wandfläche einer Wand inkl. Tür- und Fensterflächen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallArea_Gross returns the average of the gross area of the interior and exterior face of the wall, for each wall in the database; the gross area ignores holes in the wall

Spreadsheet cell:
=WallArea_Gross(t=wall) returns the average of the gross area of the interior and exterior face of the wall, combined for all walls in the drawing; the gross area ignores holes in the wall
</pre>
|-
| colspan="3" | <big>DurchschnWandhöhe()</big>
|-
|  || valign="top" | Durchschnittliche Wandhöhe inkl. der höchsten Punkte und verschiedener Anfangs- und Endhöhen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallAverageHeight returns the average height for each wall object in the database

Spreadsheet cell:
=WallAverageHeight((t=wall)&(sel=true)) returns the average height of all walls that are selected in the drawing
</pre>
|-
| colspan="3" | <big>Wanddicke()</big>
|-
|  || valign="top" | Wanddicke.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallThickness returns the thickness for each wall object in the database

Spreadsheet cell:
=WallThickness(t=wall) returns the combined thickness of all walls in the drawing
</pre>
|-
| colspan="3" | <big>Wandstilname()</big>
|-
|  || valign="top" | Name des Wandstils.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallStyleName returns the name of the wall style for each wall object in the database

Spreadsheet cell:
=WallStyleName(n='wall-1') returns the name of the wall style for the object named “wall-1”
</pre>
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Berechnet die Fläche einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Length()</big>
|-
|  || valign="top" | Die Länge einer Wand oder seiner Schichten.
|-
|  || 
|-
| colspan="3" | <big>Länge('Leitlinie Kern abgewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wandschicht, die von der Kernschicht abgewandt ist. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Länge('Leitlinie Kern abgewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Leitlinie Mitte'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die in der Mitte verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Länge('Leitlinie Mitte', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Leitlinie Kern zugewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wandschicht, die der Kernschicht zugewandt ist. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Länge('Leitlinie Kern zugewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge(Leitlinie links; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Kante der Wand oder Wandschicht verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Länge('Leitlinie links', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge(Leitlinie rechts; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Kante der Wand oder Wandschicht verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Länge('Leitlinie rechts', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Kern abgewandt Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wandschicht entlang der Wandunterkante, die vom Kern abgewandt ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Kern abgewandt Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Kern abgewandt Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wandschicht entlang der Unterkante, die vom Kern abgewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Kern abgewandt Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Mitte Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wand oder Wandschicht entlang der Mittellinie der Wandunterkante. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Mitte Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Mitte Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wandschicht entlang der Mittellinie der Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Mitte Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Kern zugewandt Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wandschicht entlang der Wandunterkante, die dem Kern zugewandt ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Kern zugewandt Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Kern zugewandt Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge einer Wandschicht entlang der Unterkante, die dem Kern zugewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Kern zugewandt Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Links Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Unterkante der Wand oder Wandschicht verläuft. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Links Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Links Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Kante der Wand oder Wandschicht verläuft.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Links Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Rechts Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Unterkante der Wand oder Wandschicht verläuft. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Rechts Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Rechts Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Unterkante der Wand oder Wandschicht verläuft.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge(Filter, 'Rechts Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Öffnungen Kern abgewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Unterkante, die zu Kernschicht abgewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge('Öffnungen dem Kern abgewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Öffnungen Mitte'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Mittellinie der Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge('Öffnungen Mitte', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Öffnungen Kern zugewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Unterkante, die der Kernschicht zugewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge('Öffnungen dem Kern zugewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Öffnungen links'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Gesamtlänge der Öffnungen einer Wandschicht entlang der linken Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge('Öffnungen links', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Länge('Öffnungen rechts'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Gesamtlänge der Öffnungen einer Wandschicht entlang der rechten Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.<p>(Schweiz: Länge('Öffnungen rechts', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Kern abgewandt Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche einer Wandschichtoberfläche, die von der Kernschicht weg ausgerichtet ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Kern abgewandt Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Kern abgewandt Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche einer Wandschichtoberfläche, die von der Kernschicht weg ausgerichtet ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.<p>(Schweiz: Oberfläche(Filter, 'Kern abgewandt Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Mitte Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche entlang der Mittellinie einer Wand oder einer Wandschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Mitte Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('center gross') returns the gross area along the center line of the wall or wall component.

=SurfaceArea('center gross', 'component=core') returns the gross area along the center line of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Mitte Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche entlang der Mittellinie einer Wand oder einer Wandschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.<p>(Schweiz: Oberfläche(Filter, 'Mitte Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('center net') returns the area along the center line of the wall or wall component.

=SurfaceArea('center net', 'min opening area=0.5 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('center net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('center net', 'opening type=Window') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('center net', 'exclude opening type=Window') returns the area along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('center net', 'opening type=Window;WinDoor 6.0') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('center net', 'component=core') returns the area along the center line of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Kern zugewandt Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Kern zugewandt Brutto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Kern zugewandt Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Kern zugewandt Netto', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Links Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der linken Wand- oder Wandschichtoberfläche. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Links Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('left gross') returns the gross area of the left side of the wall or wall component.

=SurfaceArea('left gross', 'component=core') returns the gross area of the left side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Links Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Links Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('left net') returns the area of the left side of the wall or wall component.

=SurfaceArea('left net', 'min opening area=0.5 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('left net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('left net', 'opening type=Window') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('left net', 'exclude opening type=Window') returns the area of the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('left net', 'opening type=Window;WinDoor 6.0') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('left net', 'component=core') returns the area of the left side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Öffnungen Kern abgewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der Öffnungen auf der Oberfläche einer Wandschicht, die von der Kernschale weg orientiert ist.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen Kern abgewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Öffnungen Mitte'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der Öffnungen entlang der Mittellinie einer Wand oder einer Wandschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen Mitte', [optionale Parameter])
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('openings center') returns the total area of openings along the center line of the wall or wall component.

=SurfaceArea('openings center', 'min opening area=0.5 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings center', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings center', 'opening type=Window') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings center', 'exclude opening type=Window') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings center', 'opening type=Window;WinDoor 6.0') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings center', 'component=core') returns the total area of openings along the center line of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Öffnungen Kern zugewandt'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Öffnungen auf einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist. 

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen Kern zugewandt', [optionale Parameter]))
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Öffnungen links'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Öffnungen auf der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen links', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('openings left') returns the total area of openings on the left side of the wall or wall component.

=SurfaceArea('openings left', 'min opening area=0.5 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings left', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings left', 'opening type=Window') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings left', 'exclude opening type=Window') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings left', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings left', 'component=core') returns the total area of openings on the left side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Öffnungen rechts'; [optionale Parameter])</big>
|-
|  || valign="top" | Die Fläche der Öffnungen auf der rechten Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Öffnungen rechts', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('openings right') returns the total area of openings on the right side of the wall or wall component.

=SurfaceArea('openings right', 'min opening area=0.5 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings right', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings right', 'opening type=Window') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings right', 'exclude opening type=Window') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings right', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings right', 'component=core') returns the total area of openings on the right side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Rechts Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der rechten Wand- oder Wandschichtoberfläche. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Oberfläche(Filter, 'Rechts Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('right gross') returns the gross area of the right side of the wall or wall component.

=SurfaceArea('right gross', 'component=core') returns the gross area of the right side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Oberfläche('Rechts Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Fläche der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.<p>(Schweiz: Oberfläche(Filter, 'Rechts Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SurfaceArea('right net') returns the area of the right side of the wall or wall component.

=SurfaceArea('right net', 'min opening area=0.5 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('right net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('right net', 'opening type=Window') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('right net', 'exclude opening type=Window') returns the area of the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('right net', 'opening type=Window;WinDoor 6.0') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('right net', 'component=core') returns the area of the right side of the core component of the wall.</pre>
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Brutto'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.<p>(Schweiz: Volumen(Filter, 'Brutto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.</pre>
|-
| colspan="3" | <big>Volumen('Netto'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.<p>(Schweiz: Volumen(Filter, 'Netto', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.</pre>
|-
| colspan="3" | <big>Volumen('Öffnungen'; [optionale Parameter])</big>
|-
|  || valign="top" | Das Volumen der Öffnungen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.<p>(Schweiz: Volumen(Filter, 'Öffnungen', [optionale Parameter]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.</pre>
|-
| colspan="3" | <big>Wandhöhe()</big>
|-
|  || valign="top" | Höhe von Wänden in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=WallOverallHeight returns the average overall height for each wall object in the database

Spreadsheet cell:
=WallOverallHeight((t=wall)&(sel=true)) returns the average overall height of all walls that are selected in the drawing
</pre>
|}

== Funktionen für WinDoor 6.0 ==

{| border=0
| colspan="3" | <big>Winkel('Energos')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
| style="width: 10pt;" |  || 
|}

== Funktionen für Window ==

{| border=0
| colspan="3" | <big>Winkel('Energos')</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Volume(criteria, 'glazing all')</big>
|-
|  || valign="top" | Returns the total volume of all glazing.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing for sashes')</big>
|-
|  || valign="top" | Returns the volume of glazing for all sashes except the transom.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing for sashes')     Returns the volume of glazing for all sashes except the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sashes')    Returns the volume of glazing for all sashes except the transom.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'glazing for transom')</big>
|-
|  || valign="top" | Returns the volume of glazing for the transom.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'window jamb')</big>
|-
|  || valign="top" | Returns the volume of all geometry that makes up the Jamb and Mullions.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('window jamb')     Returns the volume of all geometry that makes up the Jamb and Mullions.

Spreadsheet cell:
=VOLUME(SEL, 'window jamb')   Returns the volume of all geometry that makes up the Jamb and Mullions.
</pre>
|-
| colspan="3" | <big>Volume(criteria, 'window sashes')</big>
|-
|  || valign="top" | Returns the total volume the all sashes (including the transom sash).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=VOLUME('window sashes')     Returns the total volume the all sashes (including the transom sash).

Spreadsheet cell:
,VOLUME(SEL, 'window sashes')    Returns the total volume the all sashes (including the transom sash).
</pre>
|}

== Funktionen für XPlanung ==

{| border=0
| colspan="3" | <big>OBJEKTDATEN('xplanung'; [Objekt]; [Attribut; Index]; Attribut[:Format]; [Index])</big>
|-
| style="width: 10pt;" |  || valign="top" | Gibt Attributswerte von XPlanung-Objekten zurück. PARAMETER:
Objekt: (Optional) Das XPlanung-Objekt in dem sich das XPlanung-Attribut befindet.

Attribut: Das XPlanung-Attribute von dem der Wert zurückgegeben wird. Bei einer komplexen Datenstruktur muss zuerst das Übergeordnete Attribute als eigener Parameter angegeben werden.

Format: (Optional) Das Format des zurückzugebenden Werts. Bsp.: 'dachform:kurz'. Wird kein Format angegeben, wird der vollständige Wert zurückgegeben. Bsp.: 'Walmdach (3200)'
...:name oder ...:text: Gibt nur den entsprechenden Textwert zurück. Bsp.: 'Walmdach'.
...:value oder ...:wert: Gibt nur den entsprechenden numerischen Wert zurück. Bsp.: '3200'.
...:short oder ...:kurz: Gibt nur die entsprechende Kurzfom zurück. Bsp.: 'WD'.
...:roman oder ...:römisch: Zahlenwerte werden als Römische Zahl ausgegeben. Bsp.: 'XII' (12).

Index: (Optional) Welcher Wert zurückgegeben wird, wenn mehrere Werte definiert sind. Der erste Wert ist '0', der zweite Wert ist '1' usw. Wird kein Index angegeben (oder '-1') werden alle Werte als Text und durch ';' getrennt zurückgegeben. Bsp.: 'Pultdach (2100); Pultdach (3200)'.

Übersicht der XPlanung-Objekte und Attribute: https://xleitstelle.de/xplanung/releases
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=OBJEKTDATEN('xplanung'; 'BP_BaugebietsTeilFlaeche'; 'dachform') Gibt den Werts des Attributs 'dachform' im XPlanung-Objekt 'BP_BaugebietsTeilFlaeche' zurück.

=OBJEKTDATEN('xplanung'; 'dachform') Gibt den Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform'; 1) Gibt den zweiten Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform:kurz') Gibt die Kurzform des Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 'h') Gibt den Wert des Attributs 'h' aller Hoehenangaben zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 0; 'h') Gibt den Wert des Attributs 'h' der ersten Hoehenangabe zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 2; 'hoehenbezug:kurz')	Gibt die Kurzform des Werts des Attributs 'hoehenbezug' der dritten Hoehenangabe zurück.
</pre>
|}

== Funktionen für Zaun ==

{| border=0
| colspan="3" | <big>Tiefe('Sockelbrett')</big>
|-
| style="width: 10pt;" |  || valign="top" | Diese Funktion kann auf Zaunobjekte und Unterobjekt Sockelbrett angewandt werden.
Die Tiefe des Sockelbretts, sofern vorhanden.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Tiefe('Horizontale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profiltiefe und N/A, wenn gemischte Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Tiefe('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profiltiefe und N/A, wenn gemischte Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Tiefe('Strebe'; <Index>)</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Tiefe der aktiven Strebe.

Unterobjekt Strebe: Tiefe der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.<p>(Schweiz: Tiefe('Strebe', <Index>))
|-
|  || 
|-
| colspan="3" | <big>Tiefe('Streben')</big>
|-
|  || valign="top" | Diese Funktion kann auf Unterobjekt Strebe angewandt werden: Die Tiefe der Streben.
|-
|  || 
|-
| colspan="3" | <big>Tiefe('Vertikale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profilbreite und N/A, wenn gemischte Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Grundfläche('Eckfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundament der Eckpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Eckpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Grundfläche('Fundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundamente.

Unterobjekt Fundament: Grundfläche des Punktfundaments.
|-
|  || 
|-
| colspan="3" | <big>Grundfläche('Torfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundamente der Zauntorpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Torpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Grundfläche('Zwischenfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundament der Zwischenpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Zwischenpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Fundamenttyp')</big>
|-
|  || valign="top" | Diese Funktion kann auf nur auf Unterobjekt Fundament angewandt werden.

Gibt den Fundamenttyp zurück. Mögliche Werte sind Punktfundament für Eck-, Zwischen- oder Zauntorpfosten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Füllungstyp')</big>
|-
|  || valign="top" | Diese Funktion kann auf nur auf Unterobjekt Füllung angewandt werden.

Gibt die Füllung der Zaunfelder zurück. Mögliche Werte sind Fertigelement, vertikale Zaunlatten und horizontale Zaunlatten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Name')</big>
|-
|  || valign="top" | Diese Funktion kann auf alle Unterobjekte des Zaun angewandt werden: Pfosten, Zauntor, Zaunfeld und Strebe.

Name der verwendeten Symboldefinition.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Pfostentyp')</big>
|-
|  || valign="top" | Diese Funktion kann auf nur auf Unterobjekt Pfosten angewandt werden.

Gibt den Pfostentyp zurück . Mögliche Werte sind Eckpfosten, Zwischenpfosten und Torpfosten.
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Strebenindex')</big>
|-
|  || valign="top" | Diese Funktion kann auf nur auf Unterobjekt Strebe angewandt werden.

Gibt den Index des Strebentyps zurück, beginnend mit Index 1.
|-
|  || 
|-
| colspan="3" | <big>Breite('Horizontale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaunobjekte und deren Zaunfelder angewandt werden:

BESCHREIBUNG:
Profilbreite und N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Breite('Vertikale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaun-Objekte und Unterobjet Zaunfeld angewandt werden:

BESCHREIBUNG:
Gibt die Profildicke zurück und N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Eckfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl allerPunktfundamente der Eckpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht und N/A für runde Punktfundamente.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Eckpfosten')</big>
|-
|  || valign="top" | Diese Funktion ist identisch mit Länge('Eckpfosten').
|-
|  || 
|-
| colspan="3" | <big>Höhe('Blenden')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Höhe der Blende (bei mehreren Blenden die Höhe der ersten Blende).

Unterobjekt Strebe: Gibt nur dann ein Ergbnis zurück, wenn Blende und keine Strebe.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Fundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Torfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente der Torpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps. N/A, wenn Fundamenttyp nicht für Zauntore.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Torpfosten')</big>
|-
|  || valign="top" | Diese Funktion ist identisch mit Länge('Torpfosten').
|-
|  || 
|-
| colspan="3" | <big>Höhe('Zauntore')</big>
|-
|  || valign="top" | Diese Funktion kann nur auf das Unterobjekt Zauntor angewandt werden und gibt die Höhe des Zauntors zurück.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Sockelbrett')</big>
|-
|  || valign="top" | Diese Funktion kann auf das Zaunobjekt und das Unterobjekt Sockelbrett angewandt werden.
Die Höhe des Sockelbretts, sofern vorhanden.
|-
|  || 
|-
| colspan="3" | <big></big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big></big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Höhe('Strebe'; <Index>)</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Breite der aktiven Strebe.

Unterobjekt Strebe: Breite der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.<p>(Schweiz: Höhe('Strebe', <Index>))
|-
|  || 
|-
| colspan="3" | <big>Höhe('Streben')</big>
|-
|  || valign="top" | Diese Funktion kann angewandt werden auf:
›nUnterobjekt Strebe: Die Höhe der Strebe.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Zwischenfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps. N/A, wenn Fundamenttyp nicht für Zwischenpfosten.
|-
|  || 
|-
| colspan="3" | <big>Höhe('Zwischenpfosten')</big>
|-
|  || valign="top" | Diese Funktion ist identisch mit Länge('Zwischenpfosten').
|-
|  || 
|-
| colspan="3" | <big>Höhe('Oberkante zum Boden')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaun-Objekte angewandt werden.

Der höchte Punkt aller Streben, wenn das Zaunfeld 'Nur Querstreben' ist.

Andernfalls den Wert von 'Oberkante zum Boden'.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Eckfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl aller Eckfundamente.

Unterobjekt Fundament: Ergebnis 1 für Punktfundament Eckpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Eckpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Eckpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Eckpfosten.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Blenden')</big>
|-
|  || valign="top" | Die Funktion kann angewendet werden auf:

Zaun-Objekt: Die Gesamtzahl der Streben, die als Blenden behandelt werden.

Unterobjekt Strebe: Gibt 1 zurück, wenn Blende und keine Strebe.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Fundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente aller Pfosten.

Unterobjekt Pfosten: Ergebnis 1, wenn Punktfundament.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Torfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente der Torpfosten.

Unterobjekt Pfosten: Ergebnis 1, Punktfundament Torpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Torpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Torpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Torpfosten.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Zauntore')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Zauntore.

Unterobjekt Tor: Ergebnis 1 für Zauntore.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Sockelbrett')</big>
|-
|  || valign="top" | Die Funktion kann angewendet werden auf:

Zaun-Objekt: Anzahl der Sockelbretter, sofern in den Einstellungen ausgewählt.

 Unterobjekt Sockelbrett: Gibt 1 zurück.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Horizontale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann angewandt werden auf:

Zaun-Objekt: Gesamtzahl der horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Gibt eine 1 für jedes Zaunfeld mit horizontalen Zaunlatten. N/A, wenn die Zaunfelder unterschiedlich gefüllt sind.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl aller Fertigelemente im Zaun.

Unterobjekt Fertigelement: Ergebnis 1 für Fertigelement und N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Pfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Pfosten.

Unterobjekt Pfosten: Ergebnis 1 für Pfosten.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Strebe'; <Index>)</big>
|-
|  || valign="top" | Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Ergebnis ist 1, wenn der Index innerhalb der Anzahl der Streben liegt, oder 0, wenn der Index größer als die Anzahl ist.

Unterobjekt Strebe: Ergebnis ist 1, wenn die Strebe dem Index entspricht. Andernfalls N/A.<p>(Schweiz: Anzahl('Strebe', <Index>))
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Streben')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Streben.

Unterobjekt Strebe: Ergebnis 1 für Strebe.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Zwischenfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Ergebnis 1 für Punktfundament Zwischenpfosten und N/A für alle anderen Fundamente.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Zwischenpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Zwischen- bzw. Mittelpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Mittelpfosten.
|-
|  || 
|-
| colspan="3" | <big>Anzahl('Vertikale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl der vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Ergebnis 1, wenn vertikale Zaunlatten vorhanden sind. N/A, wenn gemischte Zaunfelder. 
|-
|  || 
|-
| colspan="3" | <big>Länge('2D')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaun-Objekte angewandt werden:

BESCHREIBUNG:
2D-Länge des Zaun unter Berücksichtigung eines Versatzes vom Pfad.
|-
|  || 
|-
| colspan="3" | <big>Länge('3D')</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaun-Objekte angewandt werden:

BESCHREIBUNG:
3D-Länge des Zaun unter Berücksichtigung eines Versatzes vom Pfad.
|-
|  || 
|-
| colspan="3" | <big>Länge('Eckpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Eckpfosten.
|-
|  || 
|-
| colspan="3" | <big>Länge('Blenden')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Blenden mit gleichen Index. Bei mehreren Blenden wird die erste Blende genommen.

Unterobjekt Strebe:  Länge der Blende und N/A, wenn keine Blende, sondern Strebe.
|-
|  || 
|-
| colspan="3" | <big>Länge('Torfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Torpfosten.
|-
|  || 
|-
| colspan="3" | <big>Länge('Zauntore')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Zauntore.

Unterobjekt Zauntor: Länge der Tors entlang des Zaunverlaufs.
|-
|  || 
|-
| colspan="3" | <big>Länge('Sockelbrett')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Sockelbretter.

Sockelbrett: Länge des Sockelbretts.
|-
|  || 
|-
| colspan="3" | <big>Länge('Horizontale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Länge der horizontalen Zaunlatte. Sie wird von Start- zu Endpfosten durch den Pfadverlauf (gerade und gekrümmt) des Zauns bestimmt. N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Länge('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Fertigelemente.

Unterobjekt Zaunfeld: Länge des Fertigelements. N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Länge('Pfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich.
|-
|  || 
|-
| colspan="3" | <big>Länge('Strebe'; <Index>)</big>
|-
|  || valign="top" | Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Gesamtlänge aller Streben, auf die mit Index verwiesen wird.

Unterobjekt Strebe: Länge der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.<p>(Schweiz: Länge('Strebe', <Index>))
|-
|  || 
|-
| colspan="3" | <big>Länge('Streben')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Streben.

Unterobjekt Strebe:Länge der Strebe.
|-
|  || 
|-
| colspan="3" | <big>Länge('Zwischenpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge der Pfosten.

Unterobjekt Pfosten: Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Zwischenpfosten.
|-
|  || 
|-
| colspan="3" | <big>Länge('Vertikale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Länge der vertikalen Zaunlatte. Sie wird von Start- zu Endpfosten durch den Pfadverlauf (gerade und gekrümmt) des Zauns bestimmt. N/A bei gemischten Zaunfelder.
|-
|  || 
|-
| colspan="3" | <big>Oberfläche('Blenden')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtoberfläche aller Blenden.

Unterobjekt Strebe: Oberfläche der Blende und N/A, wenn keine Blende, sondern Strebe.
|-
|  || 
|-
| colspan="3" | <big></big>
|-
|  || valign="top" | 
|-
|  || 
|-
| colspan="3" | <big>Volumen()</big>
|-
|  || valign="top" | Diese Funktion kann auf Zaun-Objekte angewandt werden:

Gesamtvolumen des Zaun-Objekts.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Eckfundament')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Eckpfosten.

Unterobjekt Fundament: Volumen des Fundaments. N/A, wenn nicht Punktfundament Eckpfosten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Eckpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Eckpfosten.

Unterobjekt Pfosten: Volumen des Eckpfostens. N/A, wenn nicht Eckpfosten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Fundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente.

Unterobjekt Fundament: Volumen des Punktfundaments.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Torfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Torpfosten.

Unterobjekt Fundament: Volumen des Punktfundaments. N/A, wenn nicht Punktfundament für Zauntorpfosten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Torpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Torpfosten.

Unterobjekt Pfosten: Volumen des Torpfostens. N/A, wenn nicht Torpfosten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Zauntore')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Zauntore.

Unterobjekt Zauntor: Volumen des Zauntors.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Sockelbrett')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Sockelbretter.

Unterobjekt Sockelbrett: Volumen des Sockelbretts.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Horizontale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Volumen der horizontalen Zaunlatten und N/A bei gemischten Zaunfeldern.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Fertigelemente/Platten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Fertigelemente.

Unterobjekt Zaunfeld: Volumen des Fertigelements und N/A bei gemischten Zaunfeldern.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Pfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Pfosten.

Unterobjekt Pfosten: Volumen des Pfostens.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Strebe'; <Index>)</big>
|-
|  || valign="top" | Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Gesamtvolumen aller Streben, die dem Index entsprechen

Unterobjekt Strebe: Volumen der Strebe, die dem Index entspricht. Andernfalls N/A.<p>(Schweiz: Volumen('Strebe', <Index>))
|-
|  || 
|-
| colspan="3" | <big>Volumen('Streben')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Streben.

Unterobjekt Strebe: Volumen der Strebe, wobei Tiefe und Höhe ungleich Null sein müssen.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Zwischenfundamente')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Volumen des Punktfundaments des Zwischenpfostens. N/A, wenn nicht Punktfundament Zwischenpfosten. 
|-
|  || 
|-
| colspan="3" | <big>Volumen('Zwischenpfosten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Zwischenpfosten.

Unterobjekt Pfosten: Volumen des Zwischenpfostens. N/A, wenn kein Zwischenpfosten.
|-
|  || 
|-
| colspan="3" | <big>Volumen('Vertikale Zaunlatten')</big>
|-
|  || valign="top" | Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Volumen der vertikalen Zaunlatten und N/A bei gemischten Zaunfeldern.
|-
|  || 
|}

== Logik ==

{| border=0
| colspan="3" | <big>Wechseln(Zahl; Wert1; Wert2; ... Wert_keine_Übereinstimmung)</big>
|-
| style="width: 10pt;" |  || valign="top" | Verwendet je nach Zahl Wert1 oder Wert2 oder Wert3, usw. Wenn kein Wert verfügbar ist, wird Wert_keine_Übereinstimmung verwendet.<p>(Schweiz: Wechseln(Zahl, Wert1, Wert2, ... Wert_keine_Übereinstimmung))
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=switch(3, 10, 20, 30, 40, 50, 60, 'no match') returns 30
</pre>
|-
| colspan="3" | <big>IFS((Logik1); Wert1; (Logik2); Wert2; ...; (Logikn); Wertn))</big>
|-
|  || valign="top" | Eines von mehreren möglichen Ergebnissen basierend auf einer Reihe von Abfragen. Der erste Wert, der die Abfrage erfüllt, wird gewählt.<p>(Schweiz: IFS((Logik1), Wert1, (Logik2), Wert2, ..., (Logikn), Wertn)))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=IFS(A4>30, 'yes', A4<=30, 'no') returns 'yes' if the number in the cell A4 is >30. Else, if it is <=30 'no' is returned

If the final LogicN is ELSE then the final ValueN will be applied to all items that do not match a Logic earlier in the list.
=IFS( COND1; VALUE1; COND2; VALUE2; ELSE; 'ELSE' )</pre>
|-
| colspan="3" | <big>Exakt(Wert1; Wert2)</big>
|-
|  || valign="top" | Wahr, wenn beide Werte genau gleich sind. Bei Zeichenketten wird ein Vergleich unter Berücksichtigung der Groß-/Kleinschreibung durchgeführt.<p>(Schweiz: Exakt(Wert1, Wert2))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=exact('text', 'text') returns True, while exact('Text', 'text') will return False.
</pre>
|-
| colspan="3" | <big>IstUngültig(Wert)</big>
|-
|  || valign="top" | Wahr, wenn der Wert ungültig (N/A) ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=IF(IsNA(Angle('energos')), '-', 'has value') On a database row, calculates the Energos angle of the objects, and decides which value to output based on if energos is applicable or not.

Note, you can use IfNA in order to use alternative value only when it's not applicable, the 'Angle' would have to be repeated for the IF function.

</pre>
|-
| colspan="3" | <big>IfUngültig(Wert; Wert_wenn_ungültig)</big>
|-
|  || valign="top" | Wenn der Wert den Inhalt Ungültig (n/a) hat, wird der Inhalt von Wert_wenn_ungültig verwendet, andernfalls der Inhalt von Wert selbst.<p>(Schweiz: IfUngültig(Wert, Wert_wenn_ungültig))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=IfNA(Angle('energos'), '-') On a database row, calculates the Energos angle of the objects, and if they are not applicable, would use '-'

</pre>
|-
| colspan="3" | <big>ErsterNichtLeer(Wert1; Wert2; Wert3; ...) </big>
|-
|  || valign="top" | Wert1 wird verwendet, wenn nicht leer, andernfalls Wert2, sofern nicht leer, sonst Wert3, wenn nicht leer,usw. Leer bedeutet ohne Zeichenkette, Null oder ungültiger (n/a) Wert. Gibt es keine Übereinstimmung wird ungültig (n/a) zurückgegeben.<p>(Schweiz: ErsterNichtLeer(Wert1, Wert2, Wert3, ...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=FirstNonEmpty('Format-1'.'data', B1, 'Empty')

Return the value of the data field of the Format-1, if empty return B1, or the string 'Empty' if that is empty too.

</pre>
|-
| colspan="3" | <big>IstFehler(Wert)</big>
|-
|  || valign="top" | Wahr, wenn der Wert ein Fehler verursacht.
|-
|  || 
|-
| colspan="3" | <big>IfFehler(Fehler; Wert_wenn_Fehler)</big>
|-
|  || valign="top" | Wenn der Wert einen Fehler beinhaltet, wird der Inhalt von Wert_wenn_Fehler verwendet, andernfalls der Inhalt von Wert selbst.<p>(Schweiz: IfFehler(Fehler, Wert_wenn_Fehler))
|-
|  || 
|-
| colspan="3" | <big>if((Bedingung); ‘dann’; ‘sonst’)</big>
|-
|  || valign="top" | Falls (Bsp. “=if((x>75);‘zu teuer’;‘Preis OK’”), d.h. verwende ’dann’, wenn ’Bedingung’ eintritt, verwende ’sonst’, wenn ’Bedingung’ nicht eintritt.<p>(Schweiz if((Bedingung), ‘dann’, ‘sonst’))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition') If no condition value was set for the existing tree object, the value in this cell is a dash; otherwise, the value in this cell is the condition value that was set for the tree object.

=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition')
</pre>
|}

== Math. Formeln ==

{| border=0
| colspan="3" | <big>Runden(x)</big>
|-
| style="width: 10pt;" |  || valign="top" | Rundet die Zahl.
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=round(2.345) returns 2
</pre>
|-
| colspan="3" | <big>sin(x)</big>
|-
|  || valign="top" | Sinus von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=sin(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the sine of the angle
</pre>
|-
| colspan="3" | <big>cos(x)</big>
|-
|  || valign="top" | Cosinus des Winkels x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=cos(deg2rad(23)) converts a 23-degree angle to its radian equivalent, and returns the cosine of the angle
</pre>
|-
| colspan="3" | <big>exp(x)</big>
|-
|  || valign="top" | e hoch x (e=2,71828182845904).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=exp(2) returns the numeric value of e raised to the power of 2
</pre>
|-
| colspan="3" | <big>ln(x)</big>
|-
|  || valign="top" | Der natürliche Logarithmus (Basis e) von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=ln(12) returns the natural logarithm of 12
</pre>
|-
| colspan="3" | <big>Wurzel(x)</big>
|-
|  || valign="top" | Wurzel von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=sqrt(D27) returns the square root of the number in cell D27
</pre>
|-
| colspan="3" | <big>atan(x)</big>
|-
|  || valign="top" | Arcustangens des Winkels x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=atan(A3) returns the angle for which the tangent value is given in cell A3
</pre>
|-
| colspan="3" | <big>radgrad(x)</big>
|-
|  || valign="top" | Konvertiert Radianten in Grad (x Radianten => Resultat in Grad).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=rad2deg(0.5235987) converts the radian angle measurement to its degree equivalent
</pre>
|-
| colspan="3" | <big>gradrad(x)</big>
|-
|  || valign="top" | Konvertiert Grad in Radianten (x Grad => Resultat in Radianten).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=deg2rad(47) converts the 47-degree angle measurement to its radian equivalent
</pre>
|-
| colspan="3" | <big>asin(x)</big>
|-
|  || valign="top" | Arcussinus des Winkels x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=asin(A3) returns the angle for which the sine value is given in cell A3
</pre>
|-
| colspan="3" | <big>acos(x)</big>
|-
|  || valign="top" | Arcuscosinus des Winkels x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=acos(3/5) returns the angle for which the cosine value is 3/5
</pre>
|-
| colspan="3" | <big>Abrunden(x; Dezimalstellen)</big>
|-
|  || valign="top" | Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen ab.<p>(Schweiz: Abrunden(x, Dezimalstellen))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=rounddown(2.345, 2) returns 2.34
</pre>
|-
| colspan="3" | <big>Aufrunden(x; Dezimalstellen)</big>
|-
|  || valign="top" | Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen auf.<p>(Schweiz: Aufrunden(x, Dezimalstellen))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=roundup(2.345, 2) returns 2.35
</pre>
|-
| colspan="3" | <big>Betrag(x)</big>
|-
|  || valign="top" | Der Betrag bzw. absolute Wert ohne Vorzeichen von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=abs(-12) returns the absolute value of the number -12
</pre>
|-
| colspan="3" | <big>Quotient(Divident; Divisor)</big>
|-
|  || valign="top" | Berechnet den Quotienten und den Rest einer ganzzahligen Division.<p>(Schweiz: Quotient(Divident, Divisor))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=quotient(5, 2) returns 2

You can clculate the remainder by using the MOD operator
=5 MOD 2</pre>
|-
| colspan="3" | <big>ggT(x1; x2, …)</big>
|-
|  || valign="top" | Größter gemeinsamer Teiler der Zahlengruppe.<p>(Schweiz: ggT(x1, x2, …))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=gcd(5, 10, 20) returns 5
</pre>
|-
| colspan="3" | <big>kgT(x1; x2; …)</big>
|-
|  || valign="top" | Kleinster gemeinsamer Teiler der Zahlengruppe.<p>(Schweiz: kgT(x1, x2, …))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=lcm(2, 5, 11) returns 110
</pre>
|-
| colspan="3" | <big>Zahlenmitte(x1; x2, …)</big>
|-
|  || valign="top" | Gibt die Mitte der Zahlengruppe zurück.<p>(Schweiz: Zahlenmitte(x1, x2, …))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=median(1, 2, 3, 4, 5, 6) returns 3.5
</pre>
|-
| colspan="3" | <big>logx(x; Basis)</big>
|-
|  || valign="top" | Der Logarithmus zur angegebenen Basis von x.<p>(Schweiz: logx(x, Basis))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=logx(16, 2) returns 4
</pre>
|-
| colspan="3" | <big>Exponent(x; Exponent)</big>
|-
|  || valign="top" | x hoch Exponent.<p>(Schweiz: Exponent(x, Exponent))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=power(10, 3) returns 1000
</pre>
|-
| colspan="3" | <big>WurzelPi(x)</big>
|-
|  || valign="top" | Wurzel (x * pi).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=sqrtpi(3.1415) returns 3.142 (square root of pi*3.1415)
</pre>
|-
| colspan="3" | <big>Quadratsumme(x1; x2; …)</big>
|-
|  || valign="top" | Die Summe der Quadrate der Zahlen.<p>(Schweiz: Quadratsumme(x1, x2, …))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=sumsq(0, 1, 2, 3, 4, 5) returns 55
</pre>
|-
| colspan="3" | <big>Zufallszahlgenerator(x; y)</big>
|-
|  || valign="top" | Eine zufällige Zahl zwischen dem unteren und oberen Wert, einschließlich dem unteren, jedoch nicht dem oberen Wert.<p>(Schweiz: Zufallszahlgenerator(x, y))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=randBetween(10, 100) returns a random number in the range [10, 100]
</pre>
|-
| colspan="3" | <big>Zufallszahl()</big>
|-
|  || valign="top" | Eine zufällige Zahl zwischen 0 und 1, einschließlich der 0, jedoch nicht die 1.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=rand() returns a random number in the range [0, 1)
</pre>
|-
| colspan="3" | <big>Aufrundung(x; [Signifikanz])</big>
|-
|  || valign="top" | Die nächstgelegene Ganzzahl, die nicht kleiner ist als x. Ist ein optionaler Wert (Signifikanz) angegeben, wird auf ein Vielfaches dieses Wertes gerundet.<p>(Schweiz: Aufrundung(x, [Signifikanz]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=ceiling(123.123, 0.01) returns 123.13 (123.123 rounded up to the nearest multiple of 0.01)
</pre>
|-
| colspan="3" | <big>Abrundung(x; [Signifikanz])</big>
|-
|  || valign="top" | Die nächstgelegene Ganzzahl, die nicht größer ist als x. Ist ein optionaler Wert (Signifikanz) angegeben, wird auf ein Vielfaches dieses Wertes gerundet.<p>(Schweiz: Abrundung(x, [Signifikanz]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=floorNum(123.123, 0.01) returns 123.12 (123.123 rounded down to the nearest multiple of 0.01)
</pre>
|-
| colspan="3" | <big>Kürzen(x; [Dezimalstellen])</big>
|-
|  || valign="top" | Kürzt x auf die angegebenen Dezimalstellen.<p>(Schweiz: Kürzen(x, [Dezimalstellen]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=truncate(123.123, 2) returns 123.12
</pre>
|-
| colspan="3" | <big>durchschnitt(x1; x2;...)</big>
|-
|  || valign="top" | Durchschnitt (Mittelwert) der angegebenen Zahlen.<p>(Schweiz: durchschnitt(x1, x2,...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=average(A2,A10..A12) returns the average of the numbers contained in cells A2, A10, A11, and A12
</pre>
|-
| colspan="3" | <big>int(x)</big>
|-
|  || valign="top" | x abgerundet, d.h. ohne Kommastellen (Bsp. “=int(3,87)”; Resultat: “3”).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=int(3.8) returns the value 3
</pre>
|-
| colspan="3" | <big>log(x)</big>
|-
|  || valign="top" | Der Logarithmus zur Basis 10 (log) von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=log(100) returns the base 10 logarithm of 100
</pre>
|-
| colspan="3" | <big>max(x1; x2;...)</big>
|-
|  || valign="top" | Gibt die größte Zahl der Zahlengruppe zurück.<p>(Schweiz: max(x1, x2,...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=max(C5,C7,C9) returns the largest of the numbers that are in cells C5, C7, and C9
</pre>
|-
| colspan="3" | <big>min(x1; x2;...)</big>
|-
|  || valign="top" | Gibt die kleinste Zahl der Zahlengruppe zurück.<p>(Schweiz: min(x1, x2,...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=min(C5,C7,C9) returns the smallest of the numbers that are in cells C5, C7, and C9
</pre>
|-
| colspan="3" | <big>tan(x)</big>
|-
|  || valign="top" | Tangens von x.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=tan(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the tangent of the angle
</pre>
|-
| colspan="3" | <big>sum(x1; x2; ...)</big>
|-
|  || valign="top" | Summe der Zahlen x1, x2, ... usw.<p>(Schweiz: sum(x1, x2, ...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=sum(A2,A10..A12) returns the sum of the numbers contained in cells A2, A10, A11, and A12
</pre>
|}

== Objekte ==

=== Allgemein ===

{| border=0
| colspan="3" | <big>Tiefe([optionale Parameter])</big>
|-
| style="width: 10pt;" |  || valign="top" | Tiefe des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
| style="width: 10pt;" |  || 
|-
| colspan="3" | <big>Gewicht([optionale Parameter])</big>
|-
|  || valign="top" | Gewicht der Objekte. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || 
|-
| colspan="3" | <big>ProjizierteFläche([optionale Parameter])</big>
|-
|  || valign="top" | Projizierte Fläche des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || 
|-
| colspan="3" | <big>Grundfläche([optionale Parameter])</big>
|-
|  || valign="top" | Die Grundfläche des Objekts, z.B. Gebäude. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || 
|-
| colspan="3" | <big>Querschnittsfläche([optionale Parameter])</big>
|-
|  || valign="top" | Querschnittsfläche des Objekts. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück. Die verfügbaren Optionen werden separat aufgelistet.
|-
|  || 
|-
| colspan="3" | <big>FlächeSpezial([optionale Parameter])</big>
|-
|  || valign="top" | Spezialfläche, die üblicherweise durch Parameter definiert ist. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || 
|-
| colspan="3" | <big>ObjektDaten('Beschreibung Klasse')</big>
|-
|  || valign="top" | Beschreibung der Klasse des Objekts.<p>(Schweiz: Objektdaten(Filter, 'Beschreibung Klasse'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Schicht'; <Wert> [; <Schichtindex>])</big>
|-
|  || valign="top" | Bei einem Objekt gibt die Funktion den angegebenen <Wert> der Schicht des Objekts mit dem angegebenen <Schichtindex> zurück, oder die Kernschicht, wenn <Schichtindex> fehlt. Wird die Funktion für eine Schicht aufgerufen, gibt sie den angegebenen <Wert> für diese Schicht zurück. Wenn der optionale <Schichtindex> hinzugefügt wird, gibt die Funktion den Schichtwert nur für Schichten zurück, die mit dem angegebenen Index übereinstimmen.

Die folgenden Werte werden unterstützt: "Name", "Funktion", "Klasse", "Klassenbezeichnung", "Klassenbeschreibung", "Dicke", "Lambda", "Wert", "Nettofläche", "Nettovolumen".

Siehe das Beispiel für weitere Details.<p>(Schweiz: Objektdaten(Filter, 'Schicht', <Wert> [, <Schichtindex>]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Available options for <value>:
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
	
	</pre>
|-
| colspan="3" | <big>Objektdaten('Name')</big>
|-
|  || valign="top" | Name des Objekts. Bei einem Symbol ohne Namen wird der Name der Symboldefinitionsressource zurückgegeben.<p>(Schweiz: Objektdaten(Filter, 'Name'))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectData('General Name')        Returns the name for each object in the DB row.
                                If the object is a symbol, it will return the name of the symbol

Spreadsheet cell:
=ObjectData(SEL=TRUE, 'General Name')    Returns the name for the selected object
                                      If the object is a symbol, it will return the name of the symbol
</pre>
|-
| colspan="3" | <big>Objektdaten(Filter; 'Teilbestand'; part_univ_name; part_index)</big>
|-
|  || valign="top" | Name des Bauteils im Bestand von einem Objekt, das den Bestand unterstützen.<p>(Schweiz: Objektdaten(Filter, 'inventory part', part_univ_name, part_index))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten(Filter; 'Teilbestand Param'; part_univ_name; part_index; param_index)</big>
|-
|  || valign="top" | Wert von Objekteinstellungen eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.<p>(Schweiz: Objektdaten(Filter, 'inventory part param', part_univ_name, part_index, param_index))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten(Filter; Teilbestand quantity'; part_univ_name; part_index)</big>
|-
|  || valign="top" | Menge eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.<p>(Schweiz: Objektdaten(Filter, 'inventory part quantity', part_univ_name, part_index))
|-
|  || 
|-
| colspan="3" | <big>ObjektDaten('Beschreibung Ebene')</big>
|-
|  || valign="top" | Beschreibung der Ebene des Objekts.<p>(Schweiz: Objektdaten(Filter, 'Beschreibung Ebene'))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Objekt Variable'; variable_index)</big>
|-
|  || valign="top" | Objektvariable des Objekts.<p>(Schweiz: Objektdaten(Filter, 'Objektvariable', Variable_Index))
|-
|  || 
|-
| colspan="3" | <big>Objektdaten('Universal_Wert'; Format_Name; Feld_Name, [Ist Format])</big>
|-
|  || valign="top" | Gibt den universellen Wert des angegebenen Feldes des Datensatzes oder des Formats zurück, wenn der optionale Parameter Wahr ist. Es funktioniert mit dem parametrischen Format, wenn Format_Name leer ist. Ergibt Ungültig (N/A), wenn das Objekt nicht mit dem Datensatz verknüpft ist oder das Format nicht existiert.<p>(Schweiz: Objektdaten(Filter, 'Universal_Wert', Format_Name, Feld_Name, [Ist Format]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectData('Universal Value', 'My Format-1', 'data')        Returns the 'data' field for the attached 'My Format-1' for each object in the DB row. Returns N/A if the format or the field is not available.
=ObjectData('Universal Value', 'My Format-1', 'data', True)  Returns the 'data' field for the attached 'My Format-1' for each object in the DB row. Returns N/A if the format or the field is not available.
=ObjectData('Universal Value', '', 'DoorHeight')            Returns the 'DoorHeight' field for each parametric in the DB row. Returns N/A if the field is not avaialble or the object is not a parametric.
=ObjectData('Universal Value', '', 'DoorHeight', True)      Returns the 'DoorHeight' field default value for each parametric in the DB row. Returns N/A if the field is not avaialble or the object is not a parametric.

Spreadsheet cell:
=ObjectData(t=wall, 'Universal Value', 'My Format-1', 'data')        Returns the 'data' field for the attached 'My Format-1' for the wall. Returns N/A if the format or the field is not available.
=ObjectData(t=wall, 'Universal Value', 'My Format-1', 'data', True)  Returns the 'data' field for the attached 'My Format-1' for the wall. Returns N/A if the format or the field is not available.
=ObjectData(PON='Door', 'Universal Value', '', 'DoorHeight')        Returns the 'DoorHeight' field for the parametric object Door. Returns N/A if the field is not avaialble or the object is not a parametric.
=ObjectData(PON='Door', 'Universal Value', '', 'DoorHeight', True)  Returns the 'DoorHeight' field default value the parametric object Door. Returns N/A if the field is not avaialble or the object is not a parametric.
</pre>
|-
| colspan="3" | <big>Objekttyp()</big>
|-
|  || valign="top" | ID-Nummer des Objekttyps.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectType returns the object type value for each object in the database

Spreadsheet cell:
=ObjectType(sel=true) returns the object type value of the selected object; for example, the object type value for a light is 81
</pre>
|-
| colspan="3" | <big>Breite([optionale Parameter])</big>
|-
|  || valign="top" | Breite (Delta x) von Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Width returns the width (delta x) for each object in the database

Spreadsheet cell:
=Width(sel=true) returns the combined width (delta x value) of the selected object
</pre>
|-
| colspan="3" | <big>Höhe([optionale Parameter])</big>
|-
|  || valign="top" | Gibt das Delta y (Höhe) von Objekten zurück. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück. Die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Height returns the height (delta y) for each object in the database

Spreadsheet cell:
=Height(sel=true) returns the combined height (delta y) value of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Zählen([optionale Parameter])</big>
|-
|  || valign="top" | Anzahl von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Count returns the total number of objects for each row in the database

Spreadsheet cell:
=Count(s='simple sofa') returns the total number of symbol objects named “simple sofa” in the drawing

When used with the COUNT function, the SEL (selection status) criterion counts objects that are actually non-selectable, such as the individual items within a group. The VSEL (visible selection status) criterion counts only the visibly selected items, which is the same counting method used for the Object Info palette. For example, if you select and count a group that has 11 items in it, the SEL criterion returns a value of 12 (the group, plus the 11 items). The VSEL criterion returns a value of 1 (the group only).
</pre>
|-
| colspan="3" | <big>Winkel()</big>
|-
|  || valign="top" | Winkel von Geraden und Wänden, Innenwinkel von Kreisbögen (in Grad), Neigungswinkel von Dachflächen, Profilstützen und Böden (in Grad).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Angle returns the angle of each object in the database

Spreadsheet cell:
=Angle((t=arc)&(n='arc-1')) returns the sweep angle of the arc object named “arc-1” in the drawing
</pre>
|-
| colspan="3" | <big>Gespiegelt()</big>
|-
|  || valign="top" | Gibt 1 zurück, wenn das Objekt gespiegelt ist, andernfalls wird 0 zurückgegeben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=IsFlipped returns the flip state for each object in the database

Spreadsheet cell:
=IsFlipped(PON='window') returns the flip state of the window object if it resolves to only one, otherwise returns the total number of window objects in the drawing that are flipped
</pre>
|-
| colspan="3" | <big>xKoordinate()</big>
|-
|  || valign="top" | x-Wert eines Objektes relativ zum Benutzernullpunkt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=XCoordinate returns the x coordinate value for each symbol, point plug-in object, and locus in the database
</pre>
|-
| colspan="3" | <big>yKoordinate()</big>
|-
|  || valign="top" | y-Wert eines Objektes relativ zum Benutzernullpunkt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=YCoordinate returns the y coordinate value for each symbol, point plug-in object, and locus in the database
</pre>
|-
| colspan="3" | <big>zKoordinate()</big>
|-
|  || valign="top" | z-Wert eines Objektes relativ zum Benutzernullpunkt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ZCoordinate returns the z coordinate value for each symbol, point plug-in object, and locus in the database
</pre>
|-
| colspan="3" | <big>Fläche()</big>
|-
|  || valign="top" | Gesamtfläche von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Area returns the area of each object in the database

Spreadsheet cell:
=Area(t=rect) returns the combined area of all rectangle objects in the drawing
</pre>
|-
| colspan="3" | <big>UnterKante()</big>
|-
|  || valign="top" | Am weitesten unten liegender Punkt (kleinster y-Wert) von Objekten in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=BotBound returns the bottom 2D boundary of each object in the database

Spreadsheet cell:
=BotBound(t=locus) returns the bottom 2D boundary of the locus that has the lowest bottom 2D boundary value in the drawing
</pre>
|-
| colspan="3" | <big>OberKante()</big>
|-
|  || valign="top" | Am weitesten oben liegender Punkt (größter y-Wert) von Objekten in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=TopBound returns the top 2D boundary for each object in the database

Spreadsheet cell:
=TopBound(sel=true) returns the top 2D boundary of the topmost selected object
</pre>
|-
| colspan="3" | <big>LinkeKante()</big>
|-
|  || valign="top" | Am weitesten links liegender Punkt (kleinster x-Wert) von Objekten in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=LeftBound returns the left 2D boundary for each object in the database

Spreadsheet cell:
=LeftBound(t=locus) returns the left 2D boundary of the leftmost locus in the drawing
</pre>
|-
| colspan="3" | <big>RechteKante()</big>
|-
|  || valign="top" | Am weitesten rechts liegender Punkt (größter x-Wert) von Objekten in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=RightBound returns the right 2D boundary for each object in the database

Spreadsheet cell:
=RightBound(t=rect) returns the right 2D boundary of the rightmost rectangle in the drawing
</pre>
|-
| colspan="3" | <big>Umfang([optionale Parameter])</big>
|-
|  || valign="top" | Umfang des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Perim returns the perimeter for each object in the database

Spreadsheet cell:
=Perim(sel=true) returns the total perimeter of all selected objects</pre>
|-
| colspan="3" | <big>Länge([optionale Parameter])</big>
|-
|  || valign="top" | Länge von Geraden und Wänden in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Length returns the length for each object in the database

Spreadsheet cell:
=Length(t=line) returns the total length of all line objects in the drawing
</pre>
|-
| colspan="3" | <big>xMitte()</big>
|-
|  || valign="top" | Mittelpunkt von Objekten in der Zeichnung in x-Richtung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=XCenter returns the x coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=XCenter(sel=true) returns the x coordinate value of the center of the 2D boundary of the selected object
</pre>
|-
| colspan="3" | <big>yMitte()</big>
|-
|  || valign="top" | Mittelpunkt von Objekten in der Zeichnung in y-Richtung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=YCenter returns the y coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=YCenter(sel=true) returns the y coordinate value of the center of the 2D boundary of the selected object
</pre>
|-
| colspan="3" | <big>zMitte()</big>
|-
|  || valign="top" | Mittelpunkt von Objekten in der Zeichnung in z-Richtung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ZCenter returns the z coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=ZCenter(sel=true) returns the z coordinate value of the center of the 2D boundary of the selected object
</pre>
|-
| colspan="3" | <big>Oberfläche([optionale Parameter])</big>
|-
|  || valign="top" | Oberfläche von 3D-Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SurfaceArea returns the surface area for each object in the database

Spreadsheet cell:
=SurfaceArea(st=sphere) returns the total surface area of all sphere objects in the drawing
</pre>
|-
| colspan="3" | <big>Volumen([optionale Parameter])</big>
|-
|  || valign="top" | Volumen des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Volume returns the volume for each object in the database

Spreadsheet cell:
=Volume(t=xtrd) returns the total volume of all extrude objects in the drawing
</pre>
|-
| colspan="3" | <big>Grafik()</big>
|-
|  || valign="top" | Grafische Abbildung von Objekten in der Zeichnung.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Image returns the image for each object in the database

Spreadsheet cell:
=Image(s='cabinet') returns the image of the symbol named “Cabinet”
</pre>
|-
| colspan="3" | <big>ObjU-Wert()</big>
|-
|  || valign="top" | U-Wert der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectUValue returns the U-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectUValue(n='wall-1') returns the U-value for the wall named “wall-1”</pre>
|-
| colspan="3" | <big>ObjR-Wert()</big>
|-
|  || valign="top" | R-Wert der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectRValue returns the R-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectRValue(n='wall-1') returns the R-value for the wall named “wall-1”
</pre>
|-
| colspan="3" | <big>ObjInEnergos()</big>
|-
|  || valign="top" | Gibt den Wert 1 zurück, wenn das Objekt in den Energieberechnungen berücksichtigt wird. Andernfalls wird der Wert 0 Zurückgegeben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjIncludeInEnergos returns the Energos status for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjIncludeInEnergos(t=wall) returns the Energos status for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Stilname()</big>
|-
|  || valign="top" | Gibt den Stilnamen zurück, der vom Objekt verwendet wird.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=PluginStyleName returns the plug-in style name for each object in the database

Spreadsheet cell:
=PluginStyleName(sel=true) returns the plug-in style name for all selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Ebene()</big>
|-
|  || valign="top" | Name der Ebene der Objekt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Layer returns the layer name of each object in the database

Spreadsheet cell:
=Layer(sel=true) returns the layer name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Klasse()</big>
|-
|  || valign="top" | Name der Klasse der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Class returns the class name of each object in the database

Spreadsheet cell:
=Class(sel=true) returns the class name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>ObjektTypName()</big>
|-
|  || valign="top" | Name der Objekttypen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectTypeName returns the type name for each object in the database

Spreadsheet cell:
=ObjectTypeName(sel=true) returns the type name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Name()</big>
|-
|  || valign="top" | Name der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Name returns the name for each object in the database

Spreadsheet cell:
=Name(sel=true) returns the name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Geschoss()</big>
|-
|  || valign="top" | Name des Geschosses, auf welchem die Objekte liegen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Story returns the story name for each object in the database

Spreadsheet cell:
=Story(sel=true) returns the story name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Mosaikfüllung()</big>
|-
|  || valign="top" | Name des Mosaiks, mit dem die Objekte gefüllt sind.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=TileFill returns the tile fill name for each object in the database

Spreadsheet cell:
=TileFill(sel=true) returns the tile fill name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Schraffurfüllung()</big>
|-
|  || valign="top" | Name der Schraffur, mit der die Objekte gefüllt sind.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=HatchFill returns the hatch fill name for each object in the database

Spreadsheet cell:
=HatchFill(sel=true) returns the hatch fill name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Verlauffüllung()</big>
|-
|  || valign="top" | Name des Verlaufs, mit dem die Objekte gefüllt sind.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=GradientFill returns the gradient fill name for each object in the database

Spreadsheet cell:
=GradientFill(sel=true) returns the gradient fill name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Objekttextur()</big>
|-
|  || valign="top" | Name der Textur, das den Objekten zugewiesen ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ObjectTexture returns the texture name of each object in the database

Spreadsheet cell:
=ObjectTexture(sel=true) returns the texture name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Skizzenstil()</big>
|-
|  || valign="top" | Name des Skizzenstils der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SketchStyle returns the sketch style name for each object in the database

Spreadsheet cell:
=SketchStyle(sel=true) returns the sketch style name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Linienart()</big>
|-
|  || valign="top" | Name der Linienart der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=LineType returns the line type name for each object in the database

Spreadsheet cell:
=LineType(sel=true) returns the line type name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>Bildfüllung()</big>
|-
|  || valign="top" | Name der Bildfüllung der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ImageFill returns the image fill name for each object in the database

Spreadsheet cell:
=ImageFill(sel=true) returns the image fill name of the selected objects in the drawing
</pre>
|-
| colspan="3" | <big>GetCOBieSource(Tabellenname.Spaltenname.Land.Version)</big>
|-
|  || valign="top" | Gibt die Datenquelle einer COBie-Eigenschaft (COBie property) eines Objekts zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=GETCOBIESOURCE ('space.floorname') returns the FloorName data source for objects whose COBie property is Space
</pre>
|-
| colspan="3" | <big>GetCOBieProperty(Tabellenname.Spaltenname.Land.Version)</big>
|-
|  || valign="top" | Gibt den Wert einer COBie-Eigenschaft (COBie property) zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=GETCOBIEPROPERTY ('space.floorname') returns the FloorName value for objects whose COBie property is Space
</pre>
|-
| colspan="3" | <big>Symbolname()</big>
|-
|  || valign="top" | Name des Symbols.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=SymbolName returns the name for each symbol instance in the database

Spreadsheet cell:
=SymbolName(sel=true) returns the symbol name of the selected symbol instances in the drawing
</pre>
|-
| colspan="3" | <big>DatenstempelFeld(Feldname)</big>
|-
|  || valign="top" | Gibt den Wert des angegebenen Feldes für die Datenstempelobjekte zurück. Feldname ist der Name des Feldes im Datenstempellayout.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=DataTagField('Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for each data tag in the database.

Spreadsheet cell:
=DataTagField(sel=true, 'Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for the selected data tag in the drawing.
</pre>
|-
| colspan="3" | <big>Grafik_Ansichtsber(Ansichtsbereichsname)</big>
|-
|  || valign="top" | Erstellt ein Bild der Objekte mit dem Farbschema des angegebenen Ansichtsbereichs.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Imagebyviewport('Plan A') applies the data visualizations from the viewport named “Plan A” to each image in the database 

Spreadsheet cell:
=Imagebyviewport('Space Allocation') applies the data visualization from the viewport named “Space Allocation” to the image in the cell
</pre>
|-
| colspan="3" | <big>Grafik_Datenvis(DatenvisName)</big>
|-
|  || valign="top" | Erstellt ein Bild des Objekts mit dem Farbschema des angegebenen Ansichtsbereichs.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=Imagebydatavis('truss by type') applies the “truss by type” data visualization to each image in the database rows

Spreadsheet cell:
=Imagebydatavis('offices') applies the data visualization named “offices” to the image in the cell
</pre>
|-
| colspan="3" | <big>xRotation()</big>
|-
|  || valign="top" | Der Rotationswinkel (in Grad) um die x-Achse der Objekte.
|-
|  || 
|-
| colspan="3" | <big>yRotation()</big>
|-
|  || valign="top" | Der Rotationswinkel (in Grad) um die y-Achse der Objekte.
|-
|  || 
|-
| colspan="3" | <big>zRotation()</big>
|-
|  || valign="top" | Der Rotationswinkel (in Grad) um die z-Achse der Objekte, auf die der Filter verweist.
|-
|  || 
|-
| colspan="3" | <big>UnterobjektName()</big>
|-
|  || valign="top" | Gibt den Namen der Unterobjekte zurück. Gibt den Namen des Objekttyps zurück, wenn das Objekt kein Unterobjekt ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=PartTypeName returns the part type name for each subpart object in the database. if the database object is not a subpart, the object type name is returned

</pre>
|-
| colspan="3" | <big>Füllvordergrundfarbe()</big>
|-
|  || valign="top" | Die Vordergrundfarbe der Füllung des Objekts, auf die der Filter verweist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=FillForeColor returns the name of the fill foreground color for each object in the database

Spreadsheet cell:
=FillForeColor(t=rect) returns the name of the fill foreground color of the rectangle object
</pre>
|-
| colspan="3" | <big>Füllhintergrundfarbe()</big>
|-
|  || valign="top" | Die Hintergrundfarbe der Füllung des Objekts.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=FillBackColor returns the name of the fill background color for each object in the database

Spreadsheet cell:
=FillBackColor(t=rect) returns the name of the fill background color of the rectangle object
</pre>
|-
| colspan="3" | <big>Stiftvordergrfarbe()</big>
|-
|  || valign="top" | Die Vordergrundfarbe des Stifts des Objekts.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=PenForeColor returns the name of the pen foreground color for each object in the database

Spreadsheet cell:
=PenForeColor(t=rect) returns the name of the pen foreground color of the rectangle object
</pre>
|-
| colspan="3" | <big>Stifthintergrfarbe() </big>
|-
|  || valign="top" | Die Hintergrundfarbe des Stifts des Objekts.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=PenBackColor returns the name of the pen background color for each object in the database

Spreadsheet cell:
=PenBackColor(t=rect) returns the name of the pen background color of the rectangle object
</pre>
|-
| colspan="3" | <big>AnsichtsberStilname()</big>
|-
|  || valign="top" | Der Name des vom Objekt verwendeten Ansichtsbereichstils
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ViewportStyleName returns the viewport style name for each viewport object in the database

Spreadsheet cell:
=ViewportStyleName(n='viewport-1') returns the viewport style name for the object named “viewport-1”
</pre>
|}

=== Auslaufende Funktionen ===

{| border=0
| colspan="3" | <big>Schichtfläche(Index)</big>
|-
| style="width: 10pt;" |  || valign="top" | Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentArea(2) returns the combined area of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentArea(t=wall,1) returns the combined area of the first components for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtvolumen(Index)</big>
|-
|  || valign="top" | Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentVolume(2) returns the combined volume of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentVolume(t=wall,1) returns the combined volume of the first components for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtname(Index)</big>
|-
|  || valign="top" | Name einer Schicht.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentName(2) returns the name of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentName(t=wall,1) returns the name of the first component for all walls in the drawing
</pre>
|-
| colspan="3" | <big>IFCEigenschaft(Eigenschaftenset.Eigenschaft)</big>
|-
|  || valign="top" | Eigenschaft (property field) von IFC-Daten (instance). Beispiel: IFC-Eigenschaft(‘IfcWallStandardCase.Description’).
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=GETIFCPROPERTY ('ifcfurnishingelement.name') returns the Name value for IFC objects whose IFC entity is IfcFurnishingElement 
</pre>
|-
| colspan="3" | <big>SchichtLambda(Index)</big>
|-
|  || valign="top" | Lambda-Wert der Schicht.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentLambda(2) returns the Lambda value of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentLambda(t=wall,1) returns the Lambda value of the first component for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtU-Wert(Index)</big>
|-
|  || valign="top" | U-Wert der Schicht.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentUValue(2) returns the combined U-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentUValue(t=wall,1) returns the combined U-values of the first components for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtR-Wert(Index)</big>
|-
|  || valign="top" | R-Wert der Schicht.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentRValue(2) returns the combined R-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentRValue(t=wall,1) returns the combined R-values of the first components for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtDicke(Index)</big>
|-
|  || valign="top" | Die Dicke der Schicht.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentThickness(2) returns the combined thickness of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentThickness(t=wall,1) returns the combined thickness of the first components for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtfläche_Klasse(Klasse)</big>
|-
|  || valign="top" | Fläche der von der Klasse bestimmten Schichten, abzüglich aller Öffnungen. Liegen mehrere Schichten in der Klasse, werden die Flächen addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompAreaByClass('Class-1') returns the combined area of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByClass(t=wall,'Class-1') returns the combined area of the components assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtLambda_Klasse(Klasse)</big>
|-
|  || valign="top" | Lambda-Wert vonderKlasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Wert der ersten gefundenen Schicht angezeigt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompLambdaByClass('Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByClass(t=wall,'Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtname_Klasse(Klasse)</big>
|-
|  || valign="top" | Der Name von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Name der ersten gefundenen Schicht angezeigt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompNameByClass('Class-1') returns the name of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByClass(t=wall,'Class-1') returns the name of the first component assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtRWert_Klasse(Klasse)</big>
|-
|  || valign="top" | Der R-Wert einer von der Klasse bestimmten Schicht. Liegen mehrere Schichten in der Klasse, werden die R-Werte der Schichten addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompRValueByClass('Class-1') returns the combined R-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByClass(t=wall,'Class-1') returns the combined R-values of the components assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtdicke_Klasse(Klasse)</big>
|-
|  || valign="top" | Dicke der von der Klasse bestimmen Schicht. Liegen mehrere Schichten in der Klasse, werden die Dicken addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompThicknessByClass('Class-1') returns the combined thickness of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByClass(t=wall,'Class-1') returns the combined thickness of the components assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtUWert_Klasse(Klasse)</big>
|-
|  || valign="top" | Der U-Wert der von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, werden die U-Werte der Schichten addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompUValueByClass('Class-1') returns the combined U-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByClass(t=wall,'Class-1') returns the combined U-values of the components assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtvol_Klasse(Klasse)</big>
|-
|  || valign="top" | Volumen der Schichten, die in der angegebenen Klasse liegen. Liegen mehrere Schichten in der Klasse, werden die Volumen addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompVolumeByClass('Class-1') returns the combined volume of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByClass(t=wall,'Class-1') returns the combined volume of the components assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtfläche_Name(Name)</big>
|-
|  || valign="top" | Fläche der vom Namen bestimmen Schicht, abzüglich aller Öffnungen. Haben mehrere Schichten den gleichen Namen, werden die Flächen addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompAreaByName('Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByName(t=wall,'Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtLambda_Name(Name)</big>
|-
|  || valign="top" | Lambda-Wert einer Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, wird der Wert der ersten Schicht angezeigt, die gefunden wird.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompLambdaByName('Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByName(t=wall,'Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtklasse_Name(Name)</big>
|-
|  || valign="top" | Die Klasse der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, wird die Klasse der ersten gefundenen Schicht angezeigt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompClassByName('Brick Veneer') returns the class of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByName(t=wall,'Brick Veneer') returns the class of the first component with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtRWert_Name(Name)</big>
|-
|  || valign="top" | Der R-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die R-Werte der Schichten addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompRValueByName('Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByName(t=wall,'Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtdicke_Name(Name)</big>
|-
|  || valign="top" | Dicke der Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, werden die Dicken addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompThicknessByName('Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByName(t=wall,'Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtUWert_Name(Name)</big>
|-
|  || valign="top" | Der U-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die U-Werte der Schichten addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompUValueByName('Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByName(t=wall,'Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtvolumen_Name(Name)</big>
|-
|  || valign="top" | Volumen der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die Volumen addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompVolumeByName('Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByName(t=wall,'Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtmat_Klasse(Klasse)</big>
|-
|  || valign="top" | Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten dieselbe Klasse verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompMatByClass('Class-1') returns the materials used by the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByClass(t=wall,'Class-1') returns the material used by the first component assigned to the class “Class-1” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtmaterial_Name(Name)</big>
|-
|  || valign="top" | Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten denselben Namen verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompMatByName('Siding') returns the materials used by the first component with the name “Siding” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByName(t=wall,'Siding') returns the material used by the first component with the name “Siding” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtfläche_Mat(Material)</big>
|-
|  || valign="top" | Die Fläche einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompAreaByMat('Mortar MT') returns the combined area of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByMat(t=wall, 'Mortar MT') returns the combined area of the components that use the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtklasse_Mat(Material)</big>
|-
|  || valign="top" | Die Klasse der Wand-, Boden/Decke- oder Dachschichen. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird die Klasse der ersten Schicht zurückgegeben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompClassByMat('Mortar MT') returns the class of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByMat(t=wall, 'Mortar MT') returns the class of the first component that uses the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtlamdba_Mat(Material)</big>
|-
|  || valign="top" | Der Lambdawert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Lambdawert der ersten Schicht zurückgegeben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompLambdaByMat('Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByMat(t=wall,'Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtname_Material(Material)</big>
|-
|  || valign="top" | Der Name der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Name der ersten Schicht zurückgegeben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompNameByMat('Mortar MT') returns the name of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByMat(t=wall,'Mortar MT') returns the name of the first component that uses the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtRWert_Mat(Material)</big>
|-
|  || valign="top" | Der R-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompRValueByMat('Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByMat(t=wall,'Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtdicke_Mat(Material)</big>
|-
|  || valign="top" | Die Dicke der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompThicknessByMat('Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByMat(t=wall,'Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>SchichtUWert_Mat(Material)</big>
|-
|  || valign="top" | Der U-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompUValueByMat('Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByMat(t=wall,'Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtvolumen_Mat(Material)</big>
|-
|  || valign="top" | Das Volumen einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=CompVolumeByMat('Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByMat(t=wall,'Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for all walls in the drawing
</pre>
|}

=== Material ===

{| border=0
| colspan="3" | <big>MaterialName()</big>
|-
| style="width: 10pt;" |  || valign="top" | Material der Objekte.
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialName returns the names of materials in objects for each row in the database

Spreadsheet cell:
=MaterialName(t=SOLIDCSG) returns the names of materials in generic solids in the drawing
</pre>
|-
| colspan="3" | <big>MaterialZählen()</big>
|-
|  || valign="top" | Anzahl an Materialien der Objekte.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialCount returns the total number of materials in objects for each row in the database

Spreadsheet cell:
=MaterialCount(t=SOLIDCSG) returns the total number of materials in generic solids in the drawing
</pre>
|-
| colspan="3" | <big>MaterialTextur()</big>
|-
|  || valign="top" | Gibt den Namen der Texturzuweisung des Materials für Objekte zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialTexture returns the texture of the material assigned to objects for each row in the database

Spreadsheet cell:
=MaterialTexture(t=SOLIDCSG) returns the texture of the material assigned to the generic solid in the drawing
</pre>
|-
| colspan="3" | <big>MaterialDatenfeld_Name(Materialname; IFC-Datenfeld)</big>
|-
|  || valign="top" | Gibt das angegebene IFC-Datenfeld für das angegebene Material zurück.<p>(Schweiz: MaterialDatenfeld_Name(Materialname, IFC-Datenfeld))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Spreadsheet cell:
=MatPropertyByName('Mortar MT','MaterialFinish') returns the material finish property for the material “Mortar MT”
</pre>
|-
| colspan="3" | <big>MaterialIstEinfach()</big>
|-
|  || valign="top" | Gibt den booleschen Wert Wahr zurück, wenn das Material der Objekte ein einfaches Material ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialIsSimple returns TRUE if the material of the object referenced by the database row is a simple material.

Spreadsheet cell:
=MaterialIsSimple(t=SOLIDCSG) returns TRUE if the material of the generic solid in the drawing is a simple material.
</pre>
|-
| colspan="3" | <big>MaterialBauteilname(Materialname)</big>
|-
|  || valign="top" | Der Name des Bauteils, dem das Material zugewiesen ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialPartName('Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for each row in the database

Spreadsheet cell:
=MaterialPartName(t=wall, 'Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for walls in the drawing
</pre>
|-
| colspan="3" | <big>MaterialOberfläche() </big>
|-
|  || valign="top" | Die Oberfläche der Objekte mit dem angegebenen Material.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialSurfaceArea('Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialSurfaceArea(t=wall,'Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>MaterialVolumen()</big>
|-
|  || valign="top" | Das Volumen der Objekte mit dem angegebenen Material.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialVolume('Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialVolume(t=wall,'Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>MaterialProzent(Materialname)</big>
|-
|  || valign="top" | Der prozentuale Anteil des Material, das Objekten zugewiesen ist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=MaterialPercent('Mortar MT') returns the percentage of the material “Mortar MT” in all objects for each row in the database

Spreadsheet cell:
=MaterialPercent(t=wall,'Mortar MT') returns the percentage of the material “Mortar MT” for all walls in the drawing
</pre>
|-
| colspan="3" | <big>Schichtmaterial(Index)</big>
|-
|  || valign="top" | Das Material der Schichten, auf die der Filter verweist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
=ComponentMaterial(2) returns the material used by the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentMaterial(t=wall,1) returns the material used by the first component for all walls in the drawing
</pre>
|-
| colspan="3" | <big>MaterialDatenfeld(IFC-Datenfeld)</big>
|-
|  || valign="top" | Gibt das angegebene IFC-Datenfeld für das  Material zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">Database header cell:
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
</pre>
|}

== Tabellensuche ==

{| border=0
| colspan="3" | <big>VTabellensuche(Zelle; [opt_Param]; Erg_Spaltenindex; nicht_gefunden; Zellenbereich)</big>
|-
| style="width: 10pt;" |  || valign="top" | Sucht den Inhalt aus der Zelle in der ersten Spalte des Zellenbereich. Als Ergebnis wird der Wert aus der Spalte des Zellenbereichs genommen, der in Erg_Spaltenindex angegeben ist. Verwendet ECMAScript syntax für die Textverarbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript (Schweiz: VTabellensuche(Zelle, [opt_Param], Erg_Spaltenindex, nicht_gefunden, Zellenbereich))
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=VLookup(value, [use_pattern], result_col_index, not_found_value, table)

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
And here is a web-tool that can help developing and testing regular expressions: https://regexr.com/</pre>
|-
| colspan="3" | <big>XTabellensuche(Zelle; [opt_Param]; nicht_gefunden; Zellenbereich_Such; Zellenbereich_Erg)</big>
|-
|  || valign="top" | Sucht den Inhalt der Zelle im Zellenbereich_Such und gibt den Inhalt der gefundenen Zelle aus Zellenbereich_Erg zurück. Die Zellenbereiche dürfen nur eine Spalte haben. Verwendet ECMAScript syntax für die Textverarbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript (Schweiz: XTabellensuche(Zelle, [opt_Param], nicht_gefunden, Zellenbereich_Such, Zellenbereich_Erg))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=XLookup(value, [use_pattern], not_found_value, array_lookup, array_result)

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
And here is a web-tool that can help developing and testing regular expressions: https://regexr.com/</pre>
|}

== Text ==

{| border=0
| colspan="3" | <big>Verketten(Text1; Text2;...)</big>
|-
| style="width: 10pt;" |  || valign="top" | Verknüpft einzelne Texte zu einem gesamten Text.<p>(Schweiz: Verketten(Text1, Text2,...))
|-
| style="width: 10pt;" |  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=concat(B3,', ',B4) returns the contents of cells B3 and B4 as a single string, separated by a comma and a space
</pre>
|-
| colspan="3" | <big>Teilstring(Text; Trennzeichen; Index)</big>
|-
|  || valign="top" | Zerlegt einen Text an den Trennzeichen in einzelne Teiltexte. Der Index bestimmt den Teiltext.<p>(Schweiz: Teilstring(Text, Trennzeichen, Index))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=SUBSTRING('kitchen;bedroom;bathroom;basement', ';', 2) returns “bedroom,” which is the second substring in the specified string
</pre>
|-
| colspan="3" | <big>txt(Wert; ZuEinheit; [Param1]; [Param2]; ...)</big>
|-
|  || valign="top" | Verwandelt einen numerischen Wert von Dokumenteinheiten in die angegebene Einheit und gibt eine String-Darstellung zurück, wobei die Optionen zur Formatierung verwendet werden. Weitere Informationen finden Sie im Beispiel.<p>(Schweiz: txt(Wert, ZuEinheit, [Param1], [Param2], ...))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">The first parameter must be <ToUnit> and then a list of optional parameters to fine tune the conversion.

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

- <optional param> - Units di</pre>
|-
| colspan="3" | <big>IstAlphanum(Text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge alphanumerisch sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isalnum('word123') returns True
</pre>
|-
| colspan="3" | <big>IstText(Text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge Buchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isalpha('word') returns True
</pre>
|-
| colspan="3" | <big>IstZahl(Text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge Zahlen sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isdigit('1234') returns True
</pre>
|-
| colspan="3" | <big>IstKleinbuchstaben(text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge Kleinbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben Wahr zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=islower('does not have upper char') returns True
</pre>
|-
| colspan="3" | <big>IstLeerzeichen(Text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge Leerzeichen sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isspace('      ') returns True
</pre>
|-
| colspan="3" | <big>IstWörterGroß(Text)</big>
|-
|  || valign="top" | Wahr, wenn jedes Wort mit einem Großbuchstaben beginnt andernfalls Falsch.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isTitle('This Is Title Text') returns True
</pre>
|-
| colspan="3" | <big>IstGroßbuchstaben(Text)</big>
|-
|  || valign="top" | Wahr, wenn alle Zeichen in der Zeichenfolge Großbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben Wahr zurück.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=isUpper('DOES NOT HAVE LOWER CHARS') returns True
</pre>
|-
| colspan="3" | <big>TextVerketten(Trennzeichen; Text1; Text2; …)</big>
|-
|  || valign="top" | Verknüpft einzelne Text zu einem Text, wobei das angegebene Trennzeichen zwischen die einzelnen Texte gesetzt wird.<p>(Schweiz: TextVerketten(Trennzeichen, Text1, Text2, …))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=textJoin(', ', 1, 2, 3) returns '1, 2, 3'
</pre>
|-
| colspan="3" | <big>Kleinbuchstaben(Text)</big>
|-
|  || valign="top" | Alle Buchstaben des Textes werden in Kleinbuchstaben verwandelt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=lower('MAKE THIS LOWER') returns 'make this lower'
</pre>
|-
| colspan="3" | <big>WegschneidenLinks(Text; [Zeichen])</big>
|-
|  || valign="top" | Entfernt die angegebenen Zeichen von links aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.<p>(Schweiz: WegschneidenLinks(Text, [Zeichen]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=trimLeft('abbcwordabbc', 'abc') returns 'wordabbc'
</pre>
|-
| colspan="3" | <big>Ersetzen(Text; altText; neuText; [Anzahl])</big>
|-
|  || valign="top" | Alle Vorkommen des Teiltextes altText werden durch neuText ersetzt. Wenn der optionale Parameter verwendet wird, werden nur so viele Vorkommen ersetzt, wie angegeben.<p>(Schweiz: Ersetzen(Text, altText, neuText, [Anzahl]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=replace('my car is your car', 'car', 'ball', 2) returns 'my car is your ball'
</pre>
|-
| colspan="3" | <big>WegschneidenRechts(Text; [Zeichen])</big>
|-
|  || valign="top" | Entfernt die angegebenen Zeichen von rechts aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.<p>(Schweiz: WegschneidenRechts(Text, [Zeichen]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=trimRight('abbcwordabbc', 'abc') returns 'abbcword'
</pre>
|-
| colspan="3" | <big>Wegschneiden(Text; [Zeichen])</big>
|-
|  || valign="top" | Entfernt die angegebenen Zeichen von beiden Seiten aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.<p>(Schweiz: Wegschneiden(Text, [Zeichen]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=trim('abbcwordabbc', 'abc') returns 'word'
</pre>
|-
| colspan="3" | <big>Großschreiben(Text)</big>
|-
|  || valign="top" | Jedes Wort wird mit einem großen Anfangsbuchstaben geschrieben.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=proper('make this title text') returns 'Make This Title Text'
</pre>
|-
| colspan="3" | <big>Großbuchstaben(Text)</big>
|-
|  || valign="top" | Alle Buchstaben des Textes werden in Großbuchstaben verwandelt.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=upper('make this upper') returns 'MAKE THIS UPPER'
</pre>
|-
| colspan="3" | <big>Länge(Text)</big>
|-
|  || valign="top" | Die Länge des Textes.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=len('hello there') returns 11
 </pre>
|-
| colspan="3" | <big>Einfügen(Text; Index; Einfügetext)</big>
|-
|  || valign="top" | Fügt den Einfügetext an der mit Index bezeichneten Stelle in den Text ein.<p>(Schweiz: Einfügen(Text, Index, Einfügetext))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=insert('hey, this is ok', 12, ' not') returns 'hey, this is not ok'
</pre>
|-
| colspan="3" | <big>Links(Text; Index)</big>
|-
|  || valign="top" | Die linke Seite des Textes bis zur Position Index.<p>(Schweiz: Links(Text, Index))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=left('this is sample', 4) returns 'this'
</pre>
|-
| colspan="3" | <big>Rechts(Text; Anzahl)</big>
|-
|  || valign="top" | Die Zeichen von der rechten Seite des Textes.<p>(Schweiz: Rechts(Text, Anzahl))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=right('this is sample', 6) returns 'sample'
</pre>
|-
| colspan="3" | <big>Mitte(Text; Index; Anzahl)</big>
|-
|  || valign="top" | Gibt einen Teiltext zurück, der bei Index beginnt und die Länge hat, die in Anzahl angeben ist. Ist Index negativ, wird die Startposition des Teilstrings vom Ende des Textes rückwärts bestimmt. Mitte(Text, Index, Anzahl)
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=mid('apple', 2, 3) returns 'ppl'
=mid('apple', -4, 3) looking the index backwards, returns 'ppl'
=mid('apple', 4, -3) getting characters backward from the index, returns 'ppl</pre>
|-
| colspan="3" | <big>Löschen(Text; Index; Anzahl)</big>
|-
|  || valign="top" | Teilstring, der an der Position Index beginnt und die Länge Anzahl hat.<p>(Schweiz: Löschen(Text, Index, Anzahl))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=delete('this is sample', 4, 3) returns 'this sample'. Here 3 characters after the 4th are deleted.
</pre>
|-
| colspan="3" | <big>Anführungszeichen(Text)</big>
|-
|  || valign="top" | Setzt einen Text in Anführungszeichen.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=quote('quote this') returns "quote this" (The text, in double quotes)
</pre>
|-
| colspan="3" | <big>Wdh(Text; Anzahl)</big>
|-
|  || valign="top" | Wiederholt den Text so oft, wie angegeben.<p>(Schweiz: Wdh(Text, Anzahl))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=rept('Line ', 3) returns 'Line Line Line '
</pre>
|-
| colspan="3" | <big>FesteDezimalstellen(Zahl; [Dezimalstellen])</big>
|-
|  || valign="top" | Formatiert eine Zahl als Text mit einer festen Anzahl von Nachkommastellen.<p>(Schweiz: FesteDezimalstellen(Zahl, [Dezimalstellen]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=fixed(10.12345, 3) returns 10.123 (up to the 3rd digit after the decimal point)
</pre>
|-
| colspan="3" | <big>NullenVoranstellen(Zahl; Dezimalstellen)</big>
|-
|  || valign="top" | Die numerische Zeichenfolge werden Nullen bis zum Erreichen der Anzahl der Dezimalstellen vorangestellt. Wenn ein kleinerer Wert für die Dezimalstellen angegeben wird als die Zeichenfolge besitzt, bleibt die Zeichenfolge unverändert.<p>(Schweiz: NullenVoranstellen(Zahl, Dezimalstellen))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=justNum(10.123, 8) returns '0010.123'
</pre>
|-
| colspan="3" | <big>Char(Zahl)</big>
|-
|  || valign="top" | Das Unicode-Zeichen oder die Textdarstellung (U+1234), auf die die angegebene Zahl verweist.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=char(8734) returns the symbol ∞
=char('U+221E') also returns ∞
</pre>
|-
| colspan="3" | <big>Code(Text)</big>
|-
|  || valign="top" | Die Nummer (Unicode-Codepunkt) für das erste Zeichen im Text.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=code('∞') returns 8734. The unicode codepoint for ∞
</pre>
|-
| colspan="3" | <big>Suchen(Teiltext; Text; [GroßKleinschreibung])</big>
|-
|  || valign="top" | Die erste Stelle (Index) im Text, an der der Teiltext gefunden wird. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf Wahr gesetzt ist. Das Ergebnis ist -1, wenn der Teiltext nicht gefunden wird.<p>(Schweiz: Suchen(Teiltext, Text, [GroßKleinschreibung]))
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=find('text', 'this is text') returns 8
</pre>
|-
| colspan="3" | <big>SuchenSuchbegriff(Suchbegriff; Text; [GroßKleinschreibung])</big>
|-
|  || valign="top" | Die erste Stelle (Index) im Text, an der der Suchbegriff gefunden wird. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf Wahr gesetzt ist. Der Suchbegriff ist eine Folge von Zeichen, die ein Suchmuster angibt. Das Ergebnis ist -1, wenn der Begriff nicht gefunden wird. Verwendet ECMAScript-Syntax für die Textbearbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript (Schweiz: SuchenSuchbegriff(Suchbegriff, Text, [GroßKleinschreibung])
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=findPattern('(Soft)(.*)', 'soft Software', True) returns 5
</pre>
|-
| colspan="3" | <big>Wert(text)</big>
|-
|  || valign="top" | Konvertiert einen Text, der eine Zahl darstellt, in eine Zahl.
|-
|  || valign="top" | <pre style="white-space:-moz-pre-wrap; white-space:-pre-wrap; white-space:-o-pre-wrap; white-space:pre-wrap; word-wrap:break-word;">=value('2e3') returns the numeric value of 2 times 10 raised to the power of 3
</pre>
|}
