Tabellenfunktionen

Stand: Vectorworks 2025 Update 5 (810264)

## Contents
- [Allgemein](#allgemein)
- [Funktionen für Adapter](#funktionen-für-adapter)
- [Funktionen für Anschluss](#funktionen-für-anschluss)
- [Funktionen für Arbeitsplatte](#funktionen-für-arbeitsplatte)
- [Funktionen für Assembly Frame Segment](#funktionen-für-assembly-fürame-segment)
- [Funktionen für Aussparung](#funktionen-für-aussparung)
- [Funktionen für Belag/Weg](#funktionen-für-belagweg)
- [Funktionen für Boden/Decke](#funktionen-für-bodendecke)
- [Funktionen für Dach](#funktionen-für-dach)
- [Funktionen für Door](#funktionen-für-door)
- [Funktionen für Door and Window Assembly](#funktionen-für-door-and-window-assembly)
- [Funktionen für Einfassung](#funktionen-für-einfassung)
- [Funktionen für Fenster](#funktionen-für-fenster)
- [Funktionen für Flächenpflanzung](#funktionen-für-flchenpflanzung)
- [Funktionen für Geländemodell](#funktionen-für-gelndemodell)
- [Funktionen für Geländer](#funktionen-für-gelnder)
- [Funktionen für Geländer/Zaun Classic](#funktionen-für-gelnderzaun-classic)
- [Funktionen für Gerät](#funktionen-für-gert)
- [Funktionen für Hecke](#funktionen-für-hecke)
- [Funktionen für Kabel](#funktionen-für-kabel)
- [Funktionen für Lichtschacht](#funktionen-für-lichtschacht)
- [Funktionen für Marionette Object](#funktionen-für-marionette-object)
- [Funktionen für Panel](#funktionen-für-panel)
  - [Verbinder](#verbinder)
- [Funktionen für Pflanze](#funktionen-für-pflanze)
- [Funktionen für Pfosten](#funktionen-für-pfosten)
  - [Riegel](#riegel)
    - [Fassade](#fassade)
- [Funktionen für Profillinie](#funktionen-für-profillinie)
- [Funktionen für Querprofile](#funktionen-für-querprofile)
- [Funktionen für Rampe](#funktionen-für-rampe)
- [Funktionen für Raum](#funktionen-für-raum)
- [Funktionen für Schaltkreis](#funktionen-für-schaltkreis)
- [Funktionen für Scheinwerfer](#funktionen-für-scheinwerfer)
- [Funktionen für Symbollinie Classic](#funktionen-für-symbollinie-classic)
- [Funktionen für Tragwerkselement](#funktionen-für-tragwerkselement)
- [Funktionen für Tür](#funktionen-für-tr)
- [Funktionen für Verteiler](#funktionen-für-verteiler)
- [Funktionen für Wand](#funktionen-für-wand)
- [Funktionen für WinDoor 6.0](#funktionen-für-windoor-60)
- [Funktionen für Window](#funktionen-für-window)
- [Funktionen für XPlanung](#funktionen-für-xplanung)
- [Funktionen für Zaun](#funktionen-für-zaun)
- [Logik](#logik)
- [Math. Formeln](#math-formeln)
- [Objekte](#objekte)
  - [Allgemein](#allgemein)
  - [Auslaufende Funktionen](#auslaufende-funktionen)
  - [Material](#material)
- [Tabellensuche](#tabellensuche)
- [Text](#text)

___

## Allgemein


#### __RunScript(ScriptName [; Parameter])__ ####

Führt ein Script mit Namen ScriptName und optionalen Parametern (Funktionen) aus und gibt das Ergebnis zurück.


```python
Database header cell:
=RunScript('My Script') executes the VectorScript script named “My Script” and returns a value for each object in the database

Spreadsheet cell:
=RunScript(2, 'ScriptFile.py', 2, 1) executes the Python script “ScriptFile.py” in the Vectorworks Plug-Ins folder, passing the parameters “2” and “1,” and returns a value

```

#### __Feldformat(Datenbank; Feldname)__ ####

Gibt den Wert des angegebenen Felds der Datenbank zurück.


```python
=FormatField(‘Door’, ‘Width’), where “Door” is the name of a record format, returns the default value for the “Width” field.


```

#### __ScriptbearbAusführen(ScriptName [; Parameter])__ ####

Führt ein Script aus und gibt das Ergebnis zurück. Die Zellen lassen sich bearbeiten und das Script wird danach erneut ausgeführt.



#### __Datenbank(Filter)__ ####

Erzeugt eine Datenbank von Objekten, auf die mit dem Filter verwiesen wird.


```python
=DATABASE((L='Floor-1')) creates a worksheet database of all objects on layer “Floor-1.”

```

#### __DatenbankDurchScript([scriptPfad]; scriptName; ...params...)__ ####

Führt ein Skript aus, um eine Datenbank mit Objekten zu erstellen.


```python
=DataBaseByScript('MyScript.py', 2, 1) creates a worksheet database by executing the script named “My Script.py,” passing the parameters “2” and “1” to the script.

```

## Funktionen für Adapter


#### __Objektdaten('eval adapter plug device'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag von Steckvorrichtung des Adapters.



#### __Objektdaten('eval adapter plug socket'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag von der Buchse des Adapters.



## Funktionen für Anschluss


#### __Objektdaten('eval socket circuits'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag von den mit dem Anschluss verbundenen Schaltkreisen.



#### __Objektdaten('eval socket device'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Gerät, das mit dem Anschluss verbunden ist.



## Funktionen für Arbeitsplatte


#### __Gewicht()__ ####

Nettogewicht der Arbeitsplatte oder eines der Unterobjekte. Ein Unterobjekt muss ein Material mit einer definierten Dichte haben, damit ein Gewicht bestimmt werden kann.



#### __Gewicht('Brutto')__ ####

Bruttogewicht der Arbeitsplatte oder eines der Unterobjekte. Ein Unterobjekt muss ein Material mit einer definierten Dichte haben, damit ein Gewicht bestimmt werden kann.



#### __Gewicht('Netto')__ ####

Bruttogewicht der Arbeitsplatte oder eines der Unterobjekte. Ein Unterobjekt muss ein Material mit einer definierten Dichte haben, damit ein Gewicht bestimmt werden kann.



#### __Objektdaten('Profil Abschlussleiste')__ ####

Name des Symbols des Spritzschutzes. Diese Funktion kann nur auf Arbeitsplatten und das Unterobjekt Spritzschutz angewendet werden.



#### __Objektdaten('Kantenprofil')__ ####

Name des Symbols des Kanten-/Leistenprofils. Diese Funktion kann nur auf Arbeitsplatten und die Unterobjekte Kanten und Leisten angewendet werden.



#### __Objektdaten('Verbindung')__ ####

Der Verbindungstyp des Unterobjekts Wange von Arbeitsplatten.



#### __Objektdaten('Stilname')__ ####

Der Stilname, der vom Arbeitsplatten-Objekt verwendet wird.



#### __Stärke()__ ####

Stärke der Einzelarbeitsplatte, Leisten, Spritzschutz oder Wangen. Für das Objekt Arbeitsplatte wird nur die Stärke der Einzelarbeitsplatte zurückgegeben.



#### __Breite('Bounding Box')__ ####

Die Breite der Bounding Box der Arbeitsplatte oder Einzelarbeitsplatte.



#### __Höhe()__ ####

Die Höhe (z-Wert) der Leisten und Spritzschutz von Arbeitsplatten.



#### __Höhe('Bounding Box')__ ####

Höhe der Bounding Box der Arbeitsplatte oder der Einzelarbeitsplatte.



#### __Anzahl('Aussparungen')__ ####

Die Anzahl der Ausschnitte in der Arbeitsplatte oder Einzelarbeitsplatte. Es werden sowohl 2D- als auch 3D-Ausschnitte berücksichtigt.



#### __Fläche()__ ####

Fläche der Außenseite der Wange.



#### __Fläche('Bounding Box')__ ####

Fläche der Bounding Box der Arbeitsplatte oder der Einzelarbeitsplatten.



#### __Fläche('Aussparungen')__ ####

Gesamtfläche der Aussparungen der Arbeitsplatte. Es werden hierbei alle 2D- und 3D-Aussparungen berücksichtigt. Diese Funktion lässt sich ausschließlich auf das Arbeitsplattenobjekt und das Unterobjekt Einzelarbeitsplatte anwenden.



#### __Fläche('Brutto')__ ####

Bruttofläche der Arbeitsplatte, wobei Ausschnitte nicht berücksichtigt werden. Diese Funktion kann nur auf Arbeitsplatten und das Unterobjekt Einzelarbeitsplatte angewendet werden.



#### __Fläche('Netto')__ ####

Die Nettofläche der Arbeitsplatte, wobei sämtliche Ausschnitte (2D und 3D) berücksichtigt werden. Diese Funktion kann nur auf Arbeitsplatten und das Unterobjekt Einzelarbeitsplatte angewendet werden.



#### __Umfang()__ ####

Umfang der Arbeitsplatte oder der Einzelarbeitsplatte. Ein etwaiger Überhang der Arbeitsplatte wird mit berücksichtigt.



#### __Länge()__ ####

Länge von Kantenprofilen, Leisten, Spritzschutz oder Wangen von Arbeitsplatten. Die Länge wird entlang der Außenkante des Unterobjekts gemessen.



#### __Volumenn()__ ####

Nettovolumen der Arbeitsplatte oder eines der Unterobjekte. 



#### __Volumenn('Brutto')__ ####

Bruttovolumen der Arbeitsplatte oder eines der Unterobjekte. Ausschnitte und Kantenprofile werden nicht berücksichtigt.



#### __Volumenn('Netto')__ ####

Nettovolumen der Arbeitsplatte oder eines der Unterobjekte.



## Funktionen für Assembly Frame Segment


#### __Tiefe(Filter)__ ####





#### __Breite(Filter)__ ####





#### __Länge(Filter)__ ####





## Funktionen für Aussparung


#### __Grundfläche()__ ####

Ermittelt die Grundfläche der Aussparung.



#### __Grundfläche('gross')__ ####

Ermittelt die Grundfläche der Aussparung.



#### __Grundfläche('net')__ ####

Ermittelt die Grundfläche der Aussparung abzüglich der Auskleidung.



#### __Objektdaten('isexternal')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Aussparung in einer äußeren Wand oder Boden/Decke befindet.



#### __Objektdaten('isloadbearing')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Aussparung in einer tragenden Wand oder Boden/Decke befindet.



#### __Objektdaten('size scale')__ ####

Der Skalierungsfaktor zeigt die skalierte Größe des verwendeten Symbols der Aussparung mit Grundform: Eigene Form.



#### __Objektdaten('story bound')__ ####

Ermittelt den Namen der verwendeten Referenzhöhe der Aussparung.



#### __Dicke()__ ####

Ermittelt die Dicke der Aussparung.



#### __Dicke('gross')__ ####

Ermittelt die Dicke der Aussparung.



#### __Dicke('net')__ ####

Ermittelt die Dicke der Aussparung abzüglich der Auskleidung.



#### __Höhe('above layer base')__ ####

Height('above layer base')

Ermittelt die Höhe des Einfügepunktes der Aussparung über der Ebenenbasishöhe.



#### __Höhe('above origin')__ ####

Height('above origin')

Ermittelt die Höhe des Einfügepunktes der Aussparung über dem Vectorworks-Nullpunkt.



#### __Höhe('above project origin')__ ####

Ermittelt die Höhe des Einfügepunktes der Aussparung über der Projekthöhe.



#### __Höhe('above storey base')__ ####

Height('above storey base')

Ermittelt die Höhe des Einfügepunktes der Aussparung über der Geshossbasishöhe.



#### __Höhe('story offset')__ ####

Ermittelt den Offset der verwendeten Referenzhöhe der Aussparung.



#### __Fläche()__ ####

Ermittelt die Fläche der Grundform der Aussparung.



#### __Fläche('gross')__ ####

Ermittelt die Fläche der Grundform der Aussparung.



#### __Fläche('net')__ ####

Ermittelt die Fläche der Grundform der Aussparung abzüglich der Auskleidung.



#### __Umfangeter()__ ####

Ermittelt den Umfang der Grundform der Aussparung.



#### __Umfangeter('gross')__ ####

Ermittelt den Umfang der Grundform der Aussparung.



#### __Umfangeter('net')__ ####

Ermittelt den Umfang der Grundform der Aussparung abzüglich der Auskleidung.



#### __Oberfläche()__ ####

Ermittelt die Oberfläche der Aussparung.



#### __Oberfläche('gross')__ ####

Ermittelt die Oberfläche der Aussparung.



#### __Oberfläche('lateral face')__ ####

Ermittelt die Manteloberfläche der Aussparung.



#### __Oberfläche('net')__ ####

Ermittelt die Oberfläche der Aussparung abzüglich der Auskleidung.



#### __Volumen()__ ####

Ermittelt das Volumen der Grundform der Aussparung.



#### __Volumen('gross')__ ####

Ermittelt das Volumen der Grundform der Aussparung.



#### __Volumen('net')__ ####

Ermittelt das Volumen der Grundform der Aussparung abzüglich der Auskleidung.



## Funktionen für Belag/Weg


#### __Tiefe()__ ####

Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __ProjizierteFläche()__ ####

Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Objektdaten('Schichtname')__ ####

Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.



#### __Fläche()__ ####

Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.



#### __Oberfläche()__ ####

Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Volumenn()__ ####

Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



## Funktionen für Boden/Decke


#### __Gewicht('Brutto'; [optionale Parameter])__ ####

Gewicht von Boden/Decke oder Boden/Deckenschicht in kg. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Gewicht('Netto'; [optionale Parameter])__ ####

Gewicht von Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Objektdaten('Schalldämmung')__ ####





#### __Objektdaten('Brennbare Konstruktion')__ ####





#### __Objektdaten('Brandmauer')__ ####





#### __Objektdaten('Schichtname')__ ####

Der Name der Wand-, Boden/Decke- oder Dachschicht.



#### __Objektdaten('Kostenindex-Code')__ ####





#### __Objektdaten('Kostenindex-System')__ ####





#### __Objektdaten('Beschreibung')__ ####





#### __Objektdaten('Aussenseite')__ ####





#### __Objektdaten('Feuerwiderstand')__ ####





#### __Objektdaten('Funktion')__ ####





#### __Objektdaten('Lambda')__ ####

Der Lambdawert des Objekt.



#### __Objektdaten('Tragend')__ ####





#### __Objektdaten('Hersteller')__ ####





#### __Objektdaten('Bezeichnung')__ ####





#### __Objektdaten('Modell')__ ####





#### __Objektdaten('R-Wert')__ ####

Der R-Wert des Objekts.



#### __Objektdaten('U-Wert')__ ####

Der U-Wert des Objekts.



#### __Breite()__ ####

Die Dicke einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Anzahl('Modifikatoren'; [optionale Parameter])__ ####

Die Anzahl der Modifikatoren in einem Boden oder Decke oder einer Wand. Bei einer Wand sind das Vorsprung und Nische, für Boden/Decke sind Volumenaddition und -subtraktion, sowie Entwässerung.

'Modifikatortyp=...': Es werden nur Modifikatoren mit den angegebenen Typen berücksichtigt. Mehrere Typen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Modifikatortyp ausschließen': Es werden die Modifikatoren mit dem angegebenen Typen nicht gezählt.



#### __Anzahl('Öffnungen'; [optionale Parameter])__ ####

Die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen in den Schichten gezählt, die dem Filter entsprechen.

'Schichtmaterial=...': Es werden nur Bauteile mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (für Wände), oben, unten (für Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Öffnungskriterien: Es werden nur Öffnungen gezählt, die alle angegebenen Kriterien erfüllen. Wenn für die Werte keine Einheiten angegeben sind, wird von Millimetern, Quadratmillimetern oder Kubikmillimetern ausgegangen. Für Böden/Decken stehen folgende Kriterien zur Verfügung: minimale Öffnungsfläche oben, maximale Öffnungsfläche oben, minimale Öffnungsfläche unten, maximale Öffnungsfläche unten, minimales Öffnungsvolumen, maximales Öffnungsvolumen, minimaler Öffnungsumfang oben, maximaler Öffnungsumfang oben, minimaler Öffnungsumfang unten, maximaler Öffnungsumfang unten. Für Wände stehen die folgenden Kriterien zur Verfügung: Min Öffnungsfläche links, Max Öffnungsfläche links, Min Öffnungsfläche rechts, Max Öffnungsfläche rechts, Min Öffnungsfläche dem Kern zugewandt, Max Öffnungsfläche dem Kern zugewandt, Min Öffnungsfläche dem Kern abgewandt, Max Öffnungsfläche dem Kern abgewandt, Min Öffnungsfläche Mitte, Max Öffnungsfläche Mitte, Min Öffnungsfläche der Grundfläche, Max Öffnungsfläche der Grundfläche, Min Öffnungslänge der Grundfläche links, Max Öffnungslänge der Grundfläche links, Min Öffnungslänge der Grundfläche rechts, Max Öffnungslänge der Grundfläche rechts, Min Öffnungslänge der Grundfläche dem Kern zugewandt, Max Öffnungslänge der Grundfläche dem Kern zugewandt, Min Öffnungslänge der Grundfläche dem Kern abgewandt, Max. Öffnungslänge der Grundfläche dem Kern abgewandt, Min Öffnungslänge der Grundfläche Mitte, Max Öffnungslänge der Grundfläche Mitte, Min Öffnungsvolumen, Max Öffnungsvolumen. 

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden. Gilt nur für Wände.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Gilt nur für Wände.

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -länge anhand der Filterkriterien gemessen werden. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.


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

#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __DickeDachflStützeBoden()__ ####

Dicke von Dachflächen, Profilstützen und Böden.


```python
Database header cell:
=SlabThickness returns the thickness for each object in the database

Spreadsheet cell:
=SlabThickness(PON=slab) returns the combined thickness of all slab objects in the drawing

```

#### __BodenDeckenstilName()__ ####

Name eines Boden/Deckenstils.


```python
Database header cell:
=SlabStyleName returns the name of the slab style for each slab object in the database

Spreadsheet cell:
=SlabStyleName(n='slab-1') returns the name of the slab style for the object named “slab-1”

```

#### __Fläche()__ ####

Berechnet die Fläche einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Umfang('Unten'; [optionale Parameter])__ ####

Umfang der Unterseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Umfang('Öffnungen unten'; [optionale Parameter])__ ####

Summe der Umfänge der einzelnen Öffnungen in der Unterseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsumfang=...' / 'Max Öffnungsumfang=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsumfang liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.



#### __Umfang('Öffnungen oben'; [optionale Parameter])__ ####

Summe der Umfänge der einzelnen Öffnungen in der Oberseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsumfang=...' / 'Max Öffnungsumfang=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsumfang liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.



#### __Umfang('Oben'; [optionale Parameter])__ ####

Umfang der Oberseite eines Bodens oder Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Oberfläche('Unten Brutto'; [optionale Parameter])__ ####

Fläche der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=SurfaceArea('bottom gross') returns the gross area of the bottom face of the slab or slab component.

=SurfaceArea('bottom gross', 'component=top') returns the gross area of the bottom face of the top component of the slab.
```

#### __Oberfläche('Unten Netto'; [optionale Parameter])__ ####

Fläche der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=SurfaceArea('bottom net') returns the area of the bottom face of the slab or slab component.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('bottom net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('bottom net', 'component=top') returns the area of the bottom face of the top component of the slab.
```

#### __Oberfläche('Öffnungen unten'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=SurfaceArea('openings bottom') returns the total area of openings on the bottom face of the slab or slab component.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings bottom', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the bottom face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings bottom', 'component=top') returns the total area of openings on the bottom face of the top component of the slab.
```

#### __Oberfläche('Öffnungen oben'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen in Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=SurfaceArea('openings top') returns the total area of openings on the top face of the slab or slab component.

=SurfaceArea('openings top', 'min opening area=0.5 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings top', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings top', 'component=bottom') returns the total area of openings on the top face of the bottom component of the slab.
```

#### __Oberfläche('Oben Brutto'; [optionale Parameter])__ ####

Gibt die Fläche der Obererseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=SurfaceArea('top gross') returns the gross area of the top face of the slab or slab component.

=SurfaceArea('top gross', 'component=bottom') returns the gross area of the top face of the bottom component of the slab.
```

#### __Oberfläche('Oben Netto'; [optionale Parameter])__ ####

Die Fläche der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=SurfaceArea('top net') returns the area of the top face of the slab or slab component.

=SurfaceArea('top net', 'min opening area=0.5 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('top net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the top face of the slab or slab component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('top net', 'component=bottom') returns the area of the top face of the bottom component of the slab.
```

#### __Volumenn()__ ####

Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Volumenn('Brutto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.
```

#### __Volumenn('Netto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.


```python
=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.
```

#### __Volumenn('Öffnungen'; [optionale Parameter])__ ####

Das Volumen der Öffnungen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.


```python
=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.
```

## Funktionen für Dach


#### __Objektdaten('Schichtname')__ ####

Der Name der Wand-, Boden/Decke- oder Dachschicht.



#### __Objektdaten('Kostenindex-Code')__ ####





#### __Objektdaten('Kostenindex-System')__ ####





#### __Objektdaten('Beschreibung')__ ####





#### __Objektdaten('Aussenseite')__ ####





#### __Objektdaten('Feuerwiderstand')__ ####





#### __Objektdaten('Funktion')__ ####





#### __Objektdaten('Lambda')__ ####

Der Lambdawert des Objekt.



#### __Objektdaten('Hersteller')__ ####





#### __Objektdaten('Bezeichnung')__ ####





#### __Objektdaten('Modell')__ ####





#### __Objektdaten('R-Wert')__ ####

Der R-Wert des Objekts.



#### __Objektdaten('U-Wert')__ ####

Der U-Wert des Objekts.



#### __DachflKompl()__ ####

Gesamtfläche von Dächern.


```python
Database header cell:
=RoofArea_Total returns the total area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Total(st=roofface) returns the combined total area of all roof face objects in the drawing
```

#### __DachflOhneÜberst()__ ####

Fläche von Dächern ohne die Fläche des Überstands.


```python
Database header cell:
=RoofArea_Heated returns the heated area for each roof and roof face object in the database

Spreadsheet cell:
=RoofArea_Heated (st=roofface) returns the combined heated area of all roof face objects in the drawing

```

#### __DachflKomplProj()__ ####

Gesamtfläche von Dächern auf die aktive Konstruktionsebene projiziert.


```python
Database header cell:
=RoofArea_TotalProj returns the total area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_Totalproj(t=roof) returns the combined total area of all roof objects in the drawing, as projected to the layer plane

```

#### __DachflOhneÜberstProj()__ ####

Fläche von Dächern ohne die Fläche des Überstands auf die aktive Konstruktionsebene projiziert.


```python
Database header cell:
=RoofArea_HeatedProj returns the heated area for each roof and roof face object in the database, as projected to the layer plane

Spreadsheet cell:
=RoofArea_HeatedProj (t=roof) returns the combined heated area of all roof objects in the drawing, as projected to the layer plane

```

#### __Dachstilname()__ ####

Name des Dachstils.


```python
Database header cell:
=RoofStyleName returns the roof style name for each roof object in the database

Spreadsheet cell:
=RoofStyleName(n='roof-1') returns the roof style name for the object named “roof-1”

```

## Funktionen für Door


#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __Volumen(criteria; 'door jamb')__ ####

Returns the volume the jamb.


```python
Database header cell:
=VOLUME('door jamb')     Returns the volume the jamb.

Spreadsheet cell:
=VOLUME(SEL, 'door jamb')    Returns the volume the jamb.

```

#### __Volumen(criteria; 'door sashes')__ ####

Returns the total volume all sashes (including sidelight and transom sashes).


```python
Database header cell:
=VOLUME('door sashes')     Returns the total volume all sashes (including sidelight and transom sashes).

Spreadsheet cell:
=VOLUME(SEL, 'door sashes')    Returns the total volume all sashes (including sidelight and transom sashes).

```

#### __Volumen(criteria; 'glazing all')__ ####

Returns the total volume of all glazing.


```python
Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.

```

#### __Volumen(criteria; 'glazing for leaves')__ ####

Returns the volume of glazing for all leaves (including vision panels).


```python
Database header cell:
=VOLUME('glazing for leaves')     Returns the volume of glazing for all leaves (including vision panels).

Spreadsheet cell:
=VOLUME(SEL, 'glazing for leaves')    Returns the volume of glazing for all leaves (including vision panels).

```

#### __Volumen(criteria; 'glazing for sidelights')__ ####

Returns the volume of glazing for all sidelights.


```python
Database header cell:
=VOLUME('glazing for sidelights')     Returns the volume of glazing for all sidelights.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sidelights')    Returns the volume of glazing for all sidelights.

```

#### __Volumen(criteria; 'glazing for transom')__ ####

Returns the volume of glazing for the transom.


```python
Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.

```

#### __Volumen(criteria; 'leaf panels')__ ####

Returns the total volume of the leaf panels.


```python
Database header cell:
=VOLUME('leaf panels')     Returns the total volume of the leaf panels.

Spreadsheet cell:
=VOLUME(SEL, 'leaf panels')    Returns the total volume of the leaf panels.

```

#### __Volumen(criteria; 'leaf stiles and rails')__ ####

Returns the total volume of the leaf rails, and stiles.


```python
Database header cell:
=VOLUME('leaf stiles and rails')     Returns the total volume of the leaf rails and stiles.

Spreadsheet cell:
=VOLUME(SEL, 'leaf stiles and rails')    Returns the total volume of the leaf rails and stiles.

```

## Funktionen für Door and Window Assembly


#### __Tiefe(Filter)__ ####





#### __Breite(Filter)__ ####





#### __Höhe(Filter)__ ####





#### __Fläche(Filter)__ ####





#### __Fläche(Filter)__ ####

Returns the total glazing area for all objects in the Assembly.



## Funktionen für Einfassung


#### __Grundfläche()__ ####

Berechnet die Grundfläche des Einfassung-Objekts und seiner Unterobjekte.



#### __FlächeSpezial()__ ####

Berechnet die Fläche der Profile für die Profilunterobjekte der Einfassung.



#### __Objektdaten('Material'; <Optionaler Index>)__ ####

Der Name des Material, der dem angegebenen Index entspricht. Die Materialien werden in alphabetischer Reihenfolge sortiert. Der Standardindex ist 1.



#### __Objektdaten('Name')__ ####

Der Name des Unterobjektsymbols für Einfassungen.



#### __Breite()__ ####

Die Breite der Einfassung unter Berücksichtigung der Profilelemente und Symbole, die auf dem Fundament platziert sind. Bei den Unterobjekten der Einfassung wird nur die Breite der Bounding Box berücksichtigt.



#### __Höhe()__ ####

Die Höhe der Einfassung unter Berücksichtigung der  verwendeten Profile und Symbole auf dem Fundament. Von den Unterobjekten der Einfassung wird lediglich die Bounding Box berücksichtigt.



#### __Länge()__ ####

Die Länge des Pfadverlaufs der Einfassung.



#### __Länge('Aussenradius'; <Min Radius>; <Max Radius>)__ ####

Die Gesamtlänge aller Außenradiussegmente innerhalb des angegebenen Bereichs.



#### __Länge('Innenradius'; <Min Radius>; <Max Radius>)__ ####

Die Gesamtlänge aller Innenradiussegmente innerhalb des angegebenen Bereichs.



#### __Länge('Gerade')__ ####

Die Gesamtlänge aller geraden Segmente.



#### __Volumenn()__ ####

Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Volumenn('Material'; <Optionaler Auswahl>)__ ####

Das Volumen des angegebenen Materials. Die Auswahl kann entweder ein Index oder Materialname sein. Wenn keine Auswahl angegeben wird, gibt die Funktion das Volumen des ersten gefundenen Materials zurück.



## Funktionen für Fenster


#### __Tiefe('Sill')__ ####

Gibt die Tiefe der äußeren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmenaußenkante.



#### __Tiefe('Stool')__ ####

Gibt die Tiefe der inneren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmeninnenkante.



#### __Objektdaten('CornerWindowType')__ ####

Gibt einen String zurück, der angibt, ob das Fenster ein ein- oder beidseitiges Eckfenster ist.



#### __Objektdaten('FallProtection')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Fenster eine Absturzsicherung (Geländer) hat, andernfalls falsch. Ob das Fenster ein Geländer hat, kann im Reiter 'Geländer' des Fensterdialogs festgelegt werden.



#### __Objektdaten('IsActionWallClosureRequired')__ ####

Gibt den Wert 'Wahr' (true) zurück, wenn das Fenster veraltete Laibungseinstellungen hat, die ab Vectorworks 2026 nicht mehr unterstützt werden.



#### __Objektdaten('IsArchitecturalversion')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt ein Komplettes Fenster ist, andernfalls falsch. Komplette Fenster sind Bestandteil des Architekturmoduls und benötigen eine entsprechende Seriennummer, um die volle Funktionalität freizuschalten.



#### __Objektdaten('IsBasicversion')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt ein Einfaches Fenster ist, andernfalls falsch. Einfache Fenster sind Bestandteil aller Module, haben aber nur wenige Optionen und Einstellmöglichkeiten.



#### __Objektdaten('IsInsertedInWall')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt in eine Wand eingefügt ist, andernfalls falsch.



#### __Objektdaten('IsPartOfAssembly')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Fenster Teil einer Assembly ist, andernfalls falsch.



#### __Objektdaten(IsWallExternal')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich das Fenster in einer Außenwand befindet oder nicht.



#### __Objektdaten('IsWallLoadBearing')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich das Fenster in einer tragenden Wand befindet oder nicht.



#### __Objektdaten('Material'; <Fensterbestandteil>)__ ####

Gibt den Namen des Objektmaterials eines Bestandteils des Fensters zurück.

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


```python
Datenbank:

=Objektdaten('Material'; <Fensterbestandteil>)

Tabelle:

=Objektdaten(Filter; 'Material'; <Fensterbestandteil>)

Die Funktion gibt den Namen des Objektmaterials eines Bestandteils des Fensters zurück.

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

Für alle Parameternamen und Fensterbestandteile existieren auch englische Bezeichnungen (Universal Names), die ebenfalls unterstützt werden.
```

#### __Objektdaten('ModeHeightAutoDimension')__ ####

Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.



#### __Objektdaten('ModeSelectedHeight')__ ####

Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Höhe an der Innenseite oder an der Außenseite definiert wird.



#### __Objektdaten('ModeSelectedWidth')__ ####

Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.



#### __Objektdaten('ModeWidthAutoDimension'[;<InteriorOrExterior>])__ ####

Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung innen bzw. außen bemaßt wird. Geben Sie 'Innen' oder 'Aussen' als Parameter an, wenn Sie nur einen der beiden Werte wünschen.



#### __Objektdaten('UseWallClosure')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt die Laibungseinstellungen der Wand verwendet, andernfalls falsch.



#### __Objektdaten('WinDoorHandleType'; <Nr. des Flügels>)__ ####

Gibt den Typ des Fenstergriffs eines Fensterflügels zurück.

Aufruf: =Objektdaten('Grifftyp'[;<Nummer des Flügels>])
Beispiel: =Objektdaten('Grifftyp';'2')

Die Flügel werden von innen aus gesehen von links nach rechts nummeriert.
Die Flügelnummer braucht nicht angegeben zu werden, wenn alle Flügel den gleichen Grifftyp haben.
Bei unterschiedlichen Grifftypen und fehlender Flügelnummer wird 'Verschiedene' zurückgegeben.



#### __Objektdaten('ZPositionDefinedBy')__ ####

Gibt einen String zurück, der angibt, ob die Z-Position des Fensters über die Brüstungs- oder die Sturzhöhe festgelegt ist und ob für diese Höhen die innere oder die äußere Wandseite maßgeblich ist.



#### __Breite()__ ####

Gibt diejenige Breite des Fensters zurück, die im Reiter 'Fenstergröße' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Breite('BottomFrame')__ ####

Gibt die Breite des unteren Fensterrahmens zurück.



#### __Breite('FinishedBreiteInside')__ ####

Gibt das Fertigmaß Breite Innen zurück.



#### __Breite('FinishedBreiteOutside')__ ####

Gibt das Fertigmaß Breite Außen zurück.



#### __Breite('Frame')__ ####

Gibt die Breite des Fensterrahmens zurück. Dieser Wert entspricht dem IFC-Wert 'Lining Thickness'. Bei asymmetrischen Fenstern wird die Breite des linken Rahmens zurückgegeben.



#### __Breite('FrameClearBreite')__ ####

Gibt das Rahmenlichtmaß Breite zurück.



#### __Breite('FrameTotalBreite')__ ####

Gibt das Rahmenaußenmaß Breite zurück.



#### __Breite('LeftFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen linken Fensterrahmens zurück.



#### __Breite('RightFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen rechten Fensterrahmens zurück.



#### __Breite('Sill')__ ####

Gibt die Breite der äußeren Fensterbank (gemessen längs der Wand) zurück, sofern eine solche existiert.



#### __Breite('Stool')__ ####

Gibt die Breite der inneren Fensterbank (gemessen längs der Wand) zurück, sofern eine solche existiert.



#### __Breite('TopFrame')__ ####

Gibt die Breite des oberen Fensterrahmens zurück.



#### __Breite('UnfinishedBreite')__ ####

Gibt das Rohmaß Breite zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Größe' des Fensterdialogs.



#### __Höhe()__ ####

Gibt diejenige Höhe des Fensters zurück, die im Reiter 'Fenstergröße' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Höhe ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Höhe('FinishedHöheObjectInside')__ ####

Gibt das Fertigmaß Höhe Fenster innen zurück.



#### __Höhe('FinishedHöheObjectOutside')__ ####

Gibt das Fertigmaß Höhe Fenster außen zurück.



#### __Höhe('FinishedHöheWallInside')__ ####

Gibt das Fertigmaß Höhe Wand innen zurück.



#### __Höhe('FinishedHöheWallOutside')__ ####

Gibt das Fertigmaß Höhe Wand außen zurück.



#### __Höhe('FrameClearHöhe')__ ####

Gibt das Rahmenlichtmaß Höhe zurück.



#### __Höhe('FrameTotalHöhe')__ ####

Gibt das Rahmenaußenmaß Höhe zurück.



#### __Höhe('HeadHöheDefinedBySettings')__ ####

Gibt die Sturzhöhe gemäß Einstellungen zurück.



#### __Höhe('HeadHöheFromOrigin')__ ####

Gibt die Sturzhöhe ab Nullpunkt zurück.



#### __Höhe('Left')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('Right')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('RoughSizeBottomFromOrigin')__ ####

Gibt den Abstand zwischen Unterkante Rohmaß und Nullpunkt zurück.



#### __Höhe('RoughSizeTopFromOrigin')__ ####

Gibt den Abstand zwischen Oberkante Rohmaß und Nullpunkt zurück.



#### __Höhe('SillHöheDefinedBySettings')__ ####

Gibt die Brüstungshöhe gemäß Einstellungen zurück.



#### __Höhe('SillHöheFromOrigin')__ ####

Gibt die Brüstungshöhe ab Nullpunkt zurück.



#### __Höhe('Stool')__ ####

Gibt die Höhe der inneren Fensterbank zurück, sofern eine solche existiert.



#### __Höhe('UnfinishedHöhe')__ ####

Gibt das Rohmaß Höhe zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Größe' des Fensterdialogs.



#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __Winkel('Lamellen')__ ####

Gibt den Winkel der Lamellen des Raffstorens bzw. Fensterladens - sofern vorhanden - aus.



## Funktionen für Flächenpflanzung


#### __Tiefe()__ ####

Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __ProjizierteFläche()__ ####

Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Objektdaten('Schichtname')__ ####

Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.



#### __Objektdaten('Trennlinie')__ ####

Der Trennlinientext der Pflanzen innerhalb der Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen und Trennlinien von Flächenpflanzungen aufgelistet sind. 



#### __Objektdaten('Flächenpflanzung'; <Feld>)__ ####

Ermöglicht den Zugriff auf Datenfelder der Flächenpflanzung, sofern der Stil dies zulässt.



#### __Objektdaten('Anteil'; <Pfanzenindex>)__ ####

Der Anteil einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Plant Record'; <Feld>; <Pflanzenindex>)__ ####

Ermöglicht den Zugriff auf Datenfelder der Pflanzen innerhalb der Flächenpflanzung, sofern der Stil dies zulässt. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Dichte'; <Pflanzenindex>)__ ####

Die Dichte einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Mengeneinheit'; <Pflanzenindex>)__ ####

Die Mengeneinheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Dichte mit Einheit'; <Pflanzenindex>)__ ####

Die Dichte mit Einheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Fläche()__ ####

Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.



#### __Oberfläche()__ ####

Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Volumenn()__ ####

Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



## Funktionen für Geländemodell


#### __Tiefe()__ ####

Die Tiefe der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __ProjizierteFläche()__ ####

Die projizierte Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Objektdaten('Schichtname')__ ####

Der Name der Schichten des Belagaufbaus von Flächenpflanzung, Belag/Weg und Geländemodell.



#### __Fläche()__ ####

Berechnet die Fläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und ihre Schichten.



#### __Oberfläche()__ ####

Die Oberfläche der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Oberfläche( 'Ist-Zustand' )__ ####

Berechnet die Oberfläche des Ist-Zustands des Geländemodell und dessen Schichten.


```python
Database header cell:
=SURFACEAREA('Existing')     Returns the existing Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Existing')    Returns the existing Surface Area for the selected Site Model object.

```

#### __Oberfläche( 'Soll-Zustand' )__ ####

Berechnet die Oberfläche des Soll-Zustands des Geländemodell und dessen Schichten.


```python
Database header cell:
=SURFACEAREA('Proposed')     Returns the proposed Surface Area for Site Model object or component in the DB row.

Spreadsheet cell:
=SURFACEAREA(SEL, 'Proposed')    Returns the proposed Surface Area for the selected Site Model object.

```

#### __Volumenn()__ ####

Das Volumen der Flächenpflanzung, des Belag/Weg-Objekts oder des Geländemodells und deren Schichten.



#### __Volumenn('Ist-Zustand')__ ####

Berechnet das Volumen des Ist-Zustands des Geländemodell und dessen Schichten.


```python
Database header cell:
=VOLUME('existing')     	Returns the existing volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'existing')    Returns the existing volume for the selected Site Model object.

```

#### __Volumenn('Soll-Zustand')__ ####

Berechnet das Volumen des Soll-Zustands des Geländemodell und dessen Schichten.


```python
Database header cell:
=VOLUME('proposed')     	Returns the proposed volume for Site Model object or component in the DB row.

Spreadsheet cell:
=VOLUME(SEL, 'proposed')    Returns the proposed volume for the selected Site Model object.

```

## Funktionen für Geländer


#### __Breite()__ ####

Diese Funktion kann auf folgende Unterobjekte angewandt werden: Rahmen, Platten, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Rahmen: Breite des rechteckigen Rahmens.

Für Platte: Breite der rechteckigen Platte.

:Für Halterung: Breite der Handlaufhalterung (entspricht dem Abstand des Handlaufs ).

Für Pfosten seitliche Montage: Breite Pfosten mit seitlicher Montage (entspricht der Auskragung).



#### __Breite('Halterungen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Breite der Handlaufhalterungen.



#### __Breite('Pfosten seitliche Montage')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Breite der Pfosten mit seitlicher Montage.



#### __Breite('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Breite der Rahmen.



#### __Breite('Platten/Fertigelemente')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtbreite aller Platten.



#### __Breite('Profil')__ ####

Diese Funktion kann auf folgende Unterobjekte angewandt werden: Handlauf, Geländer, Pfosten, Rahmen, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Breite des entsprechenden Unterobjekts.



#### __Höhe()__ ####

Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Geländer, Handlauf, Rahmen, Platte, Halterung, Pfosten und Pfosten seitliche Montage

BESCHREIBUNG:
Für Geländer-Objekt: Höhe des Geländer-Objekts (Maximalhöhe von Geländer oder Handlauf).

Für Rahmen: Höhe des rechteckigen Rahmens.

Platte: Höhe der rechteckigen Platte.

Für Handlauf: Höhe des Handlaufs.

Für Geländer: Höhe des Geländerhandlaufs.

Für Pfosten seitliche Montage: Höhe des Pfostens.

Für Pfosten: Höhe des Pfostens.



#### __Höhe('Halterung')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Beschreibung:
Höhe der Handlaufhalterung.



#### __Höhe('Pfosten seitliche Montage')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Höhe aller Unterobjekte der Pfosten mit seitlicher Montage.



#### __Höhe('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Höhe aller Rahmen.



#### __Höhe('Geländer')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Höhe des Geländers.



#### __Höhe('Handlauf')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Höhe des Handlaufs.



#### __Höhe('Platten/Fertigelemente')__ ####

Diese Funktion kann auf Geländer-Objekte ngewandt werden.
Die Höhe der Platten und N/A, wenn gemischte Platten.



#### __Höhe('pfosten')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Summe der Höhe aller Unterobjekte der Pfosten.



#### __Höhe('Profil')__ ####

Diese Funktion kann auf folgende Unterobjekte des Geländer-Objekts angewandt werden: Geländer, Handlauf, Rahmen, vertikale und horizontale Geländerstäbe, Pfosten und Pfosten seitliche Montage.

BESCHREIBUNG:
Höhe des Profils des entsprechenden Unterobjekts.



#### __Anzahl('Ecken')__ ####

Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Geländer und Handlauf

BESCHREIBUNG:
Für Geländer-Objekt: Anzahl der Richtungsänderungen (links, rechts, nach oben, nach unten) im Geländer-Objekt.

Für Geländer:  Anzahl der Richtungsänderungen (links, rechts, nach oben, nach unten) im Geländer.

Für Handlauf: Wenn es keinen Handlauf gibt, dann die Richtungsänderungen (links, rechts, nach oben, nach unten) des Pfadverlaufs des Geländer-Objekts.



#### __Winkel()__ ####

Diese Funktion kann auf folgende Unterobjekte angewandt werden:

Vertikale und horizontale Stäbe.

Für vertikale Stäbe: Winkel der vertikalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.

Für horizontale Stäbe: Winkel der horizontalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.



#### __Winkel('Horizontale Stäbe')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekte: Winkel der horizontalen Stäbe. Wenn in den Einstellungen diagonal angeordnet, dann 45°, andernfalls 0°.



#### __Winkel('Vertikale Geländerstäbe')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekte: Winkel der vertikalen Stäbe. Wenn in den Einstellungen diagonal ausgerichtet, dann 45°, andernfalls 0°.



#### __Fläche()__ ####

Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Rahmen, Platten, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Für Geländer-Objekt: Gesamtfläche des Geländer-Objekts.

:Für Unterobjekt: Fläche des betreffenden Unterobjekts.



#### __Fläche('Halterungen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Fläche der Handlaufhalterungen.



#### __Fläche('Pfosten seitliche Montage')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Fläche der Pfosten mit seitlicher Montage.



#### __Fläche('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtfläche der Rahmen.



#### __Fläche('Platten/Fertigelemente')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtfläche der Platten.



#### __Umfang()__ ####

Diese Funktion kann auf das Unterobjekt Rahmen angewandt werden:

BESCHREIBUNG:
Rahme: Umfang des Rahmens.



#### __Umfang('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Für Geländer-Objekt: Gesamtumfang aller Rahmen.



#### __Länge()__ ####

Diese Funktion kann auf Geländer-Objekte und folgende Unterobjekte angewandt werden: Handlauf, Geländer, Rahmen, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Für Geländer-Objekt: Länge des 3D-Pfadverlaufs des Geländers.

Für Handlauf: Länge des 3D-Handlaufs.

Für Geländer: Länge des 3D-Geländers.

Für Rahmen: Breite des Rahmens.

Für vertikale oder horizontale Geländerstäbe: Länge der Stäbe.

Für Halterung: Versatz Geländer + Höhe Halterung.

Für Pfosten seitliche Montage: Höhe Pfosten plus Auskragung.



#### __Länge('Horizontale Geländerstäbe')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Unterobjekte horizontale Geländerstäbe.



#### __Länge('Vertikale Geländerstäbe')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Unterobjekte vertikale Geländerstäbe.



#### __Länge('Halterungen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge der Halterungen.



#### __Länge('Pfosten seitliche Montage')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge des Pfostens mit seitlicher Montage.



#### __Länge('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Länge der Rahmen.



#### __Länge('Geländer')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Geländer.



#### __Länge('Handlauf')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtlänge aller Handläufe.



#### __Länge('Max Befestigungsabstand')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Maximaler Abstand der Pfosten. Wenn keine Pfosten, dann Abstand der Befestigungen.



#### __Oberfläche()__ ####

Diese Funktion kann auf folgende Unterobjekte des Geländer-Objekts angewandt werden: Geländer, Handlauf, Pfosten, Rahmen, Platten, vertikale und horizontale Geländerstäbe, Halterungen und Pfosten seitliche Montage.

BESCHREIBUNG:
Vollständige Außenfläche des Unterobjekts.



#### __Oberfläche('Geländerstäbe horizontal')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller horizontalen Geländerstäbe.



#### __Oberfläche('Geländerstäbe vertikal')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller vertikalen Geländerstäbe.



#### __Oberfläche('Halterungen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Oberfläche der Geländerhalterungen.



#### __Oberfläche('Pfosten seitliche Montage')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Pfosten mit seitlicher Montage.



#### __Oberfläche('Rahmen')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Rahmen.



#### __Oberfläche('Geländer')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Geländer.



#### __Oberfläche('Handlauf')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Handläufe.



#### __Oberfläche('Platten/Fertigelemente')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Platten.



#### __Oberfläche('Pfosten')__ ####

Diese Funktion kann auf Geländer-Objekte angewandt werden:

BESCHREIBUNG:
Gesamtoberfläche aller Pfosten mit seitlicher Montage.



## Funktionen für Geländer/Zaun Classic


#### __Breite()__ ####

Breite([optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Wandkonsole, seitliche Konsole, Rahmen und Platte.

OPTIONALER PARAMETER:Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Wandkonsole: Horizontale Abmessung der Wandkonsole des Handlaufs.

Seitliche Konsole: Abmessung der Seitlichen Konsole in horizontaler Richtung.

Rahmen: Breite des rechteckigen Rahmens

Platte: Breite der Platte in Ansicht.



#### __Breite('Profil')__ ####

Breite('Profil', [optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Handlauf oben, Pfosten, Ober- und Untergurt, Stab vertikal und horizontal, Rahmen.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Handlauf oben: Breite des Querschnittprofils des Handlaufs. Für runde und achteckige Profile ist die Breite gleich der Höhe. Für Eigene Profile (2D- Symbol), wird die Bounding Box verwendet, um die Breite zu ermitteln.

Pfosten: Breite des Querprofils des Pfostens.

Ober- und Untergurt: Breite des Querprofils des Gurts.

Stab vertikal und horizontal: Höhe des Profils der vertikalen Stäbe.



#### __Höhe()__ ####

Höhe([optionaler Parameter])

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



#### __Höhe('Profil')__ ####

Höhe('Profil', [optionaler Parameter])

Die Funktion kann auf eines der folgenden Unterobjekte angewandt werden: Handlauf oben, Pfosten, Ober- und Untergurt, Stab vertikal  und horizontal, Rahmen.

OPTIONALER PARAMETER:Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Höhe des Querschnittprofils des Handlaufs. Für runde und achteckige Profile ist die Breite gleich der Höhe. Für Eigene Profile (2D- Symbol), wird die Bounding Box verwendet, um die Höhe zu ermitteln.

Ober- und Untergurt: Höhe des Profils des Gurts.

Stab vertikal und horizontal: Höhe des Profils der vertikalen Stäbe.



#### __Anzahl('Winkel')__ ####

Anzahl('Winkel', [optionaler Parameter])

Die Funktion kann auf das Geländerobjekt und den Handlauf oben angewandt werden.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer: Anzahl der vertikalen Winkel  und horizontalen Ecken im Geländerpfad.

Handlauf oben: Anzahl der Winkelstücke im Handlauf.



#### __Winkel()__ ####

Winkel([optionaler Parameter])

Diese Funktion kann mit folgenden Unterobjekte verwendet werden: Stab vertikal and Stab horizontal.

OPTIONALER PARAMETER:
'Unterobjekt=...': Falls angegeben, wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Für Stab vertikal: Winkel der vertikalen Stäbe. Vertikal is 0°.

Für Stab horizontal: Winkel der horizontalen Stäbe. horizontal is 0°.



#### __Fläche()__ ####

Fläche([optionaler Parameter])

Die Funktion kann auf das Geländerobjekt und die folgenden Unterobjekte angewandt werden.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer: Geländerfläche als Geländerlänge multipliziert mit Geländerhöhe. Dabei wird die Länge zwischen den beiden Aussenkanten des ersten und letzten Pfostens gemessen oder zwischen den Aussenkanten der Geländerfüllungen. Die Länge des Handlaufs ist dabei irrelevant. Diese Längendefinition unterscheidet sich vom buildingSMART- Standard, der im Datenbankfeld RailingLengthIFC des Geländerobjekts gesichert ist. Die Höhe ist Oberkante des obersten Unterobjekts (Handlauf falls vorhanden, Rahmen, Füllung oder Obergurt) über dem Boden oder der Treppe. In Vectorworks entspricht der Boden dem Wert 'Höhe Punkt 1' in der Objektinfopalette.

Platte: Fläche der Platte (Breite x Höhe).



#### __Umfang()__ ####





#### __Länge('')__ ####

Die Funktion kann auf das Geländerobjekt und die folgenden Unterobjekte angewandt werden: Handlauf oben, Obergurt, Untergurt, Stab vertikal, Stab horizontal, Platte.

OPTIONALE PARAMETER:Unterobjekt=...': Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländerobjekt: Länge des Geländerobjekts zwischen den beiden Aussenkanten des ersten und letzten Pfostens oder zwischen den Aussenkanten der Geländerfüllungen. Die länge des Handlaufs ist dabei irrelevant. Diese Längendefinition unterscheidet sich vom buildingSMART- Standard, welcher im Datenfeld RailingLengthIFC gesichert und in die Felder Qto_RailingBaseQuantities.Length und BaseQuantities.Length geschrieben wird. 

Handlauf oben: Länge des 3D-Pfadobjekts des Handlaufs oben einschließlich der Verlängerungen des Handlaufs oben am Anfang oder Ende des Geländerobjekts.

Ober- und Untergurt: Länge des Gurts.

Stab vertikal und horizontal: Länge des Stabs.

Platte: Derselbe Wert, als wenn die Funktion Breite auf Rahmen angewendet wird.



#### __Länge('Max')__ ####

Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen allen Instanzen eines Unterobjekts an.
Wählbare Unterobjekte sind Wandkonsole, Pfosten und seitliche Konsole.

OPTIONALER PARAMETER:
'Unterobjekt=...': Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Wandkonsole: Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen Wandkonsolen an.

Pfosten: Gibt den irgendwo im Geländerobjekt auftretenden maximalen Abstand zwischen Pfosten an.

Seitliche Konsole: Maximaler Abstand zwischen den seitlichen Konsolen, gemessen auf deren Mittelachse.



#### __Oberfläche()__ ####

Oberfläche(Filter, [optionale Parameter])

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

Platte: Gesamte Oberfläche aller Seiten der Platte.



## Funktionen für Gerät


#### __Objektdaten('eval equipment item'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom entsprechenden Equipment-Objekt des Geräts.(Schweiz: Objektdaten('eval equipment item',



## Funktionen für Hecke


#### __Objektdaten('Anteil'; <Pfanzenindex>)__ ####

Der Anteil einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Plant Record'; <Feld>; <Pflanzenindex>)__ ####

Ermöglicht den Zugriff auf Datenfelder der Pflanzen innerhalb der Flächenpflanzung, sofern der Stil dies zulässt. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Dichte'; <Pflanzenindex>)__ ####

Die Dichte einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Mengeneinheit'; <Pflanzenindex>)__ ####

Die Mengeneinheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



#### __Objektdaten('Dichte mit Einheit'; <Pflanzenindex>)__ ####

Die Dichte mit Einheit einer Pflanze innerhalb einer Flächenpflanzung. Kann nur auf eine Datenbankzeile angewendet werden, in der die Pflanzen von Flächenpflanzungen aufgelistet sind. Wird <Pflanzenindex> verwendet, so werden die Informationen für eine bestimmte Pflanze aus der Flächenpflanzung zurückgegeben.



## Funktionen für Kabel


#### __Objektdaten('Verbindungspunkt'; '<Datenauswahl>'; [<Verbindungspunktindex>)]__ ####

Daten des Verbindungspunktes. Datenauswahl ist 'Name'. Wird die Funktion auf ein Unterobjekt des Verbindungspunkt angewendet, muss der Verbindungspunktindex nicht angegeben werden. Wird hingegen die Funktion auf ein Kabel angewendet, muss der Verbindungspunktindex angegeben werden.



#### __Objektdaten('Kabelabschnitt'; '<Datenauswahl>'; [<Kabelabschnittindex>)]; [<Bauteilindex>)]__ ####

Kabelabschnittsdaten. Datenauswahl sind 'Name' und 'Bestellte Teile'. 'Bestellte Teile' ist nur lesbar. Wenn die Funktion auf ein Unterobjekt eines Kabelabschnitts angewendet wird, muss kein Kabelabschnittindex angegeben werden. Wird hingegen die Funktion auf ein Kabel angewendet, muss ein Kabelabschnittindex angegeben werden. Optional können Sie für 'Bestellte Teile' den Index des Teils angegeben, das angezeigt werden soll.



#### __Länge('Kabelabschnitt'; '<Datenauswahl>'; [<Abschnittsindex>)]__ ####

Die Länge des Kabelabschnitts. Datenauswahl  sind 'Länge', 'Start Slack', 'End Slack', 'Swag' und 'Total Vertical Drop'. 'Länge' und 'Total Vertical Drop' können nur gelesen werden. Wird die Funktion auf ein Kabelabschnitt angewendet, so muss der Abschnittsindex nicht angegeben werden. Wird hingegen die Funktion auf ein Kabel angewendet, muss der Abschnittsindex angegeben werden.



## Funktionen für Lichtschacht


#### __Tiefe('')__ ####

Tiefe des Gitters/Wanddicke



#### __Tiefe('Innen')__ ####

Innere Tiefe des Lichtschachtkörpers orthogonal zur Gebäudeaußenwand.



#### __Tiefe('Außen')__ ####

Äußere Tiefe des Lichtschachtkörpers orthogonal zur Gebäudeaußenwand.



#### __FlächeSpezial('')__ ####

Oberfläche der Wände und des Bodens auf deren Außenseiten.



#### __Breite('')__ ####

Breite des Gitters.



#### __Breite('Innen')__ ####

Innere Breite des Lichtschachtkörpers parallel zur Gebäudeaußenwand.



#### __Breite('Außen')__ ####

Äußere Breite des Lichtschachtkörpers parallel zur Gebäudeaußenwand.



#### __Höhe('Innen')__ ####

Innere vertikale Höhe des Lichtschachtkörpers.



#### __Höhe('Außen')__ ####

Äußere vertikale Höhe des Lichtschachtkörpers.



#### __Oberfläche('')__ ####

Summe aller äußeren Oberflächen des Lichtschachtkörpers.



#### __Volumenn('')__ ####

Volumen des Lichtschachtkörpers bestehend aus Lichtschachtboden und -wänden.



## Funktionen für Marionette Object


#### __Objektdaten('parameter'; '<OIP FieldName>')__ ####

Get parameter values or attached record fields from Marionette objects.



## Funktionen für Panel

### Verbinder


#### __Objektdaten('eval panel connector circuit'; '<Datenbank>'; '<Feldname>')__ ####

Eigenschaftswert oder verbundene Datenbank des Schaltkreises, der mit dem Verbinderpanel verbunden ist.



## Funktionen für Pflanze


#### __Anzahl('Pflanzaushubschicht')__ ####

Die Anzahl der Schichten des Pflanzaushubs.



#### __Volumenn('Pflanzaushubschicht'; <index>)__ ####

Das Volumen der Schicht des Pflanzaushubs, auf die mit <index> verwiesen wird.



#### __Pflanzenbild(Index)__ ####

Bild des Objekts, auf das mit dem Index verwiesen wird.


```python
Database header cell:
=PlantImage(2) displays the image specified for Image Detail in the More Data pane of the plant symbol definition

Spreadsheet cell:
=PlantImage((‘Plant’.’plant ID’=’TaxfR’), 4) displays the image specified for Custom Image in the More Data pane of the plant symbol definition with a plant ID of TaxfR

```

## Funktionen für Pfosten

### Riegel

#### Fassade


#### __FassadePRLänge(Klassenname)__ ####

Länge aller Pfosten und Riegel einer Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Database header cell:
=CurtWallFrameLength('') returns the combined length of the curtain wall frames for each curtain wall in the database

Spreadsheet cell:
=CurtWallFrameLength(t=wall, '') returns the combined length of the curtain wall frames for all curtain walls in the drawing

```

#### __FassadeFüllFlächeBrt(Klassenname)__ ####

Bruttofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Database header cell:
=CurtWallPnlAreaGross('') returns the combined gross area of the curtain wall panels for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaGross(t=wall, '') returns the combined gross area of the curtain wall panels for all curtain walls in the drawing

```

#### __FassadeFüllFlächeNet(Klassenname)__ ####

Nettofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Database header cell:
=CurtWallPnlAreaNet ('Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for each curtain wall in the database

Spreadsheet cell:
=CurtWallPnlAreaNet(t=wall, 'Class-1') returns the combined net area of the curtain wall panels assigned to the class “Class-1” for all curtain walls in the drawing

```

## Funktionen für Profillinie


#### __Länge()__ ####





#### __Länge('Profil')__ ####

Gesamtlänge eines Profils.



#### __Länge('Profil links')__ ####

Länge der linken Seite eines Profils.



#### __Länge('Profil Stationierung')__ ####

Die Kilometrierung bzw. Stationierung eines Profils.



#### __Länge('Profil rechts')__ ####

Länge der rechten Seite eines Profils.



## Funktionen für Querprofile


#### __Objektdaten('Profillinienname')__ ####

Name der Achse.



#### __Objektdaten('Index')__ ####

Index des Profils.



#### __Objektdaten('Stationierung')__ ####

Die Texbasierte Stationierung eines Profils.



#### __Objektdaten('Anmerkung')__ ####

Zusätzliche Anmerkungen.



#### __Anzahl('Profile')__ ####

Anzahl der Querprofile.



#### __Fläche('Auftrag')__ ####

Auftragsfläche des Profils.



#### __Fläche('Abtrag')__ ####

Abtragsfläche des Profils.



#### __Länge('Abstand')__ ####

Abstand zur Stationierung des vorherigen Profils.



#### __Länge('Stationierung')__ ####

Stationierung eines Profils.



#### __Volumenn('Masse Auftrag')__ ####

Masse Auftragsfläche des Profils.



#### __Volumenn('Masse Abtrag')__ ####

Masse Abtragsfläche des Profils.



## Funktionen für Rampe


#### __Tiefe('')__ ####

Rampenlaufkörper 1: Breite des Rampenlaufkörpers quer zur Laufrichtung.

Rampenpodestkörper: Breite des Rampenpodestkörpers quer zur Laufrichtung

Rampenbelag: Breite des Belags. Bei unterschiedlicher Breite von Lauf 1, Podest und Lauf 2 wird kein Wert ausgegeben. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.



#### __ProjizierteFläche('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Projizierte Grundfläche des Rampenlaufkörpers 

Rampenpodestkörper: Projizierte Grundfläche des Rampenpodestkörpers.




#### __Grundfläche('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es wird nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Projizierte Grundfläche des Rampenlaufkörpers 

Rampenpodestkörper: Projizierte Grundfläche des Rampenpodestkörpers.



#### __Breite('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Radabweiser links/rechts: Breite des Radabweisers bezogen auf dessen vertikalen Querschnitt.

Rampenlaufkörper 1: Breite des Rampenlaufkörpers quer zur Laufrichtung.

Rampenpodestkörper: Breite des Rampenpodestkörpers quer zur Laufrichtung

Rampenbelag: Breite des Belags. Bei unterschiedlicher Breite von Lauf 1, Podest und Lauf 2 wird kein Wert ausgegeben. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben. 



#### __Profil('Profil')__ ####

Durchmesser des Handlaufs des Geländers.



#### __Höhe('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Oberkante des Geländers über dem Boden oder der Treppe.Dieser Wert wird ins IFC-Feld  des Sekundär-Objekts IfcRailing Pset_RailingCommon.Height geschrieben. 

Gehweg links/rechts: Höhe des Gehwegs bezogen auf dessen vertikalen Querschnitt. 

Radabweiser links/rechts: Höhe des Radabweisers bezogen auf dessen vertikalen Querschnitt.

Rampenbelag: Dicke des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.



#### __Winkel('')__ ####

Gesamtsteigung über alle Läufe und Podeste in Grad.



#### __Fläche('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Geländerlänge multipliziert mit Geländerhöhe. Geländerlänge beginnt und endet mit der Geländerfüllung (Rahmen/Panel). Die Geländerhöhe ist der vertikale Abstand zwischen Höhenpunkt 1 oder 2 und der Oberkante des höchsten Unterobjekts (oberer Handlauf, Rahmen, Panel oder Querprofil oben).

Rampenlaufkörper 1: Bruttofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Bruttofläche des Rampenpodestkörpers.

Rampenbelag: Bruttofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.



#### __Fläche('Brutto')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Bruttofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Bruttofläche des Rampenpodestkörpers.

Rampenbelag: Bruttofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.



#### __Fläche('Netto')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Rampenlaufkörper 1: Nettofläche des Rampenlaufkörpers entlang dessen geneigter Oberseite. 

Rampenpodestkörper: Nettofläche des Rampenpodestkörpers.

Rampenbelag: Nettofläche des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben.



#### __Länge('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Geländer links, Geländer rechts, Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenlaufkörper 1, Rampenpodestkörper.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Geländer links/rechts: Gesamtlänge des 3D- Pfadkörpers des Geländers. Dieser Wert wird in die IFC-Felder  des Sekundär-Objekts IfcRailing Qto_RailingBaseQuantities.Length und BaseQuantities.Length geschrieben.

Gehweg links/rechts: Länge des Gehwegs, gemessen auf dessen mittleren Lauflinie.

Radabweiser links/rechts: Länge des Radabweisers entlang dessen Mittelachse.

Rampenlaufkörper 1: Lauflänge des Rampenkörpers.

Rampenpodestkörper: Lauflänge des Rampenpodestkörpers.



#### __Oberfläche('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Gehweg links/rechts: Abgewickelte (= tatsächliche) und exponierte Hüllfläche des Gehwegs. Die Kontaktflächen zwischen den Unterobjekten (z.B. zwischen Gehweg und Rampenkörper oder zwischen Radabweiser und Gehweg) und die vertikale Fläche, die Teil der Rampenseitenfläche außen ist, gehören nicht dazu. Praktischer Anwendungsfall: ein Anstrich. Oberflächen von Belag und Gehweg können über die Unterobjekte separat ermittelt werden.

Radabweiser links/rechts: Abgewickelte (= tatsächliche) und exponierte Hüllfläche des Radabweisers. Die Kontaktflächen zwischen den Unterobjekten (z.B. zwischen Gehweg und Radabweiser) und die vertikale Fläche, die Teil der Rampenseitenfläche außen ist, gehören nicht dazu. Praktischer Anwendungsfall: ein Anstrich. Oberflächen von Belag und Gehweg können über die Unterobjekte separat ermittelt werden.



#### __Volumenn('')__ ####

Die Funktion kann auf das Rampenobjekt und die folgenden Unterobjekte angewandt werden: Gehweg links, Gehweg rechts, Radabweiser links, Radabweiser rechts, Rampenlaufkörper 1, Rampenpodestkörper, Rampenbelag.

OPTIONALE PARAMETER:
Unterobjekt=...':Es werden nur das angegebene Unterobjekt berücksichtigt.

BESCHREIBUNG:
Gehweg links/rechts: Bruttovolumen des Gehwegs (Summe der Volumina des Gehwegs auf Lauf 1, Podest, Lauf 2)

Radabweiser links/rechts: Bruttovolumen des Radabweisers (Summe der Volumina des Radabweisers auf Lauf 1, Podest, Lauf 2)

Rampenlaufkörper 1: Volumen des Rampenlaufkörpers

Rampenpodestkörper: Volumen des Rampenpodestkörpers.

Rampenbelag: Bruttovolumen des Belags. Wenn kein Belag vorhanden ist, wird der Wert 0 ausgegeben. 



## Funktionen für Raum


#### __Objektdaten('Belag'; Feldname; [Trennzeichen]; [Ort]; [Wandindex])__ ####

Wert des Feldes 'Feldname' in einer Raumbelagdatenbank (Raumbelag).

Diese Funktion ist auf Raumobjekte und dessen Unterobjekte anwendbar, die mit einer Datenbank Raumbelagsfläche oder Raumbelag verknüpft sind. Im letzteren Fall gibt die Funktion lediglich den Wert des Datenbankfeldes zurück. In den beiden erstgenannten Fällen listet die Funktion die Werte der Raumbelag-Datenbankfelder für alle Unterobjekte auf, die den angegebenen Kriterien 'Position' und 'Wandindex' entsprechen, getrennt durch das angegebene 'Trennzeichen'.

'Trennzeichen': Kann eine beliebige Zeichenkette sein. Wird zwischen jedem der zurückgegebenen Werte eingefügt. Verwenden Sie '\n', um jeden Wert in einer separaten Zeile aufgelistet. Standardmäßig werden die Werte durch ein Komma getrennt.

'Position': Kann 'Boden', 'Leiste', 'Wände', 'Decke', 'Nord', 'Ost', 'Süd' oder 'West' sein. Wird dieser Parameter angegeben, werden nur Beläge mit der angegebenen Position aufgelistet.

'Wandindex': Der Index einer Wand, deren Wert aufgelistet werden soll. Nur anwendbar, wenn 'Wände' für den Parameter 'Position' verwendet wird. Wenn nicht angegeben, werden alle Wandwerte aufgelistet.


```python
In einer Filterzeile einer Objektliste, für alle Raumobjekte.
=Objektdaten('Belag', 'PosNr', ', ') - Listet die Positionsnummer (bzw. Artikel- oder Bestellnummer), aller in einem Raum verwendeten Beläge auf, getrennt durch ein Komma.
=Objektdaten('Belag', 'PosNr', '') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge auf, jeweils in einer neuen Zeile.
=Objektdaten('Belag', 'PosNr', ', ', 'Boden') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für Böden auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für Wände auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände', 1) - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für die erste Wand auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände', 2) - Listet die Positionsnummer, bzw. Artikel- oder Bestellnummer, aller in einem Raum verwendeten Beläge für die zweite Wand auf.

In einer Filterzeile einer Objektliste, für alle Unterobjekte von Räumen, die mit Raumbelag verknüpft sind.
Objektdaten('Belag', 'PosNr') - Entspricht dem Datenbankfeld 'Space_Finish'.'PosNr'
=Objektdaten('Belag', 'PosNr', '', 'Decke') - Positionsnummer (bzw. Artikel- oder Bestellnummer) des Belags, jedoch nur, wenn der Belag der Decke zugeordnet ist.
=Objektdaten('Belag', 'PosNr', '', 'Wände', 1) - Positionsnummer (bzw. Artikel- oder Bestellnummer) des Belags, jedoch nur, wenn der Belag der ersten Wand zugeordnet ist.
```

#### __RaumNameVonObj()__ ####

Gibt den Namen des Raums zurück, in dem das Objekt sich befindet.


```python
Database header cell:
=GetSpaceNameForObj returns the space name for each object in the database

Spreadsheet cell:
=GetSpaceNameForObj(n='chair-1') returns the space name for the object named “chair-1”

```

#### __RaumNumVonObj()__ ####

Gibt die Nummer des Raums zurück, in dem sich das Objekt befindet.


```python
Database header cell:
=GetSpaceNumForObj returns the space number for each object in the database

Spreadsheet cell:
=GetSpaceNumForObj(n='chair-1') returns the space number for the object named “chair-1”
```

## Funktionen für Schaltkreis


#### __Objektdaten('eval circuit destination adapter'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Zieladapter des Schaltkreises.



#### __Objektdaten('eval circuit destination device'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Zielgerät des Schaltkreises.



#### __Objektdaten('eval circuit destination socket'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Zielanschluss des Schaltkreises.



#### __Objektdaten('eval circuit drop points'; ['<Datenbank>']; ['<Feldname>']; ['AbschlüsseIgnorieren'])__ ####

Auflistung der ID's von dazwischenliegenden Drop Points, Eigenschaftswerten oder angehängten Datenfeldern, durch die ein Stromkreis verläuft. Fügen Sie AbschlüsseIgnorieren hinzu, um die Drop Points am Anfang oder am Ende der Strecke nicht aufzulisten. Die Zeichnung muss analysiert werden.



#### __Objektdaten('eval circuit route'; ['<Datenbank>']; ['<Feldname>'])__ ####

Gibt die Pfad-IDs, den Parameter oder den Datenbankeintrag von den Kabelpfaden, die vom Schaltkreis verwendet werden. Die Zeichnung muss zuvor mit dem entsprechenden Befehl überprüft werden.



#### __Objektdaten('eval circuit source adapter'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Quellgerät des Schaltkreises.



#### __Objektdaten('eval circuit source device'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Quellgerät des Schaltkreises.



#### __Objektdaten('eval circuit source socket'; '<Datenbank>'; '<Feldname>')__ ####

Gibt den Parameter oder den Datenbankeintrag vom Quellanschluss des Schaltkreises.



## Funktionen für Scheinwerfer


#### __Gewicht(Filter)__ ####

Das Gesamtgewicht des Scheinwerfers mit allem Zubehör. 



#### __Objektdaten('Scheinwerfer-Zubehörtyp'; <Feld>)__ ####

Gerätetyp des Scheinwerferzubehörs. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



#### __Objektdaten('Zubehöreigenschaften'; <Feld>)__ ####

Daten des Scheinwerferzubehörs. Als Parameter kann eine Eigenschaft des Scheinwerfers eingegeben werden. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



#### __Objektdaten('Zubehörsymbole'; <Feld>)__ ####

Symbolnamen des Scheinwerferzubehörs. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



#### __Objektdaten('Gruppenscheinwerfer'; <Feld>)__ ####

Einstellungen der Scheinwerfer, wobei Zubehör ignoriert wird. Als Parameter kann eine Eigenschaft des Scheinwerfers eingegeben werden.



#### __Objektdaten('DMX-Kanal'; <Feld>)__ ####

Pultkanal der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



#### __Objektdaten('Farben'; <Feld>)__ ####

Lichtfarben der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



#### __Objektdaten('eval schematic device'; '<Datenbank>'; '<Feldname>')__ ####

Eigenschaftswert oder verbundene Datenbank des Objekts der Stromplanung.



#### __Objektdaten('Eigenschaft'; <Feld>)__ ####

Einstellungen der Scheinwerfer. Wird kein Parameter angegeben, werden alle Zellen und Zubehör berücksichtigt, während mit der Eingabe von Parametern auf bestimmte Zellen und Zubehör zugegriffen werden kann.



## Funktionen für Symbollinie Classic


#### __OBJEKTDATEN('xplanung'; [Objekt]; [Attribut; Index]; Attribut[:Format]; [Index])__ ####

Gibt Attributswerte von XPlanung-Objekten zurück. PARAMETER:
Objekt: (Optional) Das XPlanung-Objekt in dem sich das XPlanung-Attribut befindet.

Attribut: Das XPlanung-Attribute von dem der Wert zurückgegeben wird. Bei einer komplexen Datenstruktur muss zuerst das Übergeordnete Attribute als eigener Parameter angegeben werden.

Format: (Optional) Das Format des zurückzugebenden Werts. Bsp.: 'dachform:kurz'. Wird kein Format angegeben, wird der vollständige Wert zurückgegeben. Bsp.: 'Walmdach (3200)'
...:name oder ...:text: Gibt nur den entsprechenden Textwert zurück. Bsp.: 'Walmdach'.
...:value oder ...:wert: Gibt nur den entsprechenden numerischen Wert zurück. Bsp.: '3200'.
...:short oder ...:kurz: Gibt nur die entsprechende Kurzfom zurück. Bsp.: 'WD'.
...:roman oder ...:römisch: Zahlenwerte werden als Römische Zahl ausgegeben. Bsp.: 'XII' (12).

Index: (Optional) Welcher Wert zurückgegeben wird, wenn mehrere Werte definiert sind. Der erste Wert ist '0', der zweite Wert ist '1' usw. Wird kein Index angegeben (oder '-1') werden alle Werte als Text und durch ';' getrennt zurückgegeben. Bsp.: 'Pultdach (2100); Pultdach (3200)'.

Übersicht der XPlanung-Objekte und Attribute: https://xleitstelle.de/xplanung/releases


```python
=OBJEKTDATEN('xplanung'; 'BP_BaugebietsTeilFlaeche'; 'dachform') Gibt den Werts des Attributs 'dachform' im XPlanung-Objekt 'BP_BaugebietsTeilFlaeche' zurück.

=OBJEKTDATEN('xplanung'; 'dachform') Gibt den Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform'; 1) Gibt den zweiten Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform:kurz') Gibt die Kurzform des Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 'h') Gibt den Wert des Attributs 'h' aller Hoehenangaben zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 0; 'h') Gibt den Wert des Attributs 'h' der ersten Hoehenangabe zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 2; 'hoehenbezug:kurz')	Gibt die Kurzform des Werts des Attributs 'hoehenbezug' der dritten Hoehenangabe zurück.

```

## Funktionen für Tragwerkselement


#### __Objektdaten(Filter; 'Unterkante Bekleidung')__ ####

Die Unterkante der Bekleidung des Tragwerkelements.


```python
Database header cell:
=OBJECTDATA('cover bound bottom')     Returns the bottom bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound bottom')    Returns the bottom bound of the Structural Member cover.

```

#### __Objektdaten(Filter; 'Oberkante Bekleidung')__ ####

Die Oberkante der Bekleidung des Tragwerkelements.


```python
Database header cell:
=OBJECTDATA('cover bound top')     Returns the top bound of the Structural Member cover.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover bound top')    Returns the top bound of the Structural Member cover.

```

#### __Objektdaten(Filter; 'Physische Länge Bekleidung')__ ####

Die physische Länge der Bekleidung des Tragwerkelements inklusive der Abschlüsse.


```python
Database header cell:
=OBJECTDATA('cover physical length')     Returns the physical length of the structural member cover including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'cover physical length')    Returns the physical length of the structural member cover including its start and end conditions.

```

#### __Objektdaten(Filter; 'Unterkante Element')__ ####

Die Unterkante des Tragwerkelements.


```python
Database header cell:
=OBJECTDATA('member bound bottom')     Returns the bottom bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound bottom')    Returns the bottom bound of the Structural Member.

```

#### __Objektdaten(Filter; 'Oberkante Element')__ ####

Die Oberkante des Tragwerkelements.


```python
Database header cell:
=OBJECTDATA('member bound top')     Returns the top bound of the Structural Member.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member bound top')    Returns the top bound of the Structural Member.

```

#### __Objektdaten(Filter; 'Länge Tragwerkelement')__ ####

Die Länge des Tragwerkelements inklusive der Abschlüsse.


```python
Database header cell:
=OBJECTDATA('member physical length')     Returns the physical length of the structural member including its start and end conditions.

Spreadsheet cell:
=OBJECTDATA(SEL, 'member physical length')    Returns the physical length of the structural member including its start and end conditions.

```

## Funktionen für Tür


#### __Objektdaten('DoorCasingBasicType')__ ####

Gibt den Grundtyp der Zarge zurück, falls die Tür eine Zarge besitzt.



#### __Objektdaten('FloorRecessHeight')__ ####

Gibt den Bodeneinstand der Tür zurück. Der Bodeneinstand ist definiert als Ebenenbasishöhe - UK Rahmen/Zarge, wenn die Laibungseinstellungen der Wand verwendet werden, sonst undefiniert.



#### __Objektdaten('hingeside')__ ####

Gibt einen String zurück, der die Bandung der Tür beschreibt.



#### __Objektdaten('IsActionWallClosureRequired')__ ####

Gibt den Wert 'Wahr' (true) zurück, wenn die Tür veraltete Laibungseinstellungen hat, die ab Vectorworks 2026 nicht mehr unterstützt werden.



#### __Objektdaten('IsArchitecturalversion')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt eine Komplette Tür ist, andernfalls falsch. Komplette Türen sind Bestandteil des Architekturmoduls und benötigen eine entsprechende Seriennummer, um die volle Funktionalität freizuschalten.



#### __Objektdaten('IsBasicversion')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt eine Einfache Tür ist, andernfalls falsch. Einfache Türen sind Bestandteil aller Module, haben aber nur wenige Optionen und Einstellmöglichkeiten.



#### __Objektdaten('IsInsertedInWall')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt in eine Wand eingefügt ist, andernfalls falsch.



#### __Objektdaten('IsPartOfAssembly')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn die Tür Teil einer Assembly ist, andernfalls falsch.



#### __Objektdaten(IsWallExternal')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Tür in einer Außenwand befindet oder nicht.



#### __Objektdaten('IsWallLoadBearing')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Tür in einer tragenden Wand befindet oder nicht.



#### __Objektdaten('Material'; <Türbestandteil>)__ ####

Gibt den Namen des Objektmaterials eines Bestandteils der Tür zurück.

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



#### __Objektdaten('ModeHeightAutoDimension')__ ####

Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.



#### __Objektdaten('ModeSelectedHeight')__ ####

Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird N/A zurückgegeben.



#### __Objektdaten('ModeSelectedWidth')__ ####

Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.



#### __Objektdaten('ModeWidthAutoDimension'[;<InteriorOrExterior>])__ ####

Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung innen bzw. außen bemaßt wird. Geben Sie 'Innen' oder 'Aussen' als Parameter an, wenn Sie nur einen der Werte wünschen.



#### __Objektdaten('opensinwalldirection')__ ####

Gibt einen String zurück, der angibt, auf welche Seite der Wand hin (links oder rechts) die Tür sich öffnen läßt.



#### __Objektdaten('UseWallClosure')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt die Laibungseinstellungen der Wand verwendet, andernfalls falsch.



#### __Objektdaten('WinDoorHandleType'[;<Nr. des Türblatts>][; <Side>])__ ####

Gibt den Typ des Türgriffs eines Türblatts zurück. Falls in 3D ein Symbol als Türgriff angezeigt wird, wird der Name des Symbols zurückgegeben.

Aufruf: =Objektdaten('Grifftyp'[; <Nr. des Türblatts>][; <Türseite>]])

      Nr. des Türblatts: von innen gesehen von links nach rechts.

      Türseite: 'Innen' (Innenseite) oder 'Aussen' (Außenseite).
Beispiel: =Objektdaten('Grifftyp';'1';'innen')

Wird die Nummer des Türblatts weggelassen und die Türblätter haben verschiedene Grifftypen, kann kein eindeutiger Grifftyp ermittelt werden.
Falls auch noch die Türseite weggelassen wird, müssen alle Tügrifftypen innen und außen an allen Türblättern gleich sein, um einen eindeutigen Rückgabewert zu erhalten.



#### __Breite()__ ####

Gibt diejenige Breite der Tür zurück, die im Reiter 'Türbreite' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Breite('FinishedBreiteInside')__ ####

Gibt das Fertigmaß Breite Rechts zurück.



#### __Breite('FinishedBreiteOutside')__ ####

Gibt das Fertigmaß Breite Links zurück.



#### __Breite('FittingsClearBreite')__ ####

Gibt die Lichte Breite Beschlag zurück.



#### __Breite('FrameClearBreite')__ ####

Gibt das Lichte Durchgangsmaß Breite zurück.



#### __Breite('FrameTotalBreite')__ ####

Gibt das Zargen-/Rahmenaußenmaß Breite zurück.



#### __Breite('LeftFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen linken Türrahmens zurück.



#### __Breite('NinetyDegreesClearBreite')__ ####

Gibt die Lichte Breite 90° zurück.



#### __Breite('Rebate')__ ####

Gibt das Zargen-/Rahmenfalzmaß zurück.



#### __Breite('RightFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen Türrahmens zurück.



#### __Breite('TopFrame')__ ####

Gibt die Breite des oberen Türrahmens zurück.



#### __Breite('UnfinishedBreite')__ ####

Gibt das Rohmaß Breite zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türbreite' des Türendialogs.



#### __Breite('unitsizehingeside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandseite der Tür zurück.



#### __Breite('unitsizestopside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandgegenseite der Tür zurück.



#### __Höhe()__ ####

Gibt diejenige Höhe der Tür zurück, die im Reiter 'Türhöhe' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Höhe ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Höhe('FinishedHöheWallInside')__ ####

Gibt das Fertigmaß Höhe rechts zurück.



#### __Höhe('FinishedHöheWallOutside')__ ####

Gibt das Fertigmaß Höhe links zurück.



#### __Höhe('FrameClearHöhe')__ ####

Gibt das Lichte Durchgangsmaß Höhe zurück.



#### __Höhe('FrameTotalHöhe')__ ####

Gibt das Zargen-/Rahmenaußenmaß Höhe zurück.



#### __Höhe('Left')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('Rebate')__ ####

Gibt das Zargen-/Rahmenfalzmaß zurück.



#### __Höhe('Right')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('ThresholdHöheFromOrigin')__ ####

Gibt die Schwellenhöhe ab Nullpunkt der Zeichnung zurück. Falls die Checkbox 'Schwelle in 3D erzeugen' ausgeschaltet ist: bei eingeschalteter Checkbox 'Rahmen unter Tür' entspricht OK Schwelle der Höhe 'UK Türblatt' aus dem Reiter 'Türhöhe', andernfalls der Höhe 'UK Rahmen' bzw. 'UK Zarge'.



#### __Höhe('ThresholdHöheFromStory')__ ####

Gibt die Schwellenhöhe ab Geschoss zurück. Falls die Checkbox 'Schwelle in 3D erzeugen' ausgeschaltet ist: bei eingeschalteter Checkbox 'Rahmen unter Tür' entspricht OK Schwelle der Höhe 'UK Türblatt' aus dem Reiter 'Türhöhe', andernfalls der Höhe 'UK Rahmen' bzw. 'UK Zarge'.



#### __Höhe('UnfinishedHöhe')__ ####

Gibt das Rohmaß Höhe Tür zurück. Das Rohmaß Tür ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('UnfinishedHöheWall')__ ####

Gibt das Rohmaß Höhe Wand zurück. Das Rohmaß Wand ist definiert als Abstand von UK Wandöffnung bis OK Rohmaß Höhe Tür (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('unitsizehingeside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandseite der Tür zurück.



#### __Höhe('unitsizestopside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandgegenseite der Tür zurück.



#### __Anzahl('Leaf')__ ####

Gibt die Anzahl der Türblätter zurück.



#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



## Funktionen für Verteiler


#### __Objektdaten('eval schematic device'; '<Datenbank>'; '<Feldname>')__ ####

Eigenschaftswert oder verbundene Datenbank des Objekts der Stromplanung.



## Funktionen für Wand


#### __Gewicht('Brutto'; [optionale Parameter])__ ####

Gewicht von Boden/Decke oder Boden/Deckenschicht in kg. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Gewicht('Netto'; [optionale Parameter])__ ####

Gewicht von Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Grundfläche('Brutto'; [optionale Parameter])__ ####

Die Grundfläche einer Wand oder einer Wandschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.


```python
=FootprintArea('gross') returns the gross area of the footprint of the wall or wall component.

=FootprintArea('gross', 'component=core') returns the gross area of the footprint of the core component of the wall.

=FootprintArea('gross', 'height=100mm') returns the gross area of the footprint of the wall or wall component, but measured at 100mm from the layer.
```

#### __Grundfläche('Netto'; [optionale Parameter])__ ####

Die Grundfläche einer Wand oder Wandschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.
Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht in der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.


```python
=FootprintArea('net') returns the area of the footprint of the wall or wall component.

=FootprintArea('net', 'min opening area=0.5 sq m') returns the area of the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters.

=FootprintArea('net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=FootprintArea('net', 'opening type=Door') returns the area of the footprint of the wall or wall component, but only taking openings created by "Door" plug-in objects into account.

=FootprintArea('net', 'exclude opening type=Door') returns the area of the footprint of the wall or wall component, but ignoring any openings that are created by "Door" plug-in objects.

=FootprintArea('net', 'opening type=Door;WinDoor 6.0') returns the area of the footprint of the wall or wall component, but only taking openings created by "Door" or "WinDoor 6.0" plug-in objects into account.

=FootprintArea('net', 'component=core') returns the area of the footprint of the core component of the wall.

=FootprintArea('net', 'height=100mm') returns the area of the footprint of the wall or wall component, but measured at 100mm from the layer.
```

#### __Grundfläche('Öffnungen'; [optionale Parameter])__ ####

Gibt die Fläche der Öffnungen in der Grundfläche einer Wand oder Wandschicht zurück.

'Schichtname=...': Es werden nur Öffnungen in den Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Fläche gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.


```python
=FootprintArea('openings') returns the total area of openings on the footprint of the wall or wall component.

=FootprintArea('openings', 'min opening area=0.5 sq m') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters.

=FootprintArea('openings', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=FootprintArea('openings', 'opening type=Door') returns the total area of openings on the footprint of the wall or wall component, but only taking openings created by "Door" plug-in objects into account.

=FootprintArea('openings', 'exclude opening type=Door') returns the total area of openings on the footprint of the wall or wall component, but ignoring any openings that are created by "Door" plug-in objects.

=FootprintArea('openings', 'opening type=Door;WinDoor 6.0') returns the total area of openings on the footprint of the wall or wall component, but only taking openings created by "Door" or "WinDoor 6.0" plug-in objects into account.

=FootprintArea('openings', 'component=core') returns the total area of openings on the footprint of the core component of the wall.

=FootprintArea('openings', 'height=100mm') returns the total area of openings on the footprint of the wall or wall component, but measured at 100mm from the layer.
```

#### __Objektdaten('Schalldämmung')__ ####





#### __Objektdaten('Brennbare Konstruktion')__ ####





#### __Objektdaten('Brandmauer')__ ####





#### __Objektdaten('Schichtname')__ ####

Der Name der Wand-, Boden/Decke- oder Dachschicht.



#### __Objektdaten('Kostenindex-Code')__ ####





#### __Objektdaten('Kostenindex-System')__ ####





#### __Objektdaten('Beschreibung')__ ####





#### __Objektdaten('Aussenseite')__ ####





#### __Objektdaten('Feuerwiderstand')__ ####





#### __Objektdaten('Funktion')__ ####





#### __Objektdaten('Lambda')__ ####

Der Lambdawert des Objekt.



#### __Objektdaten('Tragend')__ ####





#### __Objektdaten('Hersteller')__ ####





#### __Objektdaten('Bezeichnung')__ ####





#### __Objektdaten('Modell')__ ####





#### __Objektdaten('Pfadtyp')__ ####

Gibt den Leitlinientyp der Wand. 0 ist Linie und 1 ist Bogen.



#### __Objektdaten('R-Wert')__ ####

Der R-Wert des Objekts.



#### __Objektdaten('U-Wert')__ ####

Der U-Wert des Objekts.



#### __Breite()__ ####

Die Dicke einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Höhe('Durchschnitt')__ ####

Berechnet die durchschnittliche Höhe einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Höhe('Insgesamt')__ ####

Die Gesamthöhe einer Wand.



#### __Anzahl('Einsätze'; [optionale Parameter])__ ####

Die Anzahl der in der Wand eingefügten Objekte (Symbole und intelligente Objekte).

'Einfügungstyp=...': Es werden nur eingefügte Objekte mit den angegebenen Namen berücksichtigt. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Einfügungstyp ausschließen': Es werden die angegebenen Objekte in Wände nicht gezählt.


```python
=Count('inserts') returns the number of inserts in the wall object.

=Count('inserts', 'insert type=Window') returns the number of "Window" plug-in object inserts.

=Count('inserts', 'insert type=Window;WinDoor 6.0') returns the number of by "Window" and "WinDoor 6.0" plug-in object inserts.

The difference between Count('inserts') and Count('openings') is that in the rare cases where two inserts share the same opening, Count('inserts') will treat them as different inserts, but Count('openings') will treat them as one large opening.
```

#### __Anzahl('Modifikatoren'; [optionale Parameter])__ ####

Die Anzahl der Modifikatoren in einem Boden oder Decke oder einer Wand. Bei einer Wand sind das Vorsprung und Nische, für Boden/Decke sind Volumenaddition und -subtraktion, sowie Entwässerung.

'Modifikatortyp=...': Es werden nur Modifikatoren mit den angegebenen Typen berücksichtigt. Mehrere Typen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Modifikatortyp ausschließen': Es werden die Modifikatoren mit dem angegebenen Typen nicht gezählt.



#### __Anzahl('Öffnungen'; [optionale Parameter])__ ####

Die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen in den Schichten gezählt, die dem Filter entsprechen.

'Schichtmaterial=...': Es werden nur Bauteile mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (für Wände), oben, unten (für Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Öffnungskriterien: Es werden nur Öffnungen gezählt, die alle angegebenen Kriterien erfüllen. Wenn für die Werte keine Einheiten angegeben sind, wird von Millimetern, Quadratmillimetern oder Kubikmillimetern ausgegangen. Für Böden/Decken stehen folgende Kriterien zur Verfügung: minimale Öffnungsfläche oben, maximale Öffnungsfläche oben, minimale Öffnungsfläche unten, maximale Öffnungsfläche unten, minimales Öffnungsvolumen, maximales Öffnungsvolumen, minimaler Öffnungsumfang oben, maximaler Öffnungsumfang oben, minimaler Öffnungsumfang unten, maximaler Öffnungsumfang unten. Für Wände stehen die folgenden Kriterien zur Verfügung: Min Öffnungsfläche links, Max Öffnungsfläche links, Min Öffnungsfläche rechts, Max Öffnungsfläche rechts, Min Öffnungsfläche dem Kern zugewandt, Max Öffnungsfläche dem Kern zugewandt, Min Öffnungsfläche dem Kern abgewandt, Max Öffnungsfläche dem Kern abgewandt, Min Öffnungsfläche Mitte, Max Öffnungsfläche Mitte, Min Öffnungsfläche der Grundfläche, Max Öffnungsfläche der Grundfläche, Min Öffnungslänge der Grundfläche links, Max Öffnungslänge der Grundfläche links, Min Öffnungslänge der Grundfläche rechts, Max Öffnungslänge der Grundfläche rechts, Min Öffnungslänge der Grundfläche dem Kern zugewandt, Max Öffnungslänge der Grundfläche dem Kern zugewandt, Min Öffnungslänge der Grundfläche dem Kern abgewandt, Max. Öffnungslänge der Grundfläche dem Kern abgewandt, Min Öffnungslänge der Grundfläche Mitte, Max Öffnungslänge der Grundfläche Mitte, Min Öffnungsvolumen, Max Öffnungsvolumen. 

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden. Gilt nur für Wände.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Gilt nur für Wände.

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -länge anhand der Filterkriterien gemessen werden. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.


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

#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __WandflächeNetto()__ ####

2D-Wandfläche einer Wand ohne Tür- und Fensterflächen.


```python
Database header cell:
=WallArea_Net returns the average of the net area of the interior and exterior face of the wall, for each wall in the database; the net area is adjusted for holes in the wall

Spreadsheet cell:
=WallArea_Net(t=wall) returns the average of the net area of the interior and exterior face of the wall, combined for all walls in the drawing; the net area is adjusted for holes in the wall

```

#### __WandflächeBrutto()__ ####

2D-Wandfläche einer Wand inkl. Tür- und Fensterflächen.


```python
Database header cell:
=WallArea_Gross returns the average of the gross area of the interior and exterior face of the wall, for each wall in the database; the gross area ignores holes in the wall

Spreadsheet cell:
=WallArea_Gross(t=wall) returns the average of the gross area of the interior and exterior face of the wall, combined for all walls in the drawing; the gross area ignores holes in the wall

```

#### __DurchschnWandhöhe()__ ####

Durchschnittliche Wandhöhe inkl. der höchsten Punkte und verschiedener Anfangs- und Endhöhen.


```python
Database header cell:
=WallAverageHeight returns the average height for each wall object in the database

Spreadsheet cell:
=WallAverageHeight((t=wall)&(sel=true)) returns the average height of all walls that are selected in the drawing

```

#### __Wanddicke()__ ####

Wanddicke.


```python
Database header cell:
=WallThickness returns the thickness for each wall object in the database

Spreadsheet cell:
=WallThickness(t=wall) returns the combined thickness of all walls in the drawing

```

#### __Wandstilname()__ ####

Name des Wandstils.


```python
Database header cell:
=WallStyleName returns the name of the wall style for each wall object in the database

Spreadsheet cell:
=WallStyleName(n='wall-1') returns the name of the wall style for the object named “wall-1”

```

#### __Fläche()__ ####

Berechnet die Fläche einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Länge()__ ####

Die Länge einer Wand oder seiner Schichten.



#### __Länge('Leitlinie Kern abgewandt'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wandschicht, die von der Kernschicht abgewandt ist. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Länge('Leitlinie Mitte'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die in der Mitte verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Länge('Leitlinie Kern zugewandt'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wandschicht, die der Kernschicht zugewandt ist. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Länge(Leitlinie links; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Kante der Wand oder Wandschicht verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Länge(Leitlinie rechts; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Kante der Wand oder Wandschicht verläuft. Alle Öffnungen, Vorsprünge, Nischen und Wandpunkte werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.



#### __Länge('Kern abgewandt Brutto'; [optionale Parameter])__ ####

Die Länge einer Wandschicht entlang der Wandunterkante, die vom Kern abgewandt ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Kern abgewandt Netto'; [optionale Parameter])__ ####

Die Länge einer Wandschicht entlang der Unterkante, die vom Kern abgewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Mitte Brutto'; [optionale Parameter])__ ####

Die Länge einer Wand oder Wandschicht entlang der Mittellinie der Wandunterkante. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Mitte Netto'; [optionale Parameter])__ ####

Die Länge einer Wandschicht entlang der Mittellinie der Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Kern zugewandt Brutto'; [optionale Parameter])__ ####

Die Länge einer Wandschicht entlang der Wandunterkante, die dem Kern zugewandt ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Kern zugewandt Netto'; [optionale Parameter])__ ####

Die Länge einer Wandschicht entlang der Unterkante, die dem Kern zugewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Links Brutto'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Unterkante der Wand oder Wandschicht verläuft. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Links Netto'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der linken Kante der Wand oder Wandschicht verläuft.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Rechts Brutto'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Unterkante der Wand oder Wandschicht verläuft. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Rechts Netto'; [optionale Parameter])__ ####

Die Länge der Leitlinie einer Wand oder Wandschicht, die auf der rechten Unterkante der Wand oder Wandschicht verläuft.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Öffnungen Kern abgewandt'; [optionale Parameter])__ ####

Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Unterkante, die zu Kernschicht abgewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Öffnungen Mitte'; [optionale Parameter])__ ####

Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Mittellinie der Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Öffnungen Kern zugewandt'; [optionale Parameter])__ ####

Die Gesamtlänge der Öffnungen einer Wandschicht entlang der Unterkante, die der Kernschicht zugewandt ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Öffnungen links'; [optionale Parameter])__ ####

Die Gesamtlänge der Öffnungen einer Wandschicht entlang der linken Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Länge('Öffnungen rechts'; [optionale Parameter])__ ####

Die Gesamtlänge der Öffnungen einer Wandschicht entlang der rechten Wandunterkante.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungslänge=...' / 'Max Öffnungslänge=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungslänge liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Millimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.

'Höhe=...': Die Höhe in Bezug zur Ebene, in der die Länge gemessen wird. Standardmäßig wird eine Höhe von 0 verwendet. Wenn keine Einheiten angegeben sind, werden Millimeter angenommen.



#### __Oberfläche('Kern abgewandt Brutto'; [optionale Parameter])__ ####

Fläche einer Wandschichtoberfläche, die von der Kernschicht weg ausgerichtet ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.



#### __Oberfläche('Kern abgewandt Netto'; [optionale Parameter])__ ####

Fläche einer Wandschichtoberfläche, die von der Kernschicht weg ausgerichtet ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.



#### __Oberfläche('Mitte Brutto'; [optionale Parameter])__ ####

Fläche entlang der Mittellinie einer Wand oder einer Wandschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.


```python
=SurfaceArea('center gross') returns the gross area along the center line of the wall or wall component.

=SurfaceArea('center gross', 'component=core') returns the gross area along the center line of the core component of the wall.
```

#### __Oberfläche('Mitte Netto'; [optionale Parameter])__ ####

Fläche entlang der Mittellinie einer Wand oder einer Wandschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden.


```python
=SurfaceArea('center net') returns the area along the center line of the wall or wall component.

=SurfaceArea('center net', 'min opening area=0.5 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('center net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('center net', 'opening type=Window') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('center net', 'exclude opening type=Window') returns the area along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('center net', 'opening type=Window;WinDoor 6.0') returns the area along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('center net', 'component=core') returns the area along the center line of the core component of the wall.
```

#### __Oberfläche('Kern zugewandt Brutto'; [optionale Parameter])__ ####

Fläche einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.



#### __Oberfläche('Kern zugewandt Netto'; [optionale Parameter])__ ####

Fläche einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.



#### __Oberfläche('Links Brutto'; [optionale Parameter])__ ####

Fläche der linken Wand- oder Wandschichtoberfläche. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.


```python
=SurfaceArea('left gross') returns the gross area of the left side of the wall or wall component.

=SurfaceArea('left gross', 'component=core') returns the gross area of the left side of the core component of the wall.
```

#### __Oberfläche('Links Netto'; [optionale Parameter])__ ####

Fläche der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.


```python
=SurfaceArea('left net') returns the area of the left side of the wall or wall component.

=SurfaceArea('left net', 'min opening area=0.5 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('left net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('left net', 'opening type=Window') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('left net', 'exclude opening type=Window') returns the area of the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('left net', 'opening type=Window;WinDoor 6.0') returns the area of the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('left net', 'component=core') returns the area of the left side of the core component of the wall.
```

#### __Oberfläche('Öffnungen Kern abgewandt'; [optionale Parameter])__ ####

Fläche der Öffnungen auf der Oberfläche einer Wandschicht, die von der Kernschale weg orientiert ist.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.



#### __Oberfläche('Öffnungen Mitte'; [optionale Parameter])__ ####

Fläche der Öffnungen entlang der Mittellinie einer Wand oder einer Wandschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.


```python
=SurfaceArea('openings center') returns the total area of openings along the center line of the wall or wall component.

=SurfaceArea('openings center', 'min opening area=0.5 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings center', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings center', 'opening type=Window') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings center', 'exclude opening type=Window') returns the total area of openings along the center line of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings center', 'opening type=Window;WinDoor 6.0') returns the total area of openings along the center line of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings center', 'component=core') returns the total area of openings along the center line of the core component of the wall.
```

#### __Oberfläche('Öffnungen Kern zugewandt'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf einer Wandschichtoberfläche, die zu der Kernschicht hin ausgerichtet ist. 

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.



#### __Oberfläche('Öffnungen links'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.


```python
=SurfaceArea('openings left') returns the total area of openings on the left side of the wall or wall component.

=SurfaceArea('openings left', 'min opening area=0.5 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings left', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings left', 'opening type=Window') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings left', 'exclude opening type=Window') returns the total area of openings on the left side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings left', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the left side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings left', 'component=core') returns the total area of openings on the left side of the core component of the wall.
```

#### __Oberfläche('Öffnungen rechts'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der rechten Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.


```python
=SurfaceArea('openings right') returns the total area of openings on the right side of the wall or wall component.

=SurfaceArea('openings right', 'min opening area=0.5 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('openings right', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('openings right', 'opening type=Window') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('openings right', 'exclude opening type=Window') returns the total area of openings on the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('openings right', 'opening type=Window;WinDoor 6.0') returns the total area of openings on the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('openings right', 'component=core') returns the total area of openings on the right side of the core component of the wall.
```

#### __Oberfläche('Rechts Brutto'; [optionale Parameter])__ ####

Fläche der rechten Wand- oder Wandschichtoberfläche. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.


```python
=SurfaceArea('right gross') returns the gross area of the right side of the wall or wall component.

=SurfaceArea('right gross', 'component=core') returns the gross area of the right side of the core component of the wall.
```

#### __Oberfläche('Rechts Netto'; [optionale Parameter])__ ####

Fläche der linken Wand- oder Wandschichtoberfläche.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden.


```python
=SurfaceArea('right net') returns the area of the right side of the wall or wall component.

=SurfaceArea('right net', 'min opening area=0.5 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters.

=SurfaceArea('right net', 'min opening area=0.5 sq m', 'max opening area=1 sq m') returns the area of the right side of the wall or wall component, but ignoring any openings under 0.5 square meters or over 1 square meter.

=SurfaceArea('right net', 'opening type=Window') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=SurfaceArea('right net', 'exclude opening type=Window') returns the area of the right side of the wall or wall component, but ignoring any openings that are created by "Window" plug-in objects.

=SurfaceArea('right net', 'opening type=Window;WinDoor 6.0') returns the area of the right side of the wall or wall component, but only taking openings created by "Window" or "WinDoor 6.0" plug-in objects into account.

=SurfaceArea('right net', 'component=core') returns the area of the right side of the core component of the wall.
```

#### __Volumenn()__ ####

Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Volumenn('Brutto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=Volume('gross') returns the gross volume of the wall, wall component, slab or slab component.

=Volume('gross', 'component=core') returns the gross volume of the core wall component.
```

#### __Volumenn('Netto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.


```python
=Volume('net') returns the volume of the wall, wall component, slab or slab component.

=Volume('net', 'min opening volume=10 cu cm') returns the volume of the wall, wall component, slab or slab component, but only taking openings with at least 10 cubic centimeters of volume into account.

=Volume('net', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the volume of the wall, wall component, slab or slab component, but only taking openings with between 10 cubic centimeters and 1 cubic meter of volume into account.

=Volume('net', 'opening type=Window') returns the volume of the wall or wall component, but only taking openings created by "Window" plug-in objects into account.

=Volume('net', 'opening type=Window;WinDoor 6.0') returns the volume of the wall or wall component, but only taking openings created by "Window" and "WinDoor 6.0" plug-in objects into account.

=Volume('net', 'component=core', 'min opening volume=10 cu cm') returns the volume of the core wall component, but only taking openings with a volume of at least 10 cubic centimeters into account.
```

#### __Volumenn('Öffnungen'; [optionale Parameter])__ ####

Das Volumen der Öffnungen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern (Wände), oben, unten (Böden/Decken) oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.

'Öffnungstyp=...': Es werden nur Öffnungen gezählt, die von Objekten mit einem der angegebenen Namen erzeugt wurden. Mehrere Namen können durch ein Komma (Schweiz: Strichpunkt) getrennt werden.

'Öffnungstyp ausschließen=...': Es werden Öffnungen nicht gezählt, die von Objekten mit einem der angegebenen Namen erstellt wurden. Gilt nur für Wände.


```python
=Volume('openings') returns the total volume of openings in the wall, wall component, slab or slab component.

=Volume('openings', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters.

=Volume('openings', 'min opening volume=10 cu cm', 'max opening volume=1 cu m') returns the total volume of openings with a volume of at least 10 cubic centimeters and at most 1 cubic meter.

=Volume('openings', 'opening type=Window') returns the total volume of openings created by "Window" plug-in objects.

=Volume('openings', 'opening type=Window;WinDoor 6.0') returns the total volume of openings created by "Window" and "WinDoor 6.0" plug-in objects.

=Volume('openings', 'component=core', 'min opening volume=10 cu cm') returns the total volume of openings with a volume of at least 10 cubic centimeters in the wall core component.
```

#### __Wandhöhe()__ ####

Höhe von Wänden in der Zeichnung.


```python
Database header cell:
=WallOverallHeight returns the average overall height for each wall object in the database

Spreadsheet cell:
=WallOverallHeight((t=wall)&(sel=true)) returns the average overall height of all walls that are selected in the drawing

```

## Funktionen für WinDoor 6.0


#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



## Funktionen für Window


#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __Volumen(criteria; 'glazing all')__ ####

Returns the total volume of all glazing.


```python
Database header cell:
=VOLUME('glazing all')     Returns the total volume of all glazing.

Spreadsheet cell:
=VOLUME(SEL, 'glazing all')    Returns the total volume of all glazing.

```

#### __Volumen(criteria; 'glazing for sashes')__ ####

Returns the volume of glazing for all sashes except the transom.


```python
Database header cell:
=VOLUME('glazing for sashes')     Returns the volume of glazing for all sashes except the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for sashes')    Returns the volume of glazing for all sashes except the transom.

```

#### __Volumen(criteria; 'glazing for transom')__ ####

Returns the volume of glazing for the transom.


```python
Database header cell:
=VOLUME('glazing for transom')     Returns the volume of glazing for the transom.

Spreadsheet cell:
=VOLUME(SEL, 'glazing for transom')    Returns the volume of glazing for the transom.

```

#### __Volumen(criteria; 'window jamb')__ ####

Returns the volume of all geometry that makes up the Jamb and Mullions.


```python
Database header cell:
=VOLUME('window jamb')     Returns the volume of all geometry that makes up the Jamb and Mullions.

Spreadsheet cell:
=VOLUME(SEL, 'window jamb')   Returns the volume of all geometry that makes up the Jamb and Mullions.

```

#### __Volumen(criteria; 'window sashes')__ ####

Returns the total volume the all sashes (including the transom sash).


```python
Database header cell:
=VOLUME('window sashes')     Returns the total volume the all sashes (including the transom sash).

Spreadsheet cell:
,VOLUME(SEL, 'window sashes')    Returns the total volume the all sashes (including the transom sash).

```

## Funktionen für XPlanung


#### __OBJEKTDATEN('xplanung'; [Objekt]; [Attribut; Index]; Attribut[:Format]; [Index])__ ####

Gibt Attributswerte von XPlanung-Objekten zurück. PARAMETER:
Objekt: (Optional) Das XPlanung-Objekt in dem sich das XPlanung-Attribut befindet.

Attribut: Das XPlanung-Attribute von dem der Wert zurückgegeben wird. Bei einer komplexen Datenstruktur muss zuerst das Übergeordnete Attribute als eigener Parameter angegeben werden.

Format: (Optional) Das Format des zurückzugebenden Werts. Bsp.: 'dachform:kurz'. Wird kein Format angegeben, wird der vollständige Wert zurückgegeben. Bsp.: 'Walmdach (3200)'
...:name oder ...:text: Gibt nur den entsprechenden Textwert zurück. Bsp.: 'Walmdach'.
...:value oder ...:wert: Gibt nur den entsprechenden numerischen Wert zurück. Bsp.: '3200'.
...:short oder ...:kurz: Gibt nur die entsprechende Kurzfom zurück. Bsp.: 'WD'.
...:roman oder ...:römisch: Zahlenwerte werden als Römische Zahl ausgegeben. Bsp.: 'XII' (12).

Index: (Optional) Welcher Wert zurückgegeben wird, wenn mehrere Werte definiert sind. Der erste Wert ist '0', der zweite Wert ist '1' usw. Wird kein Index angegeben (oder '-1') werden alle Werte als Text und durch ';' getrennt zurückgegeben. Bsp.: 'Pultdach (2100); Pultdach (3200)'.

Übersicht der XPlanung-Objekte und Attribute: https://xleitstelle.de/xplanung/releases


```python
=OBJEKTDATEN('xplanung'; 'BP_BaugebietsTeilFlaeche'; 'dachform') Gibt den Werts des Attributs 'dachform' im XPlanung-Objekt 'BP_BaugebietsTeilFlaeche' zurück.

=OBJEKTDATEN('xplanung'; 'dachform') Gibt den Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform'; 1) Gibt den zweiten Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'dachform:kurz') Gibt die Kurzform des Werts des Attributs 'dachform' zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 'h') Gibt den Wert des Attributs 'h' aller Hoehenangaben zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 0; 'h') Gibt den Wert des Attributs 'h' der ersten Hoehenangabe zurück.

=OBJEKTDATEN('xplanung'; 'hoehenangabe'; 2; 'hoehenbezug:kurz')	Gibt die Kurzform des Werts des Attributs 'hoehenbezug' der dritten Hoehenangabe zurück.

```

## Funktionen für Zaun


#### __Tiefe('Sockelbrett')__ ####

Diese Funktion kann auf Zaunobjekte und Unterobjekt Sockelbrett angewandt werden.
Die Tiefe des Sockelbretts, sofern vorhanden.



#### __Tiefe('Horizontale Zaunlatten')__ ####

Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profiltiefe und N/A, wenn gemischte Zaunfelder.



#### __Tiefe('Fertigelemente/Platten')__ ####

Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profiltiefe und N/A, wenn gemischte Zaunfelder.



#### __Tiefe('Strebe'; <Index>)__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Tiefe der aktiven Strebe.

Unterobjekt Strebe: Tiefe der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.



#### __Tiefe('Streben')__ ####

Diese Funktion kann auf Unterobjekt Strebe angewandt werden: Die Tiefe der Streben.



#### __Tiefe('Vertikale Zaunlatten')__ ####

Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Profilbreite und N/A, wenn gemischte Zaunfelder.



#### __Grundfläche('Eckfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundament der Eckpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Eckpfosten und N/A für alle anderen Fundamente.



#### __Grundfläche('Fundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundamente.

Unterobjekt Fundament: Grundfläche des Punktfundaments.



#### __Grundfläche('Torfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundamente der Zauntorpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Torpfosten und N/A für alle anderen Fundamente.



#### __Grundfläche('Zwischenfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Gesamtgrundfläche aller Punktfundament der Zwischenpfosten.

Unterobjekt Fundament: Grundfläche des Punktfundaments Zwischenpfosten und N/A für alle anderen Fundamente.



#### __Objektdaten('Fundamenttyp')__ ####

Diese Funktion kann auf nur auf Unterobjekt Fundament angewandt werden.

Gibt den Fundamenttyp zurück. Mögliche Werte sind Punktfundament für Eck-, Zwischen- oder Zauntorpfosten.



#### __Objektdaten('Füllungstyp')__ ####

Diese Funktion kann auf nur auf Unterobjekt Füllung angewandt werden.

Gibt die Füllung der Zaunfelder zurück. Mögliche Werte sind Fertigelement, vertikale Zaunlatten und horizontale Zaunlatten.



#### __Objektdaten('Name')__ ####

Diese Funktion kann auf alle Unterobjekte des Zaun angewandt werden: Pfosten, Zauntor, Zaunfeld und Strebe.

Name der verwendeten Symboldefinition.



#### __Objektdaten('Pfostentyp')__ ####

Diese Funktion kann auf nur auf Unterobjekt Pfosten angewandt werden.

Gibt den Pfostentyp zurück . Mögliche Werte sind Eckpfosten, Zwischenpfosten und Torpfosten.



#### __Objektdaten('Strebenindex')__ ####

Diese Funktion kann auf nur auf Unterobjekt Strebe angewandt werden.

Gibt den Index des Strebentyps zurück, beginnend mit Index 1.



#### __Breite('Horizontale Zaunlatten')__ ####

Diese Funktion kann auf Zaunobjekte und deren Zaunfelder angewandt werden:

BESCHREIBUNG:
Profilbreite und N/A bei gemischten Zaunfelder.



#### __Breite('Vertikale Zaunlatten')__ ####

Diese Funktion kann auf Zaun-Objekte und Unterobjet Zaunfeld angewandt werden:

BESCHREIBUNG:
Gibt die Profildicke zurück und N/A bei gemischten Zaunfelder.



#### __Höhe('Eckfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl allerPunktfundamente der Eckpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht und N/A für runde Punktfundamente.



#### __Höhe('Eckpfosten')__ ####

Diese Funktion ist identisch mit Länge('Eckpfosten').



#### __Höhe('Blenden')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Höhe der Blende (bei mehreren Blenden die Höhe der ersten Blende).

Unterobjekt Strebe: Gibt nur dann ein Ergbnis zurück, wenn Blende und keine Strebe.



#### __Höhe('Fundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps.



#### __Höhe('Torfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente der Torpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps. N/A, wenn Fundamenttyp nicht für Zauntore.



#### __Höhe('Torpfosten')__ ####

Diese Funktion ist identisch mit Länge('Torpfosten').



#### __Höhe('Zauntore')__ ####

Diese Funktion kann nur auf das Unterobjekt Zauntor angewandt werden und gibt die Höhe des Zauntors zurück.



#### __Höhe('Sockelbrett')__ ####

Diese Funktion kann auf das Zaunobjekt und das Unterobjekt Sockelbrett angewandt werden.
Die Höhe des Sockelbretts, sofern vorhanden.



#### __Höhe('Fertigelemente/Platten')__ ####

Diese Funktion kann auf Zaunobjekte und Unterobjekt Zaunfelder angewandt werden.
Die Höhe der Fertigelemente und N/A, wenn gemischte Zaunfelder.



#### __Höhe('Pfosten')__ ####

Diese Funktion ist identisch mit Länge('Pfosten').



#### __Höhe('Strebe'; <Index>)__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Breite der aktiven Strebe.

Unterobjekt Strebe: Breite der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.



#### __Höhe('Streben')__ ####

Diese Funktion kann angewandt werden auf:
›nUnterobjekt Strebe: Die Höhe der Strebe.



#### __Höhe('Zwischenfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl aller Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Höhe Punktfundament aus Tiefe im Erdreich + Drainageschicht des entsprechenden Fundamenttyps. N/A, wenn Fundamenttyp nicht für Zwischenpfosten.



#### __Höhe('Zwischenpfosten')__ ####

Diese Funktion ist identisch mit Länge('Zwischenpfosten').



#### __Höhe('Oberkante zum Boden')__ ####

Diese Funktion kann auf Zaun-Objekte angewandt werden.

Der höchte Punkt aller Streben, wenn das Zaunfeld 'Nur Querstreben' ist.

Andernfalls den Wert von 'Oberkante zum Boden'.



#### __Anzahl('Eckfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl aller Eckfundamente.

Unterobjekt Fundament: Ergebnis 1 für Punktfundament Eckpfosten und N/A für alle anderen Fundamente.



#### __Anzahl('Eckpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Eckpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Eckpfosten.



#### __Anzahl('Blenden')__ ####

Die Funktion kann angewendet werden auf:

Zaun-Objekt: Die Gesamtzahl der Streben, die als Blenden behandelt werden.

Unterobjekt Strebe: Gibt 1 zurück, wenn Blende und keine Strebe.



#### __Anzahl('Fundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente aller Pfosten.

Unterobjekt Pfosten: Ergebnis 1, wenn Punktfundament.



#### __Anzahl('Torfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente der Torpfosten.

Unterobjekt Pfosten: Ergebnis 1, Punktfundament Torpfosten und N/A für alle anderen Fundamente.



#### __Anzahl('Torpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Torpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Torpfosten.



#### __Anzahl('Zauntore')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Zauntore.

Unterobjekt Tor: Ergebnis 1 für Zauntore.



#### __Anzahl('Sockelbrett')__ ####

Die Funktion kann angewendet werden auf:

Zaun-Objekt: Anzahl der Sockelbretter, sofern in den Einstellungen ausgewählt.

 Unterobjekt Sockelbrett: Gibt 1 zurück.



#### __Anzahl('Horizontale Zaunlatten')__ ####

Diese Funktion kann angewandt werden auf:

Zaun-Objekt: Gesamtzahl der horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Gibt eine 1 für jedes Zaunfeld mit horizontalen Zaunlatten. N/A, wenn die Zaunfelder unterschiedlich gefüllt sind.



#### __Anzahl('Fertigelemente/Platten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl aller Fertigelemente im Zaun.

Unterobjekt Fertigelement: Ergebnis 1 für Fertigelement und N/A bei gemischten Zaunfelder.



#### __Anzahl('Pfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Pfosten.

Unterobjekt Pfosten: Ergebnis 1 für Pfosten.



#### __Anzahl('Strebe'; <Index>)__ ####

Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Ergebnis ist 1, wenn der Index innerhalb der Anzahl der Streben liegt, oder 0, wenn der Index größer als die Anzahl ist.

Unterobjekt Strebe: Ergebnis ist 1, wenn die Strebe dem Index entspricht. Andernfalls N/A.



#### __Anzahl('Streben')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Streben.

Unterobjekt Strebe: Ergebnis 1 für Strebe.



#### __Anzahl('Zwischenfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Ergebnis 1 für Punktfundament Zwischenpfosten und N/A für alle anderen Fundamente.



#### __Anzahl('Zwischenpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtzahl der Zwischen- bzw. Mittelpfosten.

Unterobjekt Pfosten: Ergebnis 1 für Mittelpfosten.



#### __Anzahl('Vertikale Zaunlatten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Die Anzahl der vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Ergebnis 1, wenn vertikale Zaunlatten vorhanden sind. N/A, wenn gemischte Zaunfelder. 



#### __Länge('2D')__ ####

Diese Funktion kann auf Zaun-Objekte angewandt werden:

BESCHREIBUNG:
2D-Länge des Zaun unter Berücksichtigung eines Versatzes vom Pfad.



#### __Länge('3D')__ ####

Diese Funktion kann auf Zaun-Objekte angewandt werden:

BESCHREIBUNG:
3D-Länge des Zaun unter Berücksichtigung eines Versatzes vom Pfad.



#### __Länge('Eckpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Eckpfosten.



#### __Länge('Blenden')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Blenden mit gleichen Index. Bei mehreren Blenden wird die erste Blende genommen.

Unterobjekt Strebe:  Länge der Blende und N/A, wenn keine Blende, sondern Strebe.



#### __Länge('Torfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Torpfosten.



#### __Länge('Zauntore')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Zauntore.

Unterobjekt Zauntor: Länge der Tors entlang des Zaunverlaufs.



#### __Länge('Sockelbrett')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Sockelbretter.

Sockelbrett: Länge des Sockelbretts.



#### __Länge('Horizontale Zaunlatten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Länge der horizontalen Zaunlatte. Sie wird von Start- zu Endpfosten durch den Pfadverlauf (gerade und gekrümmt) des Zauns bestimmt. N/A bei gemischten Zaunfelder.



#### __Länge('Fertigelemente/Platten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Fertigelemente.

Unterobjekt Zaunfeld: Länge des Fertigelements. N/A bei gemischten Zaunfelder.



#### __Länge('Pfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Pfosten.

Unterobjekt Pfosten:Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich.



#### __Länge('Strebe'; <Index>)__ ####

Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Gesamtlänge aller Streben, auf die mit Index verwiesen wird.

Unterobjekt Strebe: Länge der Strebe, auf die der Index verweist, und N/A, wenn der Index auf keine Strebe verweist.



#### __Länge('Streben')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller Streben.

Unterobjekt Strebe:Länge der Strebe.



#### __Länge('Zwischenpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge der Pfosten.

Unterobjekt Pfosten: Länge des Pfostens gemessen von der Spitze bis zum anderen Ende im Erdreich. N/A, wenn kein Zwischenpfosten.



#### __Länge('Vertikale Zaunlatten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtlänge aller vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Länge der vertikalen Zaunlatte. Sie wird von Start- zu Endpfosten durch den Pfadverlauf (gerade und gekrümmt) des Zauns bestimmt. N/A bei gemischten Zaunfelder.



#### __Oberfläche('Blenden')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtoberfläche aller Blenden.

Unterobjekt Strebe: Oberfläche der Blende und N/A, wenn keine Blende, sondern Strebe.



#### __Oberfläche('Fertigelemente/Platten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtoberfläche aller Fertigelemente.

Unterobjekt Zaunfeld: Oberfläche des Fertigelements und N/A bei gemischten Zaunfeldern.



#### __Volumenn()__ ####

Diese Funktion kann auf Zaun-Objekte angewandt werden:

Gesamtvolumen des Zaun-Objekts.



#### __Volumenn('Eckfundament')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Eckpfosten.

Unterobjekt Fundament: Volumen des Fundaments. N/A, wenn nicht Punktfundament Eckpfosten.



#### __Volumenn('Eckpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Eckpfosten.

Unterobjekt Pfosten: Volumen des Eckpfostens. N/A, wenn nicht Eckpfosten.



#### __Volumenn('Fundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente.

Unterobjekt Fundament: Volumen des Punktfundaments.



#### __Volumenn('Torfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Torpfosten.

Unterobjekt Fundament: Volumen des Punktfundaments. N/A, wenn nicht Punktfundament für Zauntorpfosten.



#### __Volumenn('Torpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Torpfosten.

Unterobjekt Pfosten: Volumen des Torpfostens. N/A, wenn nicht Torpfosten.



#### __Volumenn('Zauntore')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Zauntore.

Unterobjekt Zauntor: Volumen des Zauntors.



#### __Volumenn('Sockelbrett')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Sockelbretter.

Unterobjekt Sockelbrett: Volumen des Sockelbretts.



#### __Volumenn('Horizontale Zaunlatten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller horizontalen Zaunlatten.

Unterobjekt Zaunfeld: Volumen der horizontalen Zaunlatten und N/A bei gemischten Zaunfeldern.



#### __Volumenn('Fertigelemente/Platten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Fertigelemente.

Unterobjekt Zaunfeld: Volumen des Fertigelements und N/A bei gemischten Zaunfeldern.



#### __Volumenn('Pfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Pfosten.

Unterobjekt Pfosten: Volumen des Pfostens.



#### __Volumenn('Strebe'; <Index>)__ ####

Diese Funktion kann mit folgenden Objekten verwendet werden:

Zaunobjekt: Gesamtvolumen aller Streben, die dem Index entsprechen

Unterobjekt Strebe: Volumen der Strebe, die dem Index entspricht. Andernfalls N/A.



#### __Volumenn('Streben')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Streben.

Unterobjekt Strebe: Volumen der Strebe, wobei Tiefe und Höhe ungleich Null sein müssen.



#### __Volumenn('Zwischenfundamente')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Punktfundamente der Zwischenpfosten.

Unterobjekt Fundament: Volumen des Punktfundaments des Zwischenpfostens. N/A, wenn nicht Punktfundament Zwischenpfosten. 



#### __Volumenn('Zwischenpfosten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller Zwischenpfosten.

Unterobjekt Pfosten: Volumen des Zwischenpfostens. N/A, wenn kein Zwischenpfosten.



#### __Volumenn('Vertikale Zaunlatten')__ ####

Diese Funktion kann auf folgende Objekte angewandt werden:

Zaunobjekt: Gesamtvolumen aller vertikalen Zaunlatten.

Unterobjekt Zaunfeld: Volumen der vertikalen Zaunlatten und N/A bei gemischten Zaunfeldern.



## Logik


#### __Wechseln(Zahl; Wert1; Wert2; ... Wert_keine_Übereinstimmung)__ ####

Verwendet je nach Zahl Wert1 oder Wert2 oder Wert3, usw. Wenn kein Wert verfügbar ist, wird Wert_keine_Übereinstimmung verwendet.


```python
=switch(3, 10, 20, 30, 40, 50, 60, 'no match') returns 30

```

#### __IFS((Logik1); Wert1; (Logik2); Wert2; ...; (Logikn); Wertn))__ ####

Eines von mehreren möglichen Ergebnissen basierend auf einer Reihe von Abfragen. Der erste Wert, der die Abfrage erfüllt, wird gewählt.


```python
=IFS(A4>30, 'yes', A4<=30, 'no') returns 'yes' if the number in the cell A4 is >30. Else, if it is <=30 'no' is returned
=IFS(A4>30, 'yes', A4<30, 'no', TRUE, 'exact') returns 'exact' if the number in the cell A4 is exactly 30, 'yes' when >30, and 'no' when <30

=IFS(COND1; VALUE1; COND2; VALUE2; ELSE; 'ELSE') this example uses ELSE as a string condition, which evaluates to TRUE as it is non-empty string
```

#### __Exakt(Wert1; Wert2)__ ####

Wahr, wenn beide Werte genau gleich sind. Bei Zeichenketten wird ein Vergleich unter Berücksichtigung der Groß-/Kleinschreibung durchgeführt.


```python
=exact('text', 'text') returns True, while exact('Text', 'text') will return False.

```

#### __IstUngültig(Wert)__ ####

Wahr, wenn der Wert ungültig (N/A) ist.


```python
=IF(IsNA(Angle('energos')), '-', 'has value') On a database row, calculates the Energos angle of the objects, and decides which value to output based on if energos is applicable or not.

Note, you can use IfNA in order to use alternative value only when it's not applicable, the 'Angle' would have to be repeated for the IF function.


```

#### __IfUngültig(Wert; Wert_wenn_ungültig)__ ####

Wenn der Wert den Inhalt Ungültig (n/a) hat, wird der Inhalt von Wert_wenn_ungültig verwendet, andernfalls der Inhalt von Wert selbst.


```python
=IfNA(Angle('energos'), '-') On a database row, calculates the Energos angle of the objects, and if they are not applicable, would use '-'


```

#### __ErsterNichtLeer(Wert1; Wert2; Wert3; ...)__ ####

Wert1 wird verwendet, wenn nicht leer, andernfalls Wert2, sofern nicht leer, sonst Wert3, wenn nicht leer,usw. Leer bedeutet ohne Zeichenkette, Null oder ungültiger (n/a) Wert. Gibt es keine Übereinstimmung wird ungültig (n/a) zurückgegeben.


```python
=FirstNonEmpty('Format-1'.'data', B1, 'Empty')

Return the value of the data field of the Format-1, if empty return B1, or the string 'Empty' if that is empty too.


```

#### __IstFehler(Wert)__ ####

Wahr, wenn der Wert ein Fehler verursacht.



#### __IfFehler(Fehler; Wert_wenn_Fehler)__ ####

Wenn der Wert einen Fehler beinhaltet, wird der Inhalt von Wert_wenn_Fehler verwendet, andernfalls der Inhalt von Wert selbst.



#### __IF((Bedingung); ‘dann’; ‘sonst’)__ ####

Falls (Bsp. “=if((x>75);‘zu teuer’;‘Preis OK’”), d.h. verwende ’dann’, wenn ’Bedingung’ eintritt, verwende ’sonst’, wenn ’Bedingung’ nicht eintritt.


```python
=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition') If no condition value was set for the existing tree object, the value in this cell is a dash; otherwise, the value in this cell is the condition value that was set for the tree object.

=if(('Existing Tree'.'Condition'='Not Set'), '-', 'Existing Tree'.'Condition')

```

## Math. Formeln


#### __Runden(x)__ ####

Rundet die Zahl.


```python
=round(2.345) returns 2

```

#### __sin(x)__ ####

Sinus von x.


```python
=sin(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the sine of the angle

```

#### __cos(x)__ ####

Cosinus des Winkels x.


```python
=cos(deg2rad(23)) converts a 23-degree angle to its radian equivalent, and returns the cosine of the angle

```

#### __exp(x)__ ####

e hoch x (e=2,71828182845904).


```python
=exp(2) returns the numeric value of e raised to the power of 2

```

#### __ln(x)__ ####

Der natürliche Logarithmus (Basis e) von x.


```python
=ln(12) returns the natural logarithm of 12

```

#### __Wurzel(x)__ ####

Wurzel von x.


```python
=sqrt(D27) returns the square root of the number in cell D27

```

#### __atan(x)__ ####

Arcustangens des Winkels x.


```python
=atan(A3) returns the angle for which the tangent value is given in cell A3

```

#### __radgrad(x)__ ####

Konvertiert Radianten in Grad (x Radianten => Resultat in Grad).


```python
=rad2deg(0.5235987) converts the radian angle measurement to its degree equivalent

```

#### __gradrad(x)__ ####

Konvertiert Grad in Radianten (x Grad => Resultat in Radianten).


```python
=deg2rad(47) converts the 47-degree angle measurement to its radian equivalent

```

#### __asin(x)__ ####

Arcussinus des Winkels x.


```python
=asin(A3) returns the angle for which the sine value is given in cell A3

```

#### __acos(x)__ ####

Arcuscosinus des Winkels x.


```python
=acos(3/5) returns the angle for which the cosine value is 3/5

```

#### __Abrunden(x; Dezimalstellen)__ ####

Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen ab.


```python
=rounddown(2.345, 2) returns 2.34

```

#### __Aufrunden(x; Dezimalstellen)__ ####

Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen auf.


```python
=roundup(2.345, 2) returns 2.35

```

#### __Betrag(x)__ ####

Der Betrag bzw. absolute Wert ohne Vorzeichen von x.


```python
=abs(-12) returns the absolute value of the number -12

```

#### __Quotient(Divident; Divisor)__ ####

Berechnet den Quotienten und den Rest einer ganzzahligen Division.


```python
=quotient(5, 2) returns 2

You can clculate the remainder by using the MOD operator
=5 MOD 2
```

#### __ggT(x1; x2; …)__ ####

Größter gemeinsamer Teiler der Zahlengruppe.


```python
=gcd(5, 10, 20) returns 5

```

#### __kgT(x1; x2; …)__ ####

Kleinster gemeinsamer Teiler der Zahlengruppe.


```python
=lcm(2, 5, 11) returns 110

```

#### __Zahlenmitte(x1; x2; …)__ ####

Gibt die Mitte der Zahlengruppe zurück.


```python
=median(1, 2, 3, 4, 5, 6) returns 3.5

```

#### __logx(x; Basis)__ ####

Der Logarithmus zur angegebenen Basis von x.


```python
=logx(16, 2) returns 4

```

#### __Exponent(x; Exponent)__ ####

x hoch Exponent.


```python
=power(10, 3) returns 1000

```

#### __WurzelPi(x)__ ####

Wurzel (x * pi).


```python
=sqrtpi(3.1415) returns 3.142 (square root of pi*3.1415)

```

#### __Quadratsumme(x1; x2; …)__ ####

Die Summe der Quadrate der Zahlen.


```python
=sumsq(0, 1, 2, 3, 4, 5) returns 55

```

#### __Zufallszahlgenerator(x; y)__ ####

Eine zufällige Zahl zwischen dem unteren und oberen Wert, einschließlich dem unteren, jedoch nicht dem oberen Wert.


```python
=randBetween(10, 100) returns a random number in the range [10, 100]

```

#### __Zufallszahl()__ ####

Eine zufällige Zahl zwischen 0 und 1, einschließlich der 0, jedoch nicht die 1.


```python
=rand() returns a random number in the range [0, 1)

```

#### __Aufrundung(x; [Signifikanz])__ ####

Die nächstgelegene Ganzzahl, die nicht kleiner ist als x. Ist ein optionaler Wert (Signifikanz) angegeben, wird auf ein Vielfaches dieses Wertes gerundet.


```python
=ceiling(123.123, 0.01) returns 123.13 (123.123 rounded up to the nearest multiple of 0.01)

```

#### __Abrundung(x; [Signifikanz])__ ####

Die nächstgelegene Ganzzahl, die nicht größer ist als x. Ist ein optionaler Wert (Signifikanz) angegeben, wird auf ein Vielfaches dieses Wertes gerundet.


```python
=floorNum(123.123, 0.01) returns 123.12 (123.123 rounded down to the nearest multiple of 0.01)

```

#### __Kürzen(x; [Dezimalstellen])__ ####

Kürzt x auf die angegebenen Dezimalstellen.


```python
=truncate(123.123, 2) returns 123.12

```

#### __durchschnitt(x1; x2;...)__ ####

Durchschnitt (Mittelwert) der angegebenen Zahlen.


```python
=average(A2,A10..A12) returns the average of the numbers contained in cells A2, A10, A11, and A12

```

#### __int(x)__ ####

x abgerundet, d.h. ohne Kommastellen (Bsp. “=int(3,87)”, Resultat: “3”).


```python
=int(3.8) returns the value 3

```

#### __log(x)__ ####

Der Logarithmus zur Basis 10 (log) von x.


```python
=log(100) returns the base 10 logarithm of 100

```

#### __max(x1; x2;...)__ ####

Gibt die größte Zahl der Zahlengruppe zurück.


```python
=max(C5,C7,C9) returns the largest of the numbers that are in cells C5, C7, and C9

```

#### __min(x1; x2;...)__ ####

Gibt die kleinste Zahl der Zahlengruppe zurück.


```python
=min(C5,C7,C9) returns the smallest of the numbers that are in cells C5, C7, and C9

```

#### __tan(x)__ ####

Tangens von x.


```python
=tan(deg2rad(32)) converts a 32-degree angle to its radian equivalent, and returns the tangent of the angle

```

#### __sum(x1; x2; ...)__ ####

Summe der Zahlen x1, x2, ... usw.


```python
=sum(A2,A10..A12) returns the sum of the numbers contained in cells A2, A10, A11, and A12

```

## Objekte

### Allgemein


#### __Tiefe([optionale Parameter])__ ####

Tiefe des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.



#### __Gewicht([optionale Parameter])__ ####

Gewicht der Objekte. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.



#### __ProjizierteFläche([optionale Parameter])__ ####

Projizierte Fläche des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.



#### __Grundfläche([optionale Parameter])__ ####

Die Grundfläche des Objekts, z.B. Gebäude. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.



#### __Querschnittsfläche([optionale Parameter])__ ####

Querschnittsfläche des Objekts. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück. Die verfügbaren Optionen werden separat aufgelistet.



#### __FlächeSpezial([optionale Parameter])__ ####

Spezialfläche, die üblicherweise durch Parameter definiert ist. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.



#### __Objektdaten('Beschreibung Klasse')__ ####

Beschreibung der Klasse des Objekts.



#### __Objektdaten('Klassifikation'; Klassifikation_Index; Parameter_Index)__ ####

Returns the specified classification data from the object

Available options for classification_index:
1 -	Primary Classification;
2 -	Secondary Classification;
3 -	Tertiary Classification;

Available options for param_index:
1 -	Is classified;
2 -	Standard Name;
3 -	Classification Code;
4 -	Classification Description;
5 -	Classification System;
6 -	Standard Source;
7 -	Standard Edition;
8 -	Standard Edition Date;
9 -	Standard Location;
10 -	Standard Description;


```python
Available options for param_index:
	1 - Is classified
	2 - Standard Name
	3 - Classification Code
	4 - Classification Description
	5 - Classification System
	6 - Standard Source
	7 - Standard Edition
	8 - Standard Edition Date
	9 -	Standard Location
	10 - Standard Description;

Examples:
	Database header cell:
	=ObjectData('Classification', 1, 1)        		Returns True if the Primary Classification has value for each object in the DB row.

	=ObjectData('Classification', 1, 2)        		Returns Classification Rule Set name set to the Primary Classification for each object in the DB row.

	=ObjectData('Classification', 2, 5)        		Returns Classification System name set to the Secondary Classification for each object in the DB row.

	=ObjectData('Classification', 3, 10)       		Returns Classification Standard Description set to the Tertiary Classification for each object in the DB row.

	Spreadsheet cell:
	=ObjectData(SEL=TRUE, 'Classification', 1, 1)    Returns True if the Primary Classification has value for the selected 	object.

	=ObjectData(SEL=TRUE, 'Classification', 1, 2)    Returns Classification Rule Set name set to the Primary Classification for the selected object.

	=ObjectData(SEL=TRUE, 'Classification', 2, 5)    Returns Classification System name set to the Secondary Classification for the selected object.

	=ObjectData(SEL=TRUE, 'Classification', 3, 10)   Returns Classification Standard Description set to the Tertiary Classification for the selected object.
```

#### __Objektdaten('Schicht'; <Wert> [; <Schichtindex>])__ ####

Bei einem Objekt gibt die Funktion den angegebenen <Wert> der Schicht des Objekts mit dem angegebenen <Schichtindex> zurück, oder die Kernschicht, wenn <Schichtindex> fehlt. Wird die Funktion für eine Schicht aufgerufen, gibt sie den angegebenen <Wert> für diese Schicht zurück. Wenn der optionale <Schichtindex> hinzugefügt wird, gibt die Funktion den Schichtwert nur für Schichten zurück, die mit dem angegebenen Index übereinstimmen.

Die folgenden Werte werden unterstützt: "Name", "Funktion", "Klasse", "Klassenbezeichnung", "Klassenbeschreibung", "Dicke", "Lambda", "Wert", "Nettofläche", "Nettovolumen".

Siehe das Beispiel für weitere Details.


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

#### __Objektdaten('Name')__ ####

Name des Objekts. Bei einem Symbol ohne Namen wird der Name der Symboldefinitionsressource zurückgegeben.


```python
Database header cell:
=ObjectData('General Name')        Returns the name for each object in the DB row.
                                If the object is a symbol, it will return the name of the symbol

Spreadsheet cell:
=ObjectData(SEL=TRUE, 'General Name')    Returns the name for the selected object
                                      If the object is a symbol, it will return the name of the symbol

```

#### __Objektdaten(Filter; 'Teilbestand'; part_univ_name; part_index)__ ####

Name des Bauteils im Bestand von einem Objekt, das den Bestand unterstützen.



#### __Objektdaten(Filter; 'Teilbestand Param'; part_univ_name; part_index; param_index)__ ####

Wert von Objekteinstellungen eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.



#### __Objektdaten(Filter; Teilbestand quantity'; part_univ_name; part_index)__ ####

Menge eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.



#### __Objektdaten('Beschreibung Ebene')__ ####

Beschreibung der Ebene des Objekts.



#### __Objektdaten('Lastinfo'; Objekteigenschaft; [Lastindex])__ ####

Informationen der Last eines Lastobjekts. Objekteigeschaft ist 'Position', ' Last-ID', 'Verteiltes Gewicht' und 'Gesamtgewicht'. Ist kein Lastindex angegeben,wird die erste Last verwendet.



#### __Objektdaten('Objekt Variable'; variable_index)__ ####

Objektvariable des Objekts.



#### __Objektdaten('Universal_Wert'; Format_Name; Feld_Name; [Ist Format])__ ####

Gibt den universellen Wert des angegebenen Feldes des Datensatzes oder des Formats zurück, wenn der optionale Parameter Wahr ist. Es funktioniert mit dem parametrischen Format, wenn Format_Name leer ist. Ergibt Ungültig (N/A), wenn das Objekt nicht mit dem Datensatz verknüpft ist oder das Format nicht existiert.


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

#### __Objekttyp()__ ####

ID-Nummer des Objekttyps.


```python
Database header cell:
=ObjectType returns the object type value for each object in the database

Spreadsheet cell:
=ObjectType(sel=true) returns the object type value of the selected object; for example, the object type value for a light is 81

```

#### __Breite([optionale Parameter])__ ####

Breite (Delta x) von Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Width returns the width (delta x) for each object in the database

Spreadsheet cell:
=Width(sel=true) returns the combined width (delta x value) of the selected object

```

#### __Höhe([optionale Parameter])__ ####

Gibt das Delta y (Höhe) von Objekten zurück. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück. Die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Height returns the height (delta y) for each object in the database

Spreadsheet cell:
=Height(sel=true) returns the combined height (delta y) value of the selected objects in the drawing

```

#### __Zählen([optionale Parameter])__ ####

Anzahl von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Count returns the total number of objects for each row in the database

Spreadsheet cell:
=Count(s='simple sofa') returns the total number of symbol objects named “simple sofa” in the drawing

When used with the COUNT function, the SEL (selection status) criterion counts objects that are actually non-selectable, such as the individual items within a group. The VSEL (visible selection status) criterion counts only the visibly selected items, which is the same counting method used for the Object Info palette. For example, if you select and count a group that has 11 items in it, the SEL criterion returns a value of 12 (the group, plus the 11 items). The VSEL criterion returns a value of 1 (the group only).

```

#### __Anzahl('Unterobjekte'; [Unterobjektname])__ ####

Die Anzahl der Unterobjekte in einem intelligenten Objekt. Wird ein Unterobjektname angegeben, werden nur Unterobjekte mit diesem Namen gezählt. Wenn der Unterobjektname keinem Unterobjekt entspricht, wird er als Eigenschaft (Parameter) behandelt.



#### __Winkel()__ ####

Winkel von Geraden und Wänden, Innenwinkel von Kreisbögen (in Grad), Neigungswinkel von Dachflächen, Profilstützen und Böden (in Grad).


```python
Database header cell:
=Angle returns the angle of each object in the database

Spreadsheet cell:
=Angle((t=arc)&(n='arc-1')) returns the sweep angle of the arc object named “arc-1” in the drawing

```

#### __Gespiegelt()__ ####

Gibt 1 zurück, wenn das Objekt gespiegelt ist, andernfalls wird 0 zurückgegeben.


```python
Database header cell:
=IsFlipped returns the flip state for each object in the database

Spreadsheet cell:
=IsFlipped(PON='window') returns the flip state of the window object if it resolves to only one, otherwise returns the total number of window objects in the drawing that are flipped

```

#### __xKoordinate()__ ####

x-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Database header cell:
=XCoordinate returns the x coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __yKoordinate()__ ####

y-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Database header cell:
=YCoordinate returns the y coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __zKoordinate()__ ####

z-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Database header cell:
=ZCoordinate returns the z coordinate value for each symbol, point plug-in object, and locus in the database

```

#### __Fläche()__ ####

Gesamtfläche von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Area returns the area of each object in the database

Spreadsheet cell:
=Area(t=rect) returns the combined area of all rectangle objects in the drawing

```

#### __UnterKante()__ ####

Am weitesten unten liegender Punkt (kleinster y-Wert) von Objekten in der Zeichnung.


```python
Database header cell:
=BotBound returns the bottom 2D boundary of each object in the database

Spreadsheet cell:
=BotBound(t=locus) returns the bottom 2D boundary of the locus that has the lowest bottom 2D boundary value in the drawing

```

#### __OberKante()__ ####

Am weitesten oben liegender Punkt (größter y-Wert) von Objekten in der Zeichnung.


```python
Database header cell:
=TopBound returns the top 2D boundary for each object in the database

Spreadsheet cell:
=TopBound(sel=true) returns the top 2D boundary of the topmost selected object

```

#### __LinkeKante()__ ####

Am weitesten links liegender Punkt (kleinster x-Wert) von Objekten in der Zeichnung.


```python
Database header cell:
=LeftBound returns the left 2D boundary for each object in the database

Spreadsheet cell:
=LeftBound(t=locus) returns the left 2D boundary of the leftmost locus in the drawing

```

#### __RechteKante()__ ####

Am weitesten rechts liegender Punkt (größter x-Wert) von Objekten in der Zeichnung.


```python
Database header cell:
=RightBound returns the right 2D boundary for each object in the database

Spreadsheet cell:
=RightBound(t=rect) returns the right 2D boundary of the rightmost rectangle in the drawing

```

#### __Umfang([optionale Parameter])__ ####

Umfang des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Perim returns the perimeter for each object in the database

Spreadsheet cell:
=Perim(sel=true) returns the total perimeter of all selected objects
```

#### __Länge([optionale Parameter])__ ####

Länge von Geraden und Wänden in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Length returns the length for each object in the database

Spreadsheet cell:
=Length(t=line) returns the total length of all line objects in the drawing

```

#### __xMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in x-Richtung.


```python
Database header cell:
=XCenter returns the x coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=XCenter(sel=true) returns the x coordinate value of the center of the 2D boundary of the selected object

```

#### __yMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in y-Richtung.


```python
Database header cell:
=YCenter returns the y coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=YCenter(sel=true) returns the y coordinate value of the center of the 2D boundary of the selected object

```

#### __zMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in z-Richtung.


```python
Database header cell:
=ZCenter returns the z coordinate value of the center of the 2D boundary for each object in the database

Spreadsheet cell:
=ZCenter(sel=true) returns the z coordinate value of the center of the 2D boundary of the selected object

```

#### __Oberfläche([optionale Parameter])__ ####

Oberfläche von 3D-Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=SurfaceArea returns the surface area for each object in the database

Spreadsheet cell:
=SurfaceArea(st=sphere) returns the total surface area of all sphere objects in the drawing

```

#### __Volumenn([optionale Parameter])__ ####

Volumen des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Database header cell:
=Volume returns the volume for each object in the database

Spreadsheet cell:
=Volume(t=xtrd) returns the total volume of all extrude objects in the drawing

```

#### __Grafik()__ ####

Grafische Abbildung von Objekten in der Zeichnung.


```python
Database header cell:
=Image returns the image for each object in the database

Spreadsheet cell:
=Image(s='cabinet') returns the image of the symbol named “Cabinet”

```

#### __ObjU-Wert()__ ####

U-Wert der Objekte.


```python
Database header cell:
=ObjectUValue returns the U-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectUValue(n='wall-1') returns the U-value for the wall named “wall-1”
```

#### __ObjR-Wert()__ ####

R-Wert der Objekte.


```python
Database header cell:
=ObjectRValue returns the R-value for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjectRValue(n='wall-1') returns the R-value for the wall named “wall-1”

```

#### __ObjInEnergos()__ ####

Gibt den Wert 1 zurück, wenn das Objekt in den Energieberechnungen berücksichtigt wird. Andernfalls wird der Wert 0 Zurückgegeben.


```python
Database header cell:
=ObjIncludeInEnergos returns the Energos status for each wall, round wall, roof, roof face, slab, door, and window object in the database

Spreadsheet cell:
=ObjIncludeInEnergos(t=wall) returns the Energos status for all walls in the drawing

```

#### __Stilname()__ ####

Gibt den Stilnamen zurück, der vom Objekt verwendet wird.


```python
Database header cell:
=PluginStyleName returns the plug-in style name for each object in the database

Spreadsheet cell:
=PluginStyleName(sel=true) returns the plug-in style name for all selected objects in the drawing

```

#### __Ebene()__ ####

Name der Ebene der Objekt.


```python
Database header cell:
=Layer returns the layer name of each object in the database

Spreadsheet cell:
=Layer(sel=true) returns the layer name of the selected objects in the drawing

```

#### __Klasse()__ ####

Name der Klasse der Objekte.


```python
Database header cell:
=Class returns the class name of each object in the database

Spreadsheet cell:
=Class(sel=true) returns the class name of the selected objects in the drawing

```

#### __ObjektTypName()__ ####

Name der Objekttypen.


```python
Database header cell:
=ObjectTypeName returns the type name for each object in the database

Spreadsheet cell:
=ObjectTypeName(sel=true) returns the type name of the selected objects in the drawing

```

#### __Name()__ ####

Name der Objekte.


```python
Database header cell:
=Name returns the name for each object in the database

Spreadsheet cell:
=Name(sel=true) returns the name of the selected objects in the drawing

```

#### __Geschoss()__ ####

Name des Geschosses, auf welchem die Objekte liegen.


```python
Database header cell:
=Story returns the story name for each object in the database

Spreadsheet cell:
=Story(sel=true) returns the story name of the selected objects in the drawing

```

#### __Mosaikfüllung()__ ####

Name des Mosaiks, mit dem die Objekte gefüllt sind.


```python
Database header cell:
=TileFill returns the tile fill name for each object in the database

Spreadsheet cell:
=TileFill(sel=true) returns the tile fill name of the selected objects in the drawing

```

#### __Schraffurfüllung()__ ####

Name der Schraffur, mit der die Objekte gefüllt sind.


```python
Database header cell:
=HatchFill returns the hatch fill name for each object in the database

Spreadsheet cell:
=HatchFill(sel=true) returns the hatch fill name of the selected objects in the drawing

```

#### __Verlauffüllung()__ ####

Name des Verlaufs, mit dem die Objekte gefüllt sind.


```python
Database header cell:
=GradientFill returns the gradient fill name for each object in the database

Spreadsheet cell:
=GradientFill(sel=true) returns the gradient fill name of the selected objects in the drawing

```

#### __Objekttextur()__ ####

Name der Textur, das den Objekten zugewiesen ist.


```python
Database header cell:
=ObjectTexture returns the texture name of each object in the database

Spreadsheet cell:
=ObjectTexture(sel=true) returns the texture name of the selected objects in the drawing

```

#### __Skizzenstil()__ ####

Name des Skizzenstils der Objekte.


```python
Database header cell:
=SketchStyle returns the sketch style name for each object in the database

Spreadsheet cell:
=SketchStyle(sel=true) returns the sketch style name of the selected objects in the drawing

```

#### __Linienart()__ ####

Name der Linienart der Objekte.


```python
Database header cell:
=LineType returns the line type name for each object in the database

Spreadsheet cell:
=LineType(sel=true) returns the line type name of the selected objects in the drawing

```

#### __Bildfüllung()__ ####

Name der Bildfüllung der Objekte.


```python
Database header cell:
=ImageFill returns the image fill name for each object in the database

Spreadsheet cell:
=ImageFill(sel=true) returns the image fill name of the selected objects in the drawing

```

#### __GetCOBieSource(Tabellenname.Spaltenname.Land.Version)__ ####

Gibt die Datenquelle einer COBie-Eigenschaft (COBie property) eines Objekts zurück.


```python
=GETCOBIESOURCE ('space.floorname') returns the FloorName data source for objects whose COBie property is Space

```

#### __GetCOBieProperty(Tabellenname.Spaltenname.Land.Version)__ ####

Gibt den Wert einer COBie-Eigenschaft (COBie property) zurück.


```python
=GETCOBIEPROPERTY ('space.floorname') returns the FloorName value for objects whose COBie property is Space

```

#### __Symbolname()__ ####

Name des Symbols.


```python
Database header cell:
=SymbolName returns the name for each symbol instance in the database

Spreadsheet cell:
=SymbolName(sel=true) returns the symbol name of the selected symbol instances in the drawing

```

#### __DatenstempelFeld(Feldname)__ ####

Gibt den Wert des angegebenen Feldes für die Datenstempelobjekte zurück. Feldname ist der Name des Feldes im Datenstempellayout.


```python
Database header cell:
=DataTagField('Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for each data tag in the database.

Spreadsheet cell:
=DataTagField(sel=true, 'Color'), where “Color” is the label of a user-entered text field in a data tag, returns the value for the “Color” field (for example, “Red”) for the selected data tag in the drawing.

```

#### __Grafik_Ansichtsber(Ansichtsbereichsname)__ ####

Erstellt ein Bild der Objekte mit dem Farbschema des angegebenen Ansichtsbereichs.


```python
Database header cell:
=Imagebyviewport('Plan A') applies the data visualizations from the viewport named “Plan A” to each image in the database 

Spreadsheet cell:
=Imagebyviewport('Space Allocation') applies the data visualization from the viewport named “Space Allocation” to the image in the cell

```

#### __Grafik_Datenvis(DatenvisName)__ ####

Erstellt ein Bild des Objekts mit dem Farbschema des angegebenen Ansichtsbereichs.


```python
Database header cell:
=Imagebydatavis('truss by type') applies the “truss by type” data visualization to each image in the database rows

Spreadsheet cell:
=Imagebydatavis('offices') applies the data visualization named “offices” to the image in the cell

```

#### __xRotation()__ ####

Der Rotationswinkel (in Grad) um die x-Achse der Objekte.



#### __yRotation()__ ####

Der Rotationswinkel (in Grad) um die y-Achse der Objekte.



#### __zRotation()__ ####

Der Rotationswinkel (in Grad) um die z-Achse der Objekte, auf die der Filter verweist.



#### __UnterobjektName()__ ####

Gibt den Namen der Unterobjekte zurück. Gibt den Namen des Objekttyps zurück, wenn das Objekt kein Unterobjekt ist.


```python
Database header cell:
=PartTypeName returns the part type name for each subpart object in the database. if the database object is not a subpart, the object type name is returned


```

#### __Füllvordergrundfarbe()__ ####

Die Vordergrundfarbe der Füllung des Objekts, auf die der Filter verweist.


```python
Database header cell:
=FillForeColor returns the name of the fill foreground color for each object in the database

Spreadsheet cell:
=FillForeColor(t=rect) returns the name of the fill foreground color of the rectangle object

```

#### __Füllhintergrundfarbe()__ ####

Die Hintergrundfarbe der Füllung des Objekts.


```python
Database header cell:
=FillBackColor returns the name of the fill background color for each object in the database

Spreadsheet cell:
=FillBackColor(t=rect) returns the name of the fill background color of the rectangle object

```

#### __Stiftvordergrfarbe()__ ####

Die Vordergrundfarbe des Stifts des Objekts.


```python
Database header cell:
=PenForeColor returns the name of the pen foreground color for each object in the database

Spreadsheet cell:
=PenForeColor(t=rect) returns the name of the pen foreground color of the rectangle object

```

#### __Stifthintergrfarbe()__ ####

Die Hintergrundfarbe des Stifts des Objekts.


```python
Database header cell:
=PenBackColor returns the name of the pen background color for each object in the database

Spreadsheet cell:
=PenBackColor(t=rect) returns the name of the pen background color of the rectangle object

```

#### __AnsichtsberStilname()__ ####

Der Name des vom Objekt verwendeten Ansichtsbereichstils


```python
Database header cell:
=ViewportStyleName returns the viewport style name for each viewport object in the database

Spreadsheet cell:
=ViewportStyleName(n='viewport-1') returns the viewport style name for the object named “viewport-1”

```

### Auslaufende Funktionen


#### __Schichtfläche(Index)__ ####

Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.


```python
Database header cell:
=ComponentArea(2) returns the combined area of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentArea(t=wall,1) returns the combined area of the first components for all walls in the drawing

```

#### __Schichtvolumen(Index)__ ####

Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.


```python
Database header cell:
=ComponentVolume(2) returns the combined volume of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentVolume(t=wall,1) returns the combined volume of the first components for all walls in the drawing

```

#### __Schichtname(Index)__ ####

Name einer Schicht.


```python
Database header cell:
=ComponentName(2) returns the name of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentName(t=wall,1) returns the name of the first component for all walls in the drawing

```

#### __IFCEigenschaft(Eigenschaftenset.Eigenschaft)__ ####

Eigenschaft (property field) von IFC-Daten (instance). Beispiel: IFC-Eigenschaft(‘IfcWallStandardCase.Description’).


```python
=GETIFCPROPERTY ('ifcfurnishingelement.name') returns the Name value for IFC objects whose IFC entity is IfcFurnishingElement 

```

#### __SchichtLambda(Index)__ ####

Lambda-Wert der Schicht.


```python
Database header cell:
=ComponentLambda(2) returns the Lambda value of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentLambda(t=wall,1) returns the Lambda value of the first component for all walls in the drawing

```

#### __SchichtU-Wert(Index)__ ####

U-Wert der Schicht.


```python
Database header cell:
=ComponentUValue(2) returns the combined U-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentUValue(t=wall,1) returns the combined U-values of the first components for all walls in the drawing

```

#### __SchichtR-Wert(Index)__ ####

R-Wert der Schicht.


```python
Database header cell:
=ComponentRValue(2) returns the combined R-values of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentRValue(t=wall,1) returns the combined R-values of the first components for all walls in the drawing

```

#### __SchichtDicke(Index)__ ####

Die Dicke der Schicht.


```python
Database header cell:
=ComponentThickness(2) returns the combined thickness of the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentThickness(t=wall,1) returns the combined thickness of the first components for all walls in the drawing

```

#### __Schichtfläche_Klasse(Klasse)__ ####

Fläche der von der Klasse bestimmten Schichten, abzüglich aller Öffnungen. Liegen mehrere Schichten in der Klasse, werden die Flächen addiert.


```python
Database header cell:
=CompAreaByClass('Class-1') returns the combined area of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByClass(t=wall,'Class-1') returns the combined area of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __SchichtLambda_Klasse(Klasse)__ ####

Lambda-Wert vonderKlasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Wert der ersten gefundenen Schicht angezeigt.


```python
Database header cell:
=CompLambdaByClass('Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByClass(t=wall,'Class-1') returns the Lambda value of the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __Schichtname_Klasse(Klasse)__ ####

Der Name von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Name der ersten gefundenen Schicht angezeigt.


```python
Database header cell:
=CompNameByClass('Class-1') returns the name of the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByClass(t=wall,'Class-1') returns the name of the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __SchichtRWert_Klasse(Klasse)__ ####

Der R-Wert einer von der Klasse bestimmten Schicht. Liegen mehrere Schichten in der Klasse, werden die R-Werte der Schichten addiert.


```python
Database header cell:
=CompRValueByClass('Class-1') returns the combined R-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByClass(t=wall,'Class-1') returns the combined R-values of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __Schichtdicke_Klasse(Klasse)__ ####

Dicke der von der Klasse bestimmen Schicht. Liegen mehrere Schichten in der Klasse, werden die Dicken addiert.


```python
Database header cell:
=CompThicknessByClass('Class-1') returns the combined thickness of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByClass(t=wall,'Class-1') returns the combined thickness of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __SchichtUWert_Klasse(Klasse)__ ####

Der U-Wert der von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, werden die U-Werte der Schichten addiert.


```python
Database header cell:
=CompUValueByClass('Class-1') returns the combined U-values of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByClass(t=wall,'Class-1') returns the combined U-values of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __Schichtvol_Klasse(Klasse)__ ####

Volumen der Schichten, die in der angegebenen Klasse liegen. Liegen mehrere Schichten in der Klasse, werden die Volumen addiert.


```python
Database header cell:
=CompVolumeByClass('Class-1') returns the combined volume of the components assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByClass(t=wall,'Class-1') returns the combined volume of the components assigned to the class “Class-1” for all walls in the drawing

```

#### __Schichtfläche_Name(Name)__ ####

Fläche der vom Namen bestimmen Schicht, abzüglich aller Öffnungen. Haben mehrere Schichten den gleichen Namen, werden die Flächen addiert.


```python
Database header cell:
=CompAreaByName('Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByName(t=wall,'Brick Veneer') returns the combined area of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __SchichtLambda_Name(Name)__ ####

Lambda-Wert einer Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, wird der Wert der ersten Schicht angezeigt, die gefunden wird.


```python
Database header cell:
=CompLambdaByName('Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByName(t=wall,'Brick Veneer') returns the Lambda value of the first component with the name “Brick Veneer” for all walls in the drawing

```

#### __Schichtklasse_Name(Name)__ ####

Die Klasse der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, wird die Klasse der ersten gefundenen Schicht angezeigt.


```python
Database header cell:
=CompClassByName('Brick Veneer') returns the class of the first component with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByName(t=wall,'Brick Veneer') returns the class of the first component with the name “Brick Veneer” for all walls in the drawing

```

#### __SchichtRWert_Name(Name)__ ####

Der R-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die R-Werte der Schichten addiert.


```python
Database header cell:
=CompRValueByName('Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByName(t=wall,'Brick Veneer') returns the combined R-values of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __Schichtdicke_Name(Name)__ ####

Dicke der Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, werden die Dicken addiert.


```python
Database header cell:
=CompThicknessByName('Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByName(t=wall,'Brick Veneer') returns the combined thickness of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __SchichtUWert_Name(Name)__ ####

Der U-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die U-Werte der Schichten addiert.


```python
Database header cell:
=CompUValueByName('Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByName(t=wall,'Brick Veneer') returns the combined U-values of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __Schichtvolumen_Name(Name)__ ####

Volumen der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die Volumen addiert.


```python
Database header cell:
=CompVolumeByName('Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByName(t=wall,'Brick Veneer') returns the combined volume of the components with the name “Brick Veneer” for all walls in the drawing

```

#### __Schichtmat_Klasse(Klasse)__ ####

Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten dieselbe Klasse verwenden, werden die Werte addiert.


```python
Database header cell:
=CompMatByClass('Class-1') returns the materials used by the first component assigned to the class “Class-1” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByClass(t=wall,'Class-1') returns the material used by the first component assigned to the class “Class-1” for all walls in the drawing

```

#### __Schichtmaterial_Name(Name)__ ####

Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten denselben Namen verwenden, werden die Werte addiert.


```python
Database header cell:
=CompMatByName('Siding') returns the materials used by the first component with the name “Siding” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompMatByName(t=wall,'Siding') returns the material used by the first component with the name “Siding” for all walls in the drawing

```

#### __Schichtfläche_Mat(Material)__ ####

Die Fläche einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Database header cell:
=CompAreaByMat('Mortar MT') returns the combined area of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompAreaByMat(t=wall, 'Mortar MT') returns the combined area of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __Schichtklasse_Mat(Material)__ ####

Die Klasse der Wand-, Boden/Decke- oder Dachschichen. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird die Klasse der ersten Schicht zurückgegeben.


```python
Database header cell:
=CompClassByMat('Mortar MT') returns the class of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompClassByMat(t=wall, 'Mortar MT') returns the class of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __Schichtlamdba_Mat(Material)__ ####

Der Lambdawert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Lambdawert der ersten Schicht zurückgegeben.


```python
Database header cell:
=CompLambdaByMat('Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompLambdaByMat(t=wall,'Mortar MT') returns the Lambda value of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __Schichtname_Material(Material)__ ####

Der Name der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Name der ersten Schicht zurückgegeben.


```python
Database header cell:
=CompNameByMat('Mortar MT') returns the name of the first component that uses the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompNameByMat(t=wall,'Mortar MT') returns the name of the first component that uses the material “Mortar MT” for all walls in the drawing

```

#### __SchichtRWert_Mat(Material)__ ####

Der R-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Database header cell:
=CompRValueByMat('Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompRValueByMat(t=wall,'Mortar MT') returns the combined R-values of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __Schichtdicke_Mat(Material)__ ####

Die Dicke der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Database header cell:
=CompThicknessByMat('Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompThicknessByMat(t=wall,'Mortar MT') returns the combined thickness of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __SchichtUWert_Mat(Material)__ ####

Der U-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Database header cell:
=CompUValueByMat('Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompUValueByMat(t=wall,'Mortar MT') returns the combined U-values of the components that use the material “Mortar MT” for all walls in the drawing

```

#### __Schichtvolumen_Mat(Material)__ ####

Das Volumen einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Database header cell:
=CompVolumeByMat('Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=CompVolumeByMat(t=wall,'Mortar MT') returns the combined volume of the components that use the material “Mortar MT” for all walls in the drawing

```

### Material


#### __MaterialName()__ ####

Material der Objekte.


```python
Database header cell:
=MaterialName returns the names of materials in objects for each row in the database

Spreadsheet cell:
=MaterialName(t=SOLIDCSG) returns the names of materials in generic solids in the drawing

```

#### __MaterialZählen()__ ####

Anzahl an Materialien der Objekte.


```python
Database header cell:
=MaterialCount returns the total number of materials in objects for each row in the database

Spreadsheet cell:
=MaterialCount(t=SOLIDCSG) returns the total number of materials in generic solids in the drawing

```

#### __MaterialTextur()__ ####

Gibt den Namen der Texturzuweisung des Materials für Objekte zurück.


```python
Database header cell:
=MaterialTexture returns the texture of the material assigned to objects for each row in the database

Spreadsheet cell:
=MaterialTexture(t=SOLIDCSG) returns the texture of the material assigned to the generic solid in the drawing

```

#### __MaterialDatenfeld_Name(Materialname; IFC-Datenfeld)__ ####

Gibt das angegebene IFC-Datenfeld für das angegebene Material zurück.


```python
Spreadsheet cell:
=MatPropertyByName('Mortar MT','MaterialFinish') returns the material finish property for the material “Mortar MT”

```

#### __MaterialIstEinfach()__ ####

Gibt den booleschen Wert Wahr zurück, wenn das Material der Objekte ein einfaches Material ist.


```python
Database header cell:
=MaterialIsSimple returns TRUE if the material of the object referenced by the database row is a simple material.

Spreadsheet cell:
=MaterialIsSimple(t=SOLIDCSG) returns TRUE if the material of the generic solid in the drawing is a simple material.

```

#### __MaterialBauteilname(Materialname)__ ####

Der Name des Bauteils, dem das Material zugewiesen ist.


```python
Database header cell:
=MaterialPartName('Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for each row in the database

Spreadsheet cell:
=MaterialPartName(t=wall, 'Metal Steel MT') returns the name of the first part that uses the material “Metal Steel MT” for walls in the drawing

```

#### __MaterialOberfläche() __ ####

Die Oberfläche der Objekte mit dem angegebenen Material.


```python
Database header cell:
=MaterialSurfaceArea('Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialSurfaceArea(t=wall,'Mortar MT') returns the surface area for objects that use the material named “Mortar MT” for all walls in the drawing

```

#### __MaterialVolumenn()__ ####

Das Volumen der Objekte mit dem angegebenen Material.


```python
Database header cell:
=MaterialVolume('Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all objects for each row in the database

Spreadsheet cell:
=MaterialVolume(t=wall,'Mortar MT') returns the volume for objects that use the material named “Mortar MT” for all walls in the drawing

```

#### __MaterialProzent(Materialname)__ ####

Der prozentuale Anteil des Material, das Objekten zugewiesen ist.


```python
Database header cell:
=MaterialPercent('Mortar MT') returns the percentage of the material “Mortar MT” in all objects for each row in the database

Spreadsheet cell:
=MaterialPercent(t=wall,'Mortar MT') returns the percentage of the material “Mortar MT” for all walls in the drawing

```

#### __Schichtmaterial(Index)__ ####

Das Material der Schichten, auf die der Filter verweist.


```python
Database header cell:
=ComponentMaterial(2) returns the material used by the second component for each wall, round wall, roof, roof face, and slab object in the database

Spreadsheet cell:
=ComponentMaterial(t=wall,1) returns the material used by the first component for all walls in the drawing

```

#### __MaterialDatenfeld(IFC-Datenfeld)__ ####

Gibt das angegebene IFC-Datenfeld für das  Material zurück.


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

## Tabellensuche


#### __VTabellensuche(Zelle; [opt_Param]; Erg_Spaltenindex; nicht_gefunden; Zellenbereich)__ ####

Sucht den Inhalt aus der Zelle in der ersten Spalte des Zellenbereich. Als Ergebnis wird der Wert aus der Spalte des Zellenbereichs genommen, der in Erg_Spaltenindex angegeben ist. Verwendet ECMAScript syntax für die Textverarbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


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

#### __XTabellensuche(Zelle; [opt_Param]; nicht_gefunden; Zellenbereich_Such; Zellenbereich_Erg)__ ####

Sucht den Inhalt der Zelle im Zellenbereich_Such und gibt den Inhalt der gefundenen Zelle aus Zellenbereich_Erg zurück. Die Zellenbereiche dürfen nur eine Spalte haben. Verwendet ECMAScript syntax für die Textverarbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


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

## Text


#### __Verketten(Text1; Text2;...)__ ####

Verknüpft einzelne Texte zu einem gesamten Text.


```python
=concat(B3,', ',B4) returns the contents of cells B3 and B4 as a single string, separated by a comma and a space

```

#### __Teilstring(Text; Trennzeichen; Index)__ ####

Zerlegt einen Text an den Trennzeichen in einzelne Teiltexte. Der Index bestimmt den Teiltext.


```python
=SUBSTRING('kitchen;bedroom;bathroom;basement', ';', 2) returns “bedroom,” which is the second substring in the specified string

```

#### __txt(Wert; ZuEinheit; [Param1]; [Param2]; ...)__ ####

Verwandelt einen numerischen Wert von Dokumenteinheiten in die angegebene Einheit und gibt eine String-Darstellung zurück, wobei die Optionen zur Formatierung verwendet werden. Weitere Informationen finden Sie im Beispiel.


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

#### __IstAlphanum(Text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge alphanumerisch sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.


```python
=isalnum('word123') returns True

```

#### __IstText(Text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge Buchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.


```python
=isalpha('word') returns True

```

#### __IstZahl(Text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge Zahlen sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.


```python
=isdigit('1234') returns True

```

#### __IstKleinbuchstaben(text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge Kleinbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben Wahr zurück.


```python
=islower('does not have upper char') returns True

```

#### __IstLeerzeichen(Text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge Leerzeichen sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch.


```python
=isspace('      ') returns True

```

#### __IstWörterGroß(Text)__ ####

Wahr, wenn jedes Wort mit einem Großbuchstaben beginnt andernfalls Falsch.


```python
=isTitle('This Is Title Text') returns True

```

#### __IstGroßbuchstaben(Text)__ ####

Wahr, wenn alle Zeichen in der Zeichenfolge Großbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls Falsch. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben Wahr zurück.


```python
=isUpper('DOES NOT HAVE LOWER CHARS') returns True

```

#### __TextVerketten(Trennzeichen; Text1; Text2; …)__ ####

Verknüpft einzelne Text zu einem Text, wobei das angegebene Trennzeichen zwischen die einzelnen Texte gesetzt wird.


```python
=textJoin(', ', 1, 2, 3) returns '1, 2, 3'

```

#### __Kleinbuchstaben(Text)__ ####

Alle Buchstaben des Textes werden in Kleinbuchstaben verwandelt.


```python
=lower('MAKE THIS LOWER') returns 'make this lower'

```

#### __WegschneidenLinks(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von links aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.


```python
=trimLeft('abbcwordabbc', 'abc') returns 'wordabbc'

```

#### __Ersetzen(Text; altText; neuText; [Anzahl])__ ####

Alle Vorkommen des Teiltextes altText werden durch neuText ersetzt. Wenn der optionale Parameter verwendet wird, werden nur so viele Vorkommen ersetzt, wie angegeben.


```python
=replace('my car is your car', 'car', 'ball', 2) returns 'my car is your ball'

```

#### __WegschneidenRechts(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von rechts aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.


```python
=trimRight('abbcwordabbc', 'abc') returns 'abbcword'

```

#### __Wegschneiden(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von beiden Seiten aus der Zeichenkette. Werden sie weggelassen oder bleiben leer, werden statt dessen Leerzeichen entfernt.


```python
=trim('abbcwordabbc', 'abc') returns 'word'

```

#### __Großschreiben(Text)__ ####

Jedes Wort wird mit einem großen Anfangsbuchstaben geschrieben.


```python
=proper('make this title text') returns 'Make This Title Text'

```

#### __Großbuchstaben(Text)__ ####

Alle Buchstaben des Textes werden in Großbuchstaben verwandelt.


```python
=upper('make this upper') returns 'MAKE THIS UPPER'

```

#### __Länge(Text)__ ####

Die Länge des Textes.


```python
=len('hello there') returns 11

```

#### __Einfügen(Text; Index; Einfügetext)__ ####

Fügt den Einfügetext an der mit Index bezeichneten Stelle in den Text ein.


```python
=insert('hey, this is ok', 12, ' not') returns 'hey, this is not ok'

```

#### __Links(Text; Index)__ ####

Die linke Seite des Textes bis zur Position Index.


```python
=left('this is sample', 4) returns 'this'

```

#### __Rechts(Text; Anzahl)__ ####

Die Zeichen von der rechten Seite des Textes.


```python
=right('this is sample', 6) returns 'sample'

```

#### __Mitte(Text; Index; Anzahl)__ ####

Gibt einen Teiltext zurück, der bei Index beginnt und die Länge hat, die in Anzahl angeben ist. Ist Index negativ, wird die Startposition des Teilstrings vom Ende des Textes rückwärts bestimmt.


```python
=mid('apple', 2, 3) returns 'ppl'
=mid('apple', -4, 3) looking the index backwards, returns 'ppl'
=mid('apple', 4, -3) getting characters backward from the index, returns 'ppl
```

#### __Löschen(Text; Index; Anzahl)__ ####

Teilstring, der an der Position Index beginnt und die Länge Anzahl hat.


```python
=delete('this is sample', 4, 3) returns 'this sample'. Here 3 characters after the 4th are deleted.

```

#### __Anführungszeichen(Text)__ ####

Setzt einen Text in Anführungszeichen.


```python
=quote('quote this') returns "quote this" (The text, in double quotes)

```

#### __Wdh(Text; Anzahl)__ ####

Wiederholt den Text so oft, wie angegeben.


```python
=rept('Line ', 3) returns 'Line Line Line '

```

#### __FesteDezimalstellen(Zahl; [Dezimalstellen])__ ####

Formatiert eine Zahl als Text mit einer festen Anzahl von Nachkommastellen.


```python
=fixed(10.12345, 3) returns 10.123 (up to the 3rd digit after the decimal point)

```

#### __NullenVoranstellen(Zahl; Dezimalstellen)__ ####

Die numerische Zeichenfolge werden Nullen bis zum Erreichen der Anzahl der Dezimalstellen vorangestellt. Wenn ein kleinerer Wert für die Dezimalstellen angegeben wird als die Zeichenfolge besitzt, bleibt die Zeichenfolge unverändert.


```python
=justNum(10.123, 8) returns '0010.123'

```

#### __Char(Zahl)__ ####

Das Unicode-Zeichen oder die Textdarstellung (U+1234), auf die die angegebene Zahl verweist.


```python
=char(8734) returns the symbol ∞
=char('U+221E') also returns ∞

```

#### __Code(Text)__ ####

Die Nummer (Unicode-Codepunkt) für das erste Zeichen im Text.


```python
=code('∞') returns 8734. The unicode codepoint for ∞

```

#### __Suchen(Teiltext; Text; [GroßKleinschreibung])__ ####

Die erste Stelle (Index) im Text, an der der Teiltext gefunden wird. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf Wahr gesetzt ist. Das Ergebnis ist -1, wenn der Teiltext nicht gefunden wird.


```python
=find('text', 'this is text') returns 8

```

#### __SuchenSuchbegriff(Suchbegriff; Text; [GroßKleinschreibung])__ ####

Die erste Stelle (Index) im Text, an der der Suchbegriff gefunden wird. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf Wahr gesetzt ist. Der Suchbegriff ist eine Folge von Zeichen, die ein Suchmuster angibt.Das Ergebnis ist -1, wenn der Begriff nicht gefunden wird.Verwendet ECMAScript-Syntax für die Textbearbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript.


```python
=findPattern('(Soft)(.*)', 'soft Software', True) returns 5

```

#### __Wert(text)__ ####

Konvertiert einen Text, der eine Zahl darstellt, in eine Zahl.


```python
=value('2e3') returns the numeric value of 2 times 10 raised to the power of 3

```

