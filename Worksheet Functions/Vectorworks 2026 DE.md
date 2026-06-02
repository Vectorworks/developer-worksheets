Worksheet functions

Based on Vectorworks 2026 Update 5 (Build 862586)



## Contents
- [Allgemein](#Allgemein)
- [Datum/Zeit](#Datum/Zeit)
- [Funktionen für Adapter](#Funktionen-für-Adapter)
- [Funktionen für Anschluss](#Funktionen-für-Anschluss)
- [Funktionen für Arbeitsplatte](#Funktionen-für-Arbeitsplatte)
- [Funktionen für Aussparung](#Funktionen-für-Aussparung)
- [Funktionen für Belag/Weg](#Funktionen-für-Belag/Weg)
- [Funktionen für Boden/Decke](#Funktionen-für-Boden/Decke)
- [Funktionen für Bridle](#Funktionen-für-Bridle)
- [Funktionen für Dach](#Funktionen-für-Dach)
- [Funktionen für Door](#Funktionen-für-Door)
- [Funktionen für Einfassung](#Funktionen-für-Einfassung)
- [Funktionen für Fassadenmodul](#Funktionen-für-Fassadenmodul)
- [Funktionen für Fassadenmodul Rahmenelement](#Funktionen-für-Fassadenmodul-Rahmenelement)
- [Funktionen für Fenster](#Funktionen-für-Fenster)
- [Funktionen für Flächenpflanzung](#Funktionen-für-Flächenpflanzung)
- [Funktionen für Geländemodell](#Funktionen-für-Geländemodell)
- [Funktionen für Geländer](#Funktionen-für-Geländer)
- [Funktionen für Geländer/Zaun Classic](#Funktionen-für-Geländer/Zaun-Classic)
- [Funktionen für Gerät](#Funktionen-für-Gerät)
- [Funktionen für Hecke](#Funktionen-für-Hecke)
- [Funktionen für Kabel](#Funktionen-für-Kabel)
- [Funktionen für Lichtschacht](#Funktionen-für-Lichtschacht)
- [Funktionen für Marionette Object](#Funktionen-für-Marionette-Object)
- [Funktionen für Panel](#Funktionen-für-Panel)
  - [Verbinder](#Verbinder)
- [Funktionen für Pflanze](#Funktionen-für-Pflanze)
- [Funktionen für Pfosten](#Funktionen-für-Pfosten)
  - [Riegel](#Riegel)
    - [Fassade](#Fassade)
- [Funktionen für Profillinie](#Funktionen-für-Profillinie)
- [Funktionen für Querprofile](#Funktionen-für-Querprofile)
- [Funktionen für Rampe](#Funktionen-für-Rampe)
- [Funktionen für Raum](#Funktionen-für-Raum)
- [Funktionen für Schaltkreis](#Funktionen-für-Schaltkreis)
- [Funktionen für Scheinwerfer](#Funktionen-für-Scheinwerfer)
- [Funktionen für Symbollinie Classic](#Funktionen-für-Symbollinie-Classic)
- [Funktionen für Tragwerkselement](#Funktionen-für-Tragwerkselement)
- [Funktionen für Tür](#Funktionen-für-Tür)
- [Funktionen für Wand](#Funktionen-für-Wand)
- [Funktionen für WinDoor 6.0](#Funktionen-für-WinDoor-6.0)
- [Funktionen für Window](#Funktionen-für-Window)
- [Funktionen für XPlanung](#Funktionen-für-XPlanung)
- [Funktionen für Zaun](#Funktionen-für-Zaun)
- [Logik](#Logik)
- [Math. Formeln](#Math.-Formeln)
- [Objekte](#Objekte)
  - [Allgemein](#Allgemein)
  - [Auslaufende Funktionen](#Auslaufende-Funktionen)
  - [Material](#Material)
  - [Phasen](#Phasen)
- [Tabellensuche](#Tabellensuche)
- [Text](#Text)

___

## Allgemein


#### __RUNSCRIPT('ScriptName')__ ####

Führt ein Python-Script mit dem Namen 'ScriptFile.py' im Ordner 'Vectorworks Plaug-Ins' aus und übergibt die Parameter '2' und '1' und gibt den Wert zurück.


```python
Dantenbank Kopfzeile:

=RUNSCRIPT('ScriptName')

Führt ein VectorScript mit dem Namen 'ScriptName' aus und gibt die Werte aller Objekte in der Datenbank zurück.



Tabellenkalkulation:

=RUNSCRIPT(2, 'ScriptFile.py', 2, 1)

Führt ein Python-Script mit dem Namen 'ScriptFile.py' im Ordner 'Vectorworks Plug-Ins' aus und übergibt die Parameter '2' und '1' und gibt den Wert zurück.


```

#### __FELDFORMAT('Datenbank'; 'Feldname')__ ####

Gibt den Basiswert eines bestimmten Datenfeldes der verknüpften Datenbank zurück.


```python
=FELDFORMAT('Window CW', 'UnfinishedWidth')

Wobei 'Window CW' die Datenbank ist und 'UnfinishedWidth' das Datenfeld.




```

#### __RUNSCRIPTEDIT('ScriptName')__ ####

Führt ein Script aus und gibt die erhaltenen Werte zurück. Ähnlich zu RunScript, jedoch lassen sich die Zellen bearbeiten und das selbe Script wird auch wieder ausgeführt, um die Bearbeitung durchzuführen.



#### __DATENBANK(Filter)__ ####

Erzeugt eine Datenbank der Objekte, welche dem gegebenen Kriterium entsprechen.


```python
=DATABASE(L='Erdgeschoss')

Gibt alle Objekte auf der Konstruktionsebene `'Erdgeschoss'` in der Tabelle zurück.

Wobei Parameter L = Layer (Konstruktionsebene)


```

#### __DATENBANKDURCHSCRIPT([ScriptPfad]; 'ScriptName')__ ####

Führt ein Skript aus, um eine Datenbank mit Objekten zu erstellen.


```python
=DATABASEBYSCRIPT('./Desktop/Beispieldatei.py', 'Beispieldatei.py' 2, 1)

führt das Script mit dem Namen 'Beispieldatei.py' aus und übergibt die Werte '2', '1' an das Skript.


```

#### __Dateipfad()__ ####

Gibt den vollen Pfad des aktuellen Dokuments zurück und den Pfad der Projektdatei, wenn das Dokument eine Arbeitsdatei ist.


```python
=Dateipfad

Gibt den vollen Pfadnamen des aktuellen Dokuments zurück. Wenn das aktuelle Dokument eine Arbeitsdatei ist, wird der Pfadname der Projektdatei zurückgegeben.


```

#### __Dateiname()__ ####

Gibt des Namen des aktuellen Dokuments zurück und den Namen der Projektdatei, wenn das Dokument eine Arbeitsdatei ist.


```python
=Dateiname

Gibt den Namen des aktuellen Dokuments zurück. Wenn das aktuelle Dokument eine Arbeitsdatei ist, wird der Name der Projektdatei zurückgegeben.


```

#### __AktiveTabelle()__ ####

Gibt den Namen der aktiven Tabelle zurück.


```python
=ActiveWorksheet returns the name of the active worksheet in which the function is being called.
```

## Datum/Zeit


#### __Heute()__ ####

Gibt das aktuelle Datum zurück. Der Wert für den Tag wird zunächst nur als Zahl zurückgegeben. Die Zelle muss noch als Datum formatiert werden, um die Ergebnis in einem Zeitformat anzuzeigen.


```python
=Heute gibt das aktuelle Datum zurück.

```

#### __Jetzt()__ ####

Gibt die aktuelle Uhrzeit zurück. Der Wert wird zunächst nur als Zahl zurückgegeben. Die Zelle muss noch als Datum formatiert werden, um die Ergebnis in einem Zeitformat anzuzeigen.


```python
=Jetzt

gibt die aktuelle Uhrzeit zurück.


```

#### __Zeit12h()__ ####

Gibt die aktuelle Uhrzeit im 12h-Format zurück (hh-mm am/pm).


```python
=Zeit12h

Gibt die aktuelle Uhrzeit im 12h-Format zurück (hh-mm am/pm).


```

#### __Zeit24h()__ ####

Gibt die aktuelle Uhrzeit im 24h-Format zurück (hh-mm).


```python
=Zeit24h

Gibt die aktuelle Uhrzeit im 24h-Format zurück (hh-mm am/pm).


```

#### __FDatum(Datumsformat)__ ####

Gibt das aktuelle Datum im angegebenen Datumsformat zurück (klicken Sie auf 'Beispiel zeigen' für unterstützte Datumsformate).


```python
FDatum(1)

Gibt das aktuelle Datum im ersten Format der Datumsliste, welches MTJJ ist, zurück, z.B.

1/12/26.



Datumsformate:
1	M/T/JJ
2	M/T/JJ hmm
3	T/M/JJ
4	T/M/JJ hm
5	JJ/M/T
6	JJ/M/T hm
7	T-MMM-J
8	T-MMM
9	MMM-JJ
10	h mm
11	h mm ss
12	h mm (AM/PM)
13	h mm ss (AM/PM)
14	M/T/JJ hms (AM/PM)
15	Tag, Monat T, JJJJ
16	Tag, Monat T, JJJJ hms (AM/PM)
17	Wochentag, MMMM T, JJJJ
18	Wochentag, MMMM T, JJJJ hms (AM/PM)
19	Tag, T Monat JJJJ
20	Tag, T Monat JJJJ hms (AM/PM)
21	Wochentag, T MMM JJJJ
22	Wochentag, T MMM JJJJ hms (AM/PM)
23	T/M/JJ hms (AM/PM)
24	Tag, JJJJ Monat T
25	Tag, JJJJ Monat T hms (AM/PM)
26	Wochentag, JJJJ MMM T
27	Wochentag, JJJJ MMM T hms (AM/PM)
28	JJ/M/T hms (AM/PM)
29	JJJJMMTT
30	MM/TT/JJJJ
31	JJJJ-MM-TT
32	JJJJMMTThhmmss
33	TT/MM/JJ
34	TT/MM/JJ hms (AM/PM)
35	TT/MM/JJJJ
36	TT/MM/JJJJ hms (AM/PM)
37	JJMMTT


```

#### __DatumKurzMTJ()__ ####

Gibt das aktuelle Datum im Datumsformat MTJ zurück.


```python
=DatumKurzMTJ

Gibt das aktuelle Datum in einem Datumsformat MTJ zurück, wie z.B.

11/126/25


```

#### __DatumKurzTMJ()__ ####

Gibt das aktuelle Datum im Datumsformat TMJ zurück.


```python
=DatumKurzTMJ

Gibt das aktuelle Datum in einem Datumsformat TMJ zurück, wie z.B.

26/11/25


```

#### __DatumMittel()__ ####

Gibt das aktuelle Datum als mittellanges Datumsformat zurück.


```python
=DatumMittel

Gibt das aktuelle Datum in einem mittellangen Datumsformat zurück, wie z.B.

Nov 26, 2025


```

#### __DatumLang()__ ####

Gibt das aktuelle Datum als langes Datumsformat zurück.


```python
=DatumLang

Gibt das aktuelle Datum in einem langen Datumsformat zurück, wie z.B.

Mittwoch, November 26, 2025


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



## Funktionen für Aussparung


#### __Grundfläche()__ ####

Ermittelt die Grundfläche der Aussparung.



#### __Grundfläche('gross')__ ####

Ermittelt die Grundfläche der Aussparung.



#### __Grundfläche('net')__ ####

Ermittelt die Grundfläche der Aussparung abzüglich der Auskleidung.



#### __Objektdaten('basicobject'; [Parameter 2]; [Parameter 3]; [Parameter 4])__ ####

Gibt Werte der Wand oder Boden/Decke, in der die Aussparung eingefügt ist, zurück.

Parameter 1:
'Basisobjekt'

Parameter 2:
'Datenbankwert', 'isteingefügt', 'Bezeichnung', 'Beschreibung', 'Funktion', 'Aussenseite', 'Tragend', 'Feuerwiderstand', 'Brennbare Konstruktion', 'Brandmauer', 'Schalldämmung', 'Typ', 'Hersteller', 'Stilname'

Parameter 3 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
'Name der verwendeten Datenbank'

Parameter 4 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
'Name des Datenbankfeldes einer Datenbank'



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

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -l


```python
=Anzahl('Öffnungen')

Gibt die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deck-Schicht zurück.

=Anzahl('Öffnungen', 'Min Öffnungsvolumen=10 cm3') gibt die Anzahl der Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern zurück.

=Anzahl('Öffnungen', 'Min Öffnungsfläche oben=0,5qm2', 'Max Öffnungsfläche oben=1 m2') gibt die Anzahl der Öffnungen zwischen 0,5 und einem Quadratmeter oben in Boden/Decke oder Boden/Decke-Schicht.

=Anzahl('Öffnungen', 'Min Öffnungsfläche unten=0,25m2'. 'Max Öffnungsvolumen=1m3') gibt die Anzahl der Öffnungen mit einer Fläche von mindestens 0,25 Quadratmeter unten in Boden/Decke oder Boden/Decke-Schicht und einem Volumen von höchstens einem Kubikmeter

=Anzahl('Öffnungen', 'Öffnungstyp=Fenster') gibt die Anzahl der Öffnungen durch Fenster zurück.

=Anzahl('Öffnungen', 'Schicht=Dämmung', 'Min Öffnungsvolumen=10cm3') gibt die Öffnungen mit einem Volumen von mindestens 10 Kubikzentimeter in der Schicht Dämmung zurück.

Der Unterschied zwischen Anzahl('Einfügungen') und Anzahl('Öffnungen') ist, dass in (seltenen) Fällen, in denen zwei eingefügte Objekte dieselbe Öffnung haben, Anzahl('Einfügungen') sie als getrennte Objekte, während Anzahl('Öffnungen') sie als eine einzige Öffnung behandelt.


```

#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __DickeDachflStützeBoden()__ ####

Dicke von Dachflächen, Profilstützen und Böden.


```python
Objektliste:

=DICKEDACHFLSTÜBODE

Gibt Gesamtdicke von Böden wie auch Dachflächen und Profilstützen zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DICKEDACHFLSTÜBODE((PON='SLAB') & (SEL=WAHR))

Gibt Gesamtdicke des Boden/Decke-Stils zurück, wenn das aktive Objekt ein/e Boden/Decke ist.

PON = Unterobjekt PlugIn

SEL = Aktive Selektion (selection status)
```

#### __BodenDeckenstilName()__ ####

Name eines Boden/Deckenstils.


```python
Objektliste:

=BODENDECKENSTIL

Gibt Namen des Boden/Deckenstils zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=BODENDECKENSTIL((PON='SLAB') & (SEL=WAHR))

Gibt Namen des Boden/Deckenstils zurück, wenn das aktive Objekt ein/e Boden/Decke ist.

PON = Unterobjekt PlugIn

SEL = Aktive Selektion (selection status)
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
=Oberfläche('Unten Brutto') gibt die Bruttofläche der   Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.



Oberfläche('Unten Brutto', 'Schicht=Dämmung') gibt die Bruttofläche der Unterseite der Boden/Decken-Schicht namens 'Dämmung'.


```

#### __Oberfläche('Unten Netto'; [optionale Parameter])__ ####

Fläche der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=Oberfläche('Unten Netto') gibt die Nettofläche der Unterseite eines Boden/Decke-Objekts oder einer Boden/Decke-Schicht zurück, wobei alle Öffnungen berücksichtigt werden.



Oberfläche('Unten Netto', 'Min Öffnungsfläche=0,5 m2') gibt die Nettofläche der Unterseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei alle Öffnungen unter 0,5 m2 ignoriert werden.



Oberfläche('Unten Netto', 'Min Öffnungsfläche=0,5 m2', 'Max Öffnungsfläche=1 m2') gibt die Nettofläche der Unterseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei alle Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



Oberfläche('Unten Netto', 'Schicht=Dämmung') gibt die Nettofläche der Unterseite der Schicht 'Dämmung' zurück.
```

#### __Oberfläche('Öffnungen unten'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der Unterseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen von Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=Oberfläche('Öffnungen unten') gibt die Gesamtfläche der Öffnungen der Unterseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück.



=Oberfläche('Öffnungen unten', 'Min Öffnungsfläche=0.5 m2') gibt Gesamtfläche der Öffnungen der Unterseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



=Oberfläche('Öffnungen unten', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt Gesamtfläche der Öffnungen der Unterseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.

=Oberfläche('Öffnungen unten', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen der Unterseite der Boden/Decke-Schicht 'Dämmung' zurück.
```

#### __Oberfläche('Öffnungen oben'; [optionale Parameter])__ ####

Die Fläche der Öffnungen auf der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Öffnungen in Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=Oberfläche('Öffnungen oben') gibt die Gesamtfläche der Öffnungen der Oberseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück.



=Oberfläche('Öffnungen oben', 'Min Öffnungsfläche=0.5 m2') gibt Gesamtfläche der Öffnungen der Oberseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



=Oberfläche('Öffnungen oben', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt Gesamtfläche der Öffnungen der Oberseite eines Boden/Decke-Objekts oder Boden/Decke-Schicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.

=Oberfläche('Öffnungen oben', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen der Obseite der Boden/Decke-Schicht 'Dämmung' zurück.
```

#### __Oberfläche('Oben Brutto'; [optionale Parameter])__ ####

Gibt die Fläche der Obererseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=Oberfläche('Oben Brutto') gibt die Bruttofläche der Oberseite der Wand oder Wandschicht zurück.

=Oberfläche('Oben Brutto', 'Schicht=Dämmung') gibt die Bruttofläche der Oberseite der Wandschicht 'Dämmung' zurück.
```

#### __Oberfläche('Oben Netto'; [optionale Parameter])__ ####

Die Fläche der Oberseite eines Boden/Decken-Objekts oder einer Boden/Decken-Schicht.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Min Öffnungsfläche=...' / 'Max Öffnungsfläche=...': Es werden nur Öffnungen berücksichtig, die zwischen der minimalen und maximalen Öffnungsfläche liegen. Wenn für die Werte keine Einheiten angegeben sind, werden Quadratmillimeter genommen.


```python
=Oberfläche('Oben Netto') gibt die Fläche der Oberseite der Wand oder Wandschicht zurück, wobei alle Öffnungen berücksichtigt werden.



=Oberfläche('Oben Netto', 'Min Öffnungsfläche=0.5 m2') gibt die Fläche der Oberseite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden



=Oberfläche('Oben Netto', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Fläche der Oberseite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Oben Netto', 'Schicht=Dämmung') gibt die Fläche der Oberseite der Wandschicht 'Dämmung' zurück.
```

#### __Volumenn()__ ####

Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Volumenn('Brutto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=Volumen('Brutto')

Gibt das Bruttovolumen der Wand, Wandschicht, Boden/Decke und Boden/Decke-Schicht zurück.

=Volumen('Brutto', 'Schicht=Dämmung') gibt das Bruttovolumen der Wandschicht namens Dämmung zurück.


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
=Volumen('Netto')

Gibt das Volumen der Wand, Wandfläche, Boden/Decke und Boden/Decke-Schicht zurück.

=Volumen('Netto', 'Min Öffnungsvolumen=10 cm2') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern berücksichtigt werden.

=Volumen('Netto', 'Min Öffnungvolumen=10 cm2', 'Max Öffnungsvolumen=1 m3')  gibt das Volumen der Wand , Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nür Öffnungen mit einem Volumen zwischen 10 Kubikzentimetern und 1 Kubikmeter berücksichtigt werden.

=Volumen('Netto', 'Öffnungstyp=Fenster') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen durch Fenster berücksichtigt werden.

=Volumen('Netto', 'Öffnungstyp=Fenster; Tür') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen durch Fenster und Türen berücksichtigt werden

=Volumen('Netto', 'Schicht=Dämmung', 'Min Öffnungsvolumen=10 cm3') gibt das Volumen der Wandschicht Dämmung zuück, wobei nur Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern berücksichtigt werden.


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
=Volumen('Öffnungen')

Gibt das Gesamtvolumen der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Decke-Schicht zurück.

=Volumen('Öffnungen', 'Min Öffnungsvolumen=10 cm3') gibt das Gesamtvolumen von Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern zurück.

=Volumen('Öffnungen', 'Min Öffnungsvolumen=10 cm3', 'Max Öffnungsvolumen=1 m3') gibt das Gesamtvolumen von Öffnungen mit einem Volumen zwischen 10 Kubikzentimetern und 1 Kubikmeter zurück.

=Volumen('Öffnungen', 'Öffnungstyp=Fenster') gibt das Gesamtvolumen der Öffnungen durch Fenster zurück.

=Volumen('Öffnungen', 'Schichtname=Dämmung', 'Min Öffnungsvolumen=10cm3') gibt das Gesamtvolumen von Öffnungen mit mindestens 10 Kubikzentimetern in der Wandschicht namens Dämmung.


```

## Funktionen für Bridle


#### __Objektdaten('Bridle Leg'; '<Datenauswahl>'; '[<Bauteilauswahl>]'; [<Leg Index>]__ ####

Daten Bridle Leg. Datenauswahl - 'Name', 'Bestellte Bauteile', 'Summe Bauteile'. Bauteilauswahl - 'Leg', 'Basket/Pickup', oder leer, um alle Bauteile anzuzeigen. Der Leg Index muss nicht angegeben weren,  wenn die Funktion auf nur ein Leg angewendet wird. Wird sie auf ein ganzes Bridle angewendet, muss ein Leg Index angegeben werden. Die Bauteilauswahl kann ignoriert werden, wenn Sie alle Bauteil anzeigen und einen Leg Index angeben möchten, z.B. '(Bridle Leg', 'Bestellte Bauteile', 2)'



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





#### __Objektdaten('Dachneigung')__ ####

Gibt die Dachneigung des Dachs oder Dachfläche zurück, auf die der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(((L='Obergeschoss') & (T=DACH)), 'Dachneigung') gibt die Neigung des Dachs auf der Ebene 'Obergeschoss zurück.



Objektliste:

=Objektdaten('Dachneigung') gibt die Neigung des Dachs oder der Dachfläche zurück.


```

#### __Objektdaten('R-Wert')__ ####

Der R-Wert des Objekts.



#### __Objektdaten('U-Wert')__ ####

Der U-Wert des Objekts.



#### __DachflKompl()__ ####

Gesamtfläche von Dächern.


```python
Objektliste:

=DACHFLKOMPL

Gibt die orthogonal (senkrecht zur Fläche) gemessene Dachfläche des Daches zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DACHFLKOMPL((ST=DACHFLÄCHE) & (SEL=WAHR))

Gibt die orthogonal (senkrecht zur Fläche) gemessene Dachfläche des Daches zurück, wenn das aktive Objekt eine Dachfläche ist. Beim Dach ist der Filter T=Dach zu verwenden.

T = Objekttyp

ST = Unterobjekt

SEL = Aktive Selektion (selection status)
```

#### __DachflOhneÜberst()__ ####

Fläche von Dächern ohne die Fläche des Überstands.


```python
Objektliste:

=DACHFLOHNEÜBERST

Gibt die orthogonal (senkrecht zur Fläche) gemessene Dachfläche des Daches zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DACHFLOHNEÜBERST((ST=DACHFLÄCHE) & (SEL=WAHR))

Gibt die orthogonal (senkrecht zur Fläche) gemessene Dachfläche des Daches zurück, wenn das aktive Objekt eine Dachfläche ist. Beim Dach ist der Filter T=Dach zu verwenden.

T = Objekttyp

ST = Unterobjekt

SEL = Aktive Selektion (selection status)
```

#### __DachflKomplProj()__ ####

Gesamtfläche von Dächern auf die aktive Konstruktionsebene projiziert.


```python
Objektliste:

=DACHFLKOMPLPROJ

Gibt die von Oben (2D-Plan Draufsicht) gemessene Dachfläche des Daches zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DACHFLKOMPLPROJ((ST=DACHFLÄCHE) & (SEL=WAHR))

Gibt die von Oben (2D-Plan Draufsicht) gemessene Dachfläche des Daches zurück, wenn das aktive Objekt eine Dachfläche ist. Beim Dach ist der Filter T=Dach zu verwenden.

T = Objekttyp

ST = Unterobjekt

SEL = Aktive Selektion (selection status)
```

#### __DachflOhneÜberstProj()__ ####

Fläche von Dächern ohne die Fläche des Überstands auf die aktive Konstruktionsebene projiziert.


```python
Objektliste:

=DACHFLOHNEÜBERSTPROJ

Gibt die von Oben (2D-Plan Draufsicht) gemessene Dachfläche des Daches zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DACHFLOHNEÜBERSTPROJ((ST=DACHFLÄCHE) & (SEL=WAHR))

Gibt die von Oben (2D-Plan Draufsicht) gemessene Dachfläche des Daches zurück, wenn das aktive Objekt eine Dachfläche ist. Beim Dach ist der Filter T=Dach zu verwenden.

T = Objekttyp

ST = Unterobjekt

SEL = Aktive Selektion (selection status)
```

#### __Dachstilname()__ ####

Name des Dachstils.


```python
Objektliste:

=DACHSTIL

Gibt Namen des Dachstils zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DACHSTIL((ST=DACHFLÄCHE) & (SEL=WAHR))

Gibt Namen des Dachstils zurück, wenn das aktive Objekt eine Dachfläche ist. Beim Dach ist der Filter T=Dach zu verwenden.

T = Objekttyp

ST = Unterobjekt

SEL = Aktive Selektion (selection status)
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



## Funktionen für Fassadenmodul


#### __Tiefe(Filter)__ ####





#### __Breite(Filter)__ ####





#### __Höhe(Filter)__ ####





#### __Fläche(Filter)__ ####





#### __Fläche(Filter)__ ####

Returns the total glazing area for all objects in the Assembly.



## Funktionen für Fassadenmodul Rahmenelement


#### __Tiefe(Filter)__ ####





#### __Breite(Filter)__ ####





#### __Länge(Filter)__ ####





## Funktionen für Fenster


#### __Tiefe('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Tiefe der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!!



#### __Tiefe('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen.



#### __Tiefe('Sill')__ ####

Gibt die Tiefe der äußeren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmenaußenkante.



#### __Tiefe('Stool')__ ####

Gibt die Tiefe der inneren Fensterbank (gemessen senkrecht zur Wand) zurück, sofern eine solche existiert. Gemessen wird ab der Rahmeninnenkante.



#### __Objektdaten('basicobject'[; Parameter 2][; Parameter 3][; Parameter 4])__ ####

Gibt Werte der Wand, in der das Fenster eingefügt ist, zurück.

Parameter 1:
'basicobject'

Parameter 2:
'recordvalue', 'isinserted', 'mark', 'description', 'function', 'exterior', 'load bearing', 'fire rating', 'combustible construction', 'compartmentation', 'acoustic rating', 'model', 'manufacturer', 'stylename'

Parameter 3 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
<Name der verwendeten Datenbank>

Parameter 4 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
<Name des Datenbankfeldes einer Datenbank>


```python
=Objektdaten('basicobject'; 'description')
=Objektdaten('Basisobjekt'; 'IstEingefügt')
=Objektdaten('basicobject'; 'recordvalue'; 'MeineDatenbank'; 'MeinDatenbankfeld')

Gibt Werte der Wand, in der das Fenster eingefügt ist, zurück.

Für die meisten Parameter stehen deutsche und englische Bezeichnungen zur Verfügung.
Es wird empfohlen, die englischen Bezeichnungen zu verwenden.
Eine Übersetzungstabelle finden Sie weiter unten.

Diese Objektdatenfunktion kann mit zwei bis vier Parametern aufgerufen werden:


Parameter 1:


'basicobject'

Dieser Parameter bewirkt, dass die Werte des übergeordneten Objekts (in diesem Fall der Wand) und nicht des Fensters selbst zurückgegeben werden.



Parameter 2:


'mark'              
'description'
'function'   
'exterior'     
'load bearing' 
'fire rating'   
'combustible construction'
'compartmentation'        
'acoustic rating'    
'model'              
'manufacturer'   
'stylename' 

Einer dieser Parameter bewirkt, dass der entsprechende Wert der Wand bzw. der IFC-Daten der Wand zurückgegeben wird.

'isinserted' 

Gibt zurück, ob das Fenster in eine Wand eingefügt ist.

'recordvalue'   

Dieser Parameter bewirkt, dass der Inhalt des mit den beiden folgenden Parametern definierten Datenbankfeldes der Wand (also des Basisobjekts) zurückgegeben wird.



Parameter 3:

<Name einer Datenbank, mit der die Wand verknüpft ist>

Dieser Parameter wird nur berücksichtigt, wenn Parameter 2 = 'recordvalue'.



Parameter 4:

<Name eines Datenbankfeldes der in Parameter 3 spezifizierten Datenbank>




Ist Parameter2 = 'recordvalue' und Parameter 3 und 4 enthalten den Namen einer mit der Wand verknüpften Datenbank und eines Datenbankfeldes dieser Datenbank,
so wird der Inhalt dieses Datenbankfeldes zurückgegeben.



Übersetzungstabelle (nicht automatisch erstellt und möglicherweise nicht aktuell):

'basicobject' 		   = 'Basisobjekt' 

'isinserted'               = 'IstEingefügt'
'mark'                     = 'Bezeichnung'
'description'              = 'Beschreibung'
'function'                 = 'Funktion'
'exterior'                 = 'Aussenseite'
'load bearing'             = 'Tragend'
'fire rating'              = 'Feuerwiderstand'
'combustible construction' = 'Brennbare Konstruktion'
'compartmentation'         = 'Brandmauer'
'acoustic rating'          = 'Schalldämmung'
'model'                    = 'Typ'
'manufacturer'             = 'Hersteller'
'stylename'                = 'Stilname'

'recordvalue'              = 'Datenbankfeld'


Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs. 






```

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

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Fenster Teil eines Fassadenmoduls ist, andernfalls falsch.



#### __Objektdaten('IsWallExternal')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich das Fenster in einer Außenwand befindet oder nicht.



#### __Objektdaten('IsWallLoadBearing')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich das Fenster in einer tragenden Wand befindet oder nicht.



#### __Objektdaten('Material' [; Parameter 2] [; Parameter 3])__ ####

Gibt den Namen des Objektmaterials eines Bestandteils des Fensters zurück.

Parameter 1: 'material'

Parameter 2: <Bestandteil des Fensters>

Parameter 3 (nur wenn Parameter 2 = 'Verkleidung'): 'inside' oder 'outside'.

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
  Verkleidung
  Verkleidung aussen
  Verkleidung innen


Mehr und detaillierte Informationen zu dieser Funktion finden Sie bei den Beispielen.


```python
Beispiele: 

=Objektdaten('Material';'Rollladen')
=Objektdaten('Material';'handle')


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
Verkleidung  
Verkleidung aussen  
Verkleidung innen 


Bei der Verkleidung kann entweder der Aufruf mit

=Objektdaten('Material';'Verkleidung';'inside') (oder 'outside'. Dieser dritte Parameter steht nur bei der Verkleidung zur Verfügung!)

oder mit 


=Objektdaten('Material';'Verkleidung innen')

erfolgen.


Groß-/Kleinschreibung spielt keine Rolle.

Für alle Fensterbestandteile gibt es sowohl englische als auch deutsche Bezeichnungen.
Es wird empfohlen, im Zweifelsfall die englischen Bezeichnungen zu verwenden, da sich die deutschen in zukünftigen Versionen ändern können.

Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

"frame" = "Rahmen";
"stool" = "Fensterbank innen"; // also used for depth/height function
"sill" = "Fensterbank aussen"; // also used for depth/height function
"handle" = "Griff";
"glass" = "Glas";
"radiator" = "Heizkörper";
"windowshutter" = "Fensterladen";
"rollershutter" = "Rollladen";
"rollershutterbox" = "Rollladenkasten";
"rollershutterboxsymbol" = "Rollladenkastensymbol";
"rollershutterboxclosing" = "Rollladenkastenabschluss";
"railingtopbar" = "Geländeroberkante";
"railingbottombar" = "Geländerunterkante";
"railingframe" = "Geländerrahmen";
"railingrods" = "Geländerstäbe";
"railingposts" = "Geländerpfosten";
"reveal" = "Verkleidung";
"revealexterior" = "Verkleidung aussen";
"revealinterior" = "Verkleidung innen";



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.



```

#### __Objektdaten('ModeHeightAutoDimension')__ ####

Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.



#### __Objektdaten('ModeSelectedHeight')__ ####

Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Höhe an der Innenseite oder an der Außenseite definiert wird.



#### __Objektdaten('ModeSelectedWidth')__ ####

Gibt einen String zurück, der bei Fenstern, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Fenstern, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.



#### __Objektdaten('ModeWidthAutoDimension'[; Parameter 2])__ ####

Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung innen bzw. außen bemaßt wird. 

Parameter 2: Geben Sie 'inside' oder 'outside' bzw. 'Innen' oder 'Aussen' als Parameter an, wenn Sie nur einen der beiden Werte wünschen.


Mehr und detaillierte Informationen zu dieser Funktion finden Sie bei den Beispielen.


```python
=Objektdaten('modewidthautodimension')
=Objektdaten('modewidthautodimension'; 'inside')

Gibt einen String zurück, der angibt, welcher Breitenwert (Rohmaß, Fertigmaß...) von der Automatischen Bemaßung innen bzw. außen bemaßt wird. 

Für die meisten Parameter stehen deutsche und englische Bezeichnungen zur Verfügung.
Es wird empfohlen, die englischen Bezeichnungen zu verwenden.
Eine Übersetzungstabelle finden Sie weiter unten.

Diese Objektdatenfunktion kann mit einem oder zwei Parametern aufgerufen werden:


Parameter 1:

'modewidthautodimension'

Dieser Parameter ist der Name der Objektdatenfunktion.


Parameter 2 (optional):

'inside'              
'outside'


Dieser Parameter bewirkt, dass nur entweder die Bezeichnung der innen oder der außen bemaßten Breite zurückgegeben wird.

Fehlt dieser Parameter, so werden die Bezeichnungen beider Breitenwerte zurückgegeben.



Übersetzungstabelle:

'modewidthautodimension' = 'Definition Breite Autobemassung' 
'inside'                 = 'Innen';
'outside'                = 'Aussen'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.
```

#### __Objektdaten('revealexteriorprofile'[; Parameter 2])__ ####

Gibt das oder die Symbole zurück, mit denen die äußere Laibungsverkleidung gezeichnet wird.

Parameter 1:
'revealexteriorprofile'

Parameter 2:
'left','top','right','bottom'


```python
Beispiele: 

=Objektdaten('revealexteriorprofile')
=Objektdaten('revealexteriorprofile';'top')


Die Funktion gibt das oder die Symbole zurück, mit denen die äußere Laibungsverkleidung gezeichnet wird.

Wird nur ein Parameter übergeben, so gibt die Funktion eine Liste aller Profilsymbole der äußeren Verkleidung zurück.

Wird als zweiter Parameter eine Seite übergeben, so wird nur der Name des Symbols an dieser Seite übergeben.

Liste der unterstützten Seiten:

left
right
top
bottom

Für Funktionsnamen und Parameter stehen auch deutsche Übersetzungen zur Verfügung.
Es wird aber empfohlen, die englischen Bezeichnungen zu verwenden.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

'revealexteriorprofile' = 'Verkleidung aussen Profil'

'left'                  = 'Links'
'right'                 = 'Rechts'
'bottom'                = 'Unten'
'top'                   = 'Oben'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.



```

#### __Objektdaten('revealinteriorprofile'[; Parameter 2])__ ####

Gibt das oder die Symbole zurück, mit denen die innere Laibungsverkleidung gezeichnet wird.

Parameter 1:
'revealinteriorprofile'

Parameter 2:
'left','top','right','bottom'


```python
Beispiele: 

=Objektdaten('revealinteriorprofile')
=Objektdaten('revealinteriorprofile';'left')


Die Funktion gibt das oder die Symbole zurück, mit denen die innere Laibungsverkleidung gezeichnet wird.

Wird nur ein Parameter übergeben, so gibt die Funktion eine Liste aller Profilsymbole der inneren Verkleidung zurück.

Wird als zweiter Parameter eine Seite übergeben, so wird nur der Name des Symbols an dieser Seite übergeben.

Liste der unterstützten Seiten:

left
right
top
bottom

Für Funktionsnamen und Parameter stehen auch deutsche Übersetzungen zur Verfügung.
Es wird aber empfohlen, die englischen Bezeichnungen zu verwenden.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

'revealinteriorprofile' = 'Verkleidung innen Profil'

'left'                  = 'Links'
'right'                 = 'Rechts'
'bottom'                = 'Unten'
'top'                   = 'Oben'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.

```

#### __Objektdaten('RevealType')__ ####

Gibt den Typ der Laibungsverkleidung zurück, sofern das Fenster eine besitzt.



#### __Objektdaten('usedcutplane')__ ####

Gibt zurück, ob das Fenster für die Darstellung in 2D Draufsicht die Ebenenschnitthöhe, die Schnitthöhe der Wand oder eine individuelle Schnitthöhe verwendet.



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



#### __Dicke('Reveal'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der durchlaufenden Laibungsverkleidung zurück, sofern vorhanden. Optional kann noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll.



#### __Dicke('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!!



#### __Dicke('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen.



#### __Breite()__ ####

Gibt diejenige Breite des Fensters zurück, die im Reiter 'Fenstergröße' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Breite('BottomFrame')__ ####

Gibt die Breite des unteren Fensterrahmens zurück.



#### __Breite('FinishedBreiteInside')__ ####

Gibt das Fertigmaß Breite Innen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Breite('FinishedBreiteOutside')__ ####

Gibt das Fertigmaß Breite Außen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Breite('Frame')__ ####

Gibt die Breite des Fensterrahmens zurück. Dieser Wert entspricht dem IFC-Wert 'Lining Thickness'. Bei asymmetrischen Fenstern wird die Breite des linken Rahmens zurückgegeben.



#### __Breite('FrameClearBreite')__ ####

Gibt das Rahmenlichtmaß Breite zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Breite('FrameTotalBreite')__ ####

Gibt das Rahmenaußenmaß Breite zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Breite('LeftFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen linken Fensterrahmens zurück.



#### __Breite('overallreveal'[;<inside|outside>])__ ####

Gibt die Breite des Verkleidungsaußenmaßes zurück, sofern das Fenster eine Laibungsverkleidung besitzt. Wird kein optionaler Parameter angegeben und auf beiden Seiten ist eine Laibungsverkleidung vorhanden, entspricht der Rückgabewert dem Maß außen.



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



#### __Höhe('cutplane')__ ####

Gibt die Höhe der Schnittebene des Fensters in Bezug auf die Ebenenbasishöhe zurück. Verwendet das Fenster die Schnitthöhe der Wand, in die es eingefügt ist, wird stattdessen die Schnitthöhe der Wand zurückgegeben. Verwendet diese Wand die Schnitthöhe der Ebene, wird stattdessen die Schnitthöhe der Ebene zurückgegeben.



#### __Höhe('FinishedHöheObjectInside')__ ####

Gibt das Fertigmaß Höhe Fenster innen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('FinishedHöheObjectOutside')__ ####

Gibt das Fertigmaß Höhe Fenster außen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('FinishedHöheWallInside')__ ####

Gibt das Fertigmaß Höhe Wand innen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('FinishedHöheWallOutside')__ ####

Gibt das Fertigmaß Höhe Wand außen zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('FrameClearHöhe')__ ####

Gibt das Rahmenlichtmaß Höhe zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('FrameTotalHöhe')__ ####

Gibt das Rahmenaußenmaß Höhe zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Fenstergröße' des Fensterdialogs.



#### __Höhe('HeadHöheDefinedBySettings')__ ####

Gibt die Sturzhöhe gemäß Einstellungen zurück.



#### __Höhe('HeadHöheFromOrigin')__ ####

Gibt die Sturzhöhe ab Nullpunkt zurück.



#### __Höhe('Left')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('overallreveal'[;<inside|outside>])__ ####

Gibt die Höhe des Verkleidungsaußenmaßes zurück, sofern das Fenster eine Laibungsverkleidung besitzt. Wird kein optionaler Parameter angegeben und auf beiden Seiten ist eine Laibungsverkleidung vorhanden, entspricht der Rückgabewert dem Maß außen.



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



#### __Länge('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Länge der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Länge an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!! Ist keine Seite angegeben, wird die Gesamtlänge aller Seiten ausgegeben.



#### __Länge('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Länge der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Länge an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen. Ist keine Seite angegeben, wird die Gesamtlänge aller Seiten ausgegeben.



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

Gibt den Parameter oder den Datenbankeintrag vom entsprechenden Equipment-Objekt oder Rackrahmen des Geräts.



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


#### __Objektdaten('Kabelbreak'; '<Datenauswahl>'; [<Breakindex>)]__ ####

Daten des Kabelbreaks. Datenauswahl ist 'Name' und 'Tape'. Wird die Funktion auf ein Unterobjekt des Kabelbreaks angewendet, muss der Breakindex nicht angegeben werden. Wird hingegen die Funktion auf ein Kabel angewendet, muss der Breakindex. angegeben werden.



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
Objektliste:

=Pflanzenbild(2) zeigt das Bild, welches als Detailbild für die Pflanze (Kategorie Weitere Pflanzendaten im Dialogfenster der Pflanze) festgelegt wurde.



Einzelne Zelle:

Pflanzenbild(('Pflanze'.'Kürzel'='Pfl-1'), 4) zeigt das Bild welches als eigenes Bild für eine Pflanze mit Kürzel Pfl-1 festgelegt wurde.
```

## Funktionen für Pfosten

### Riegel

#### Fassade


#### __FassadePRLänge(Klassenname)__ ####

Länge aller Pfosten und Riegel einer Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Objektliste:

=FASSADEPRLÄNGE('')

Gibt Gesamtlänge aller Pfosten und/oder Riegel zurück.

Im Filter kann die Klasse des Pfostens oder des Riegels verwendet werden, um die Länge der Unterobjekte zu filtern.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FASSADEPRLÄNGE((T=WAND) & (SEL=WAHR), '')

Gibt Gesamtlänge aller Pfosten und/oder zurück, wenn das aktive Objekt eine Wand ist.

Im Filter kann die Klasse des Pfostens oder des Riegels verwendet werden, um die Länge der Uneterobjekte zu filtern.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __FassadeFüllFlächeBrt(Klassenname)__ ####

Bruttofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Objektliste:

=FASSADEFÜLLFLÄCHEBRT('')

Gibt die Bruttofläche aller Paneele der Fassade zurück.

Optional: Im Filter kann die Klasse der Füllung verwendet werden, um die Bruttofläche weiter zu filtern.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FASSADEFÜLLFLÄCHEBRT((T=WAND) & (SEL=WAHR), '')

Gibt die Bruttofläche aller Paneele der Fassade zurück, wenn das aktive Objekt eine Wand ist.

Optional: Im Filter kann die Klasse der Füllung verwendet werden, um die Bruttofläche weiter zu filtern.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __FassadeFüllFlächeNet(Klassenname)__ ####

Nettofläche der Füllungen der Fassade, die in der mit Klassenname bezeichneten Klasse liegen.


```python
Objektliste:

=FASSADEFÜLLFLÄCHENET('')

Gibt die Nettofläche aller Paneele der Fassade zurück.

Optional: Im Filter kann die Klasse der Füllung verwendet werden, um die Nettofläche weiter zu filtern.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FASSADEFÜLLFLÄCHENET((T=WAND) & (SEL=WAHR), '')

Gibt die Nettofläche aller Paneele der Fassade zurück, wenn das aktive Objekt eine Wand ist.

Optional: Im Filter kann die Klasse der Füllung verwendet werden, um die Nettofläche weiter zu filtern.

T = Objekttyp

SEL = Aktive Selektion (selection status)
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
=Objektdaten('Belag', 'PosNr', '
') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge auf, jeweils in einer neuen Zeile.
=Objektdaten('Belag', 'PosNr', ', ', 'Boden') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für Böden auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände') - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für Wände auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände', 1) - Listet die Positionsnummer aller in einem Raum verwendeten Beläge für die erste Wand auf.
=Objektdaten('Belag', 'PosNr', ', ', 'Wände', 2) - Listet die Positionsnummer, bzw. Artikel- oder Bestellnummer, aller in einem Raum verwendeten Beläge für die zweite Wand auf.

In einer Filterzeile einer Objektliste, für alle Unterobjekte von Räumen, die mit Raumbelag verknüpft sind.
Objektdaten('Belag', 'PosNr') - Entspricht dem Datenbankfeld 'Space_Finish'.'PosNr'
=Objektdaten('Belag', 'PosNr', '', 'Decke') - Positionsnummer (bzw. Artikel- oder Bestellnummer) des Belags, jedoch nur, wenn der Belag der Decke zugeordnet ist.
=Objektdaten('Belag', 'PosNr', '', 'Wände', 1) - Positionsnummer (bzw. Artikel- oder Bestellnummer) des Belags, jedoch nur, wenn der Belag der ersten Wand zugeordnet ist.
```

#### __Umfang('Brutto')__ ####

Gibt den Umfang der Bruttofläche zurück.



#### __Umfang('Aussparungen')__ ####

Gibt die Summe der Umfänge aller Aussparungen von der Nettofläche zurück.



#### __Umfang('Netto')__ ####

Gibt den Umfang der Nettofläche zurück.



#### __RaumNameVonObj()__ ####

Gibt den Namen des Raums zurück, in dem das Objekt sich befindet.


```python
Objektliste:

=RAUMNAMEVONOBJ

Gibt den dazugehörigen Raumname eines Objektes zurück, wenn dieses in einem Raum liegt oder diesen tangiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=RAUMNAMEVONOBJ((T=WAND) & (SEL=WAHR))

Gibt den dazugehörigen Raumname eines Objektes zurück, wenn dieses in einem Raum liegt oder diesen tangiert, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __RaumNumVonObj()__ ####

Gibt die Nummer des Raums zurück, in dem sich das Objekt befindet.


```python
Objektliste:

=RAUMNUMVONOBJ

Gibt die dazugehörige Raumnummer eines Objektes zurück, wenn dieses in einem Raum liegt oder diesen tangiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=RAUMNUMVONOBJ((T=WAND) & (SEL=WAHR))

Gibt die dazugehörige Raumnummer eines Objektes zurück, wenn dieses in einem Raum liegt oder diesen tangiert, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
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


#### __Tiefe('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Tiefe der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!!



#### __Tiefe('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen.



#### __Objektdaten('basicobject'[; Parameter 2][; Parameter 3][; Parameter 4])__ ####

Gibt Werte der Wand, in der die Tür eingefügt ist, zurück.

Parameter 1:
'basicobject'

Parameter 2:
'recordvalue', 'isinserted', 'mark', 'description', 'function', 'exterior', 'load bearing', 'fire rating', 'combustible construction', 'compartmentation', 'acoustic rating', 'model', 'manufacturer', 'stylename'

Parameter 3 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
<Name der verwendeten Datenbank>

Parameter 4 (nur verfügbar, wenn Parameter 2 = 'recordvalue'):
<Name des Datenbankfeldes einer Datenbank>


```python
=Objektdaten('basicobject'; 'description')
=Objektdaten('Basisobjekt'; 'IstEingefügt')
=Objektdaten('basicobject'; 'recordvalue'; 'MeineDatenbank'; 'MeinDatenbankfeld')

Gibt Werte der Wand, in der das Fenster eingefügt ist, zurück.

Für die meisten Parameter stehen deutsche und englische Bezeichnungen zur Verfügung.
Es wird empfohlen, die englischen Bezeichnungen zu verwenden.
Eine Übersetzungstabelle finden Sie weiter unten.

Diese Objektdatenfunktion kann mit zwei bis vier Parametern aufgerufen werden:


Parameter 1:


'basicobject'

Dieser Parameter bewirkt, dass die Werte des übergeordneten Objekts (in diesem Fall der Wand) und nicht der Tür selbst zurückgegeben werden.



Parameter 2:

'mark'              
'description'
'function'   
'exterior'     
'load bearing' 
'fire rating'   
'combustible construction'
'compartmentation'        
'acoustic rating'    
'model'              
'manufacturer'   
'stylename' 

Einer dieser Parameter bewirkt, dass der entsprechende Wert der Wand bzw. der IFC-Daten der Wand zurückgegeben wird.

'isinserted' 

Gibt zurück, ob die Tür in eine Wand eingefügt ist.

'recordvalue'   

Dieser Parameter bewirkt, dass der Inhalt des mit den beiden folgenden Parametern definierten Datenbankfeldes der Wand (also des Basisobjekts) zurückgegeben wird.



Parameter 3:

<Name einer Datenbank, mit der die Wand verknüpft ist>

Dieser Parameter wird nur berücksichtigt, wenn Parameter 2 = 'recordvalue'.



Parameter 4:

<Name eines Datenbankfeldes der in Parameter 3 spezifizierten Datenbank>




Ist Parameter2 = 'recordvalue' und Parameter 3 und 4 enthalten den Namen einer mit der Wand verknüpften Datenbank und eines Datenbankfeldes dieser Datenbank,
so wird der Inhalt dieses Datenbankfeldes zurückgegeben.



Übersetzungstabelle (nicht automatisch erstellt und möglicherweise nicht aktuell):

'basicobject' 		   = 'Basisobjekt' 

'isinserted'               = 'IstEingefügt'
'mark'                     = 'Bezeichnung'
'description'              = 'Beschreibung'
'function'                 = 'Funktion'
'exterior'                 = 'Aussenseite'
'load bearing'             = 'Tragend'
'fire rating'              = 'Feuerwiderstand'
'combustible construction' = 'Brennbare Konstruktion'
'compartmentation'         = 'Brandmauer'
'acoustic rating'          = 'Schalldämmung'
'model'                    = 'Typ'
'manufacturer'             = 'Hersteller'
'stylename'                = 'Stilname'

'recordvalue'              = 'Datenbankfeld'


Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.
```

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

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn die Tür Teil eines Fassadenmoduls ist, andernfalls falsch.



#### __Objektdaten('IsWallExternal')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Tür in einer Außenwand befindet oder nicht.



#### __Objektdaten('IsWallLoadBearing')__ ####

Gibt einen Booleschen Wert zurück, der angibt, ob sich die Tür in einer tragenden Wand befindet oder nicht.



#### __Objektdaten('Material' [; Parameter 2] [; Parameter 3])__ ####

Gibt den Namen des Objektmaterials eines Bestandteils der Tür zurück.

Parameter 1: 'material'

Parameter 2: <Bestandteil der Tür>

Parameter 3 (nur wenn Parameter 2 = 'Verkleidung'): 'inside' oder 'outside'.

Liste der unterstützten Türbestandteile:

  Beschlag
  Rahmen
  Rahmenfüllung
  Schwelle
  Stäbe Türblattfüllung
  Türblatt
  Türblattfüllung
  Verkleidung
  Verkleidung aussen
  Verkleidung innen
  Zarge





Mehr und detaillierte Informationen zu dieser Funktion finden Sie bei den Beispielen.


```python
Beispiele: 


=Objektdaten('Material';'Rollladen')
=Objektdaten('Material';'frame')

Allgemein:

=Objektdaten('Material'; <Türbestandteil>)

Die Funktion gibt den Namen des Objektmaterials eines Bestandteils der Tür zurück.



Liste der unterstützten Türbestandteile:

Beschlag
Rahmen  
Rahmenfüllung  
Schwelle  
Stäbe 
Türblattfüllung  
Türblatt  
Türblattfüllung   
Verkleidung  
Verkleidung aussen  
Verkleidung innen 
Zarge

Bei der Verkleidung kann entweder der Aufruf mit

=Objektdaten('Material';'Verkleidung';'inside') (oder 'outside'. Dieser dritte Parameter steht nur bei der Verkleidung zur Verfügung!)

oder mit 

=Objektdaten('Material';'Verkleidung innen')

erfolgen.

Groß-/Kleinschreibung spielt keine Rolle.

Für alle Türbestandteile gibt es sowohl englische als auch deutsche Bezeichnungen.
Es wird empfohlen, im Zweifelsfall die englischen Bezeichnungen zu verwenden, da sich die deutschen in zukünftigen Versionen ändern können.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

"frame" = "Rahmen";
"zarge" = "Zarge"; // No matching English word seems to exist
"leaf" = "Türblatt";
"leaffill" = "Türblattfüllung";
"framefill" = "Rahmenfüllung";
"leaffillbars" = "Stäbe Türblattfüllung";
"fitting" = "Beschlag";
"threshold" = "Schwelle";
"reveal" = "Verkleidung";
"revealexterior" = "Verkleidung aussen";
"revealinterior" = "Verkleidung innen";



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.


```

#### __Objektdaten('ModeHeightAutoDimension')__ ####

Gibt einen String zurück, der angibt, welcher Höhenwert von der Automatischen Bemaßung bemaßt wird.



#### __Objektdaten('ModeSelectedHeight')__ ####

Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Höhe ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird N/A zurückgegeben.



#### __Objektdaten('ModeSelectedWidth')__ ####

Gibt einen String zurück, der bei Türen, die die Laibungseinstellungen der Wand verwenden, angibt, welcher Wert die Gewählte Breite ist. Bei Türen, die nicht die Laibungseinstellungen der Wand verwenden, wird angegeben, ob die Breite an der Innenseite, Außenseite oder am Lichtmaß definiert wird.



#### __Objektdaten('ModeWidthAutoDimension'[; Parameter 2])__ ####

Gibt einen String zurück, der angibt, welcher Breitenwert von der Automatischen Bemaßung innen bzw. außen bemaßt wird. 

Parameter 2: Geben Sie 'inside' oder 'outside' bzw. 'Innen' oder 'Aussen' als Parameter an, wenn Sie nur einen der beiden Werte wünschen.


Mehr und detaillierte Informationen zu dieser Funktion finden Sie bei den Beispielen.


```python
=Objektdaten('modewidthautodimension')
=Objektdaten('modewidthautodimension'; 'inside')

Gibt einen String zurück, der angibt, welcher Breitenwert (Rohmaß, Fertigmaß...) von der Automatischen Bemaßung innen bzw. außen bemaßt wird. 

Für die meisten Parameter stehen deutsche und englische Bezeichnungen zur Verfügung.
Es wird empfohlen, die englischen Bezeichnungen zu verwenden.
Eine Übersetzungstabelle finden Sie weiter unten.

Diese Objektdatenfunktion kann mit einem oder zwei Parametern aufgerufen werden:


Parameter 1:

'modewidthautodimension'

Dieser Parameter ist der Name der Objektdatenfunktion.



Parameter 2 (optional):

'inside'              
'outside'


Dieser Parameter bewirkt, dass nur entweder die Bezeichnung der innen oder der außen bemaßten Breite zurückgegeben wird.

Fehlt dieser Parameter, so werden die Bezeichnungen beider Breitenwerte zurückgegeben.



Übersetzungstabelle:

'modewidthautodimension' = 'Definition Breite Autobemassung' 
'inside'                 = 'Innen';
'outside'                = 'Aussen'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.
```

#### __Objektdaten('opensinwalldirection')__ ####

Gibt einen String zurück, der angibt, auf welche Seite der Wand hin (links oder rechts) die Tür sich öffnen läßt.



#### __Objektdaten('revealexteriorprofile'[; Parameter 2])__ ####

Gibt das oder die Symbole zurück, mit denen die äußere Laibungsverkleidung gezeichnet wird.

Parameter 1:
'revealexteriorprofile'

Parameter 2:
'left','top','right','bottom'


```python
Beispiele: 

=Objektdaten('revealexteriorprofile')
=Objektdaten('revealexteriorprofile';'top')


Die Funktion gibt das oder die Symbole zurück, mit denen die äußere Laibungsverkleidung gezeichnet wird.

Wird nur ein Parameter übergeben, so gibt die Funktion eine Liste aller Profilsymbole der äußeren Verkleidung zurück.

Wird als zweiter Parameter eine Seite übergeben, so wird nur der Name des Symbols an dieser Seite übergeben.

Liste der unterstützten Seiten:

left
right
top
bottom

Für Funktionsnamen und Parameter stehen auch deutsche Übersetzungen zur Verfügung.
Es wird aber empfohlen, die englischen Bezeichnungen zu verwenden.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

'revealexteriorprofile' = 'Verkleidung aussen Profil'

'left'                  = 'Links'
'right'                 = 'Rechts'
'bottom'                = 'Unten'
'top'                   = 'Oben'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.


```

#### __Objektdaten('revealinteriorprofile'[; Parameter 2])__ ####

Gibt das oder die Symbole zurück, mit denen die innere Laibungsverkleidung gezeichnet wird.

Parameter 1:
'revealinteriorprofile'

Parameter 2:
'left','top','right','bottom'


```python
Beispiele: 

=Objektdaten('revealinteriorprofile')
=Objektdaten('revealinteriorprofile';'left')


Die Funktion gibt das oder die Symbole zurück, mit denen die innere Laibungsverkleidung gezeichnet wird.

Wird nur ein Parameter übergeben, so gibt die Funktion eine Liste aller Profilsymbole der inneren Verkleidung zurück.

Wird als zweiter Parameter eine Seite übergeben, so wird nur der Name des Symbols an dieser Seite übergeben.

Liste der unterstützten Seiten:

left
right
top
bottom

Für Funktionsnamen und Parameter stehen auch deutsche Übersetzungen zur Verfügung.
Es wird aber empfohlen, die englischen Bezeichnungen zu verwenden.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

'revealinteriorprofile' = 'Verkleidung innen Profil'

'left'                  = 'Links'
'right'                 = 'Rechts'
'bottom'                = 'Unten'
'top'                   = 'Oben'



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.





```

#### __Objektdaten('RevealType')__ ####

Gibt den Typ der Laibungsverkleidung zurück, sofern die Tür eine besitzt.



#### __Objektdaten('usedcutplane')__ ####

Gibt zurück, ob die Tür für die Darstellung in 2D Draufsicht die Ebenenschnitthöhe, die Schnitthöhe der Wand oder eine individuelle Schnitthöhe verwendet.



#### __Objektdaten('UseWallClosure')__ ####

Gibt einen Booleschen Wert zurück. Dieser ist wahr, wenn das Objekt die Laibungseinstellungen der Wand verwendet, andernfalls falsch.



#### __Objektdaten('WinDoorHandleType' [; Parameter 2] [; Parameter 3])__ ####

Gibt den Typ des Türgriffs eines Türblatts zurück. Falls in 3D ein Symbol als Türgriff angezeigt wird, wird der Name des Symbols zurückgegeben.

Parameter 1: 'WinDoorHandleType'

Parameter 2: <Nr. des Türblatts>

Parameter 3: <Seite der Tür>

Aufruf: =Objektdaten('Grifftyp'[; <Nr. des Türblatts>][; <Türseite>])

      Nr. des Türblatts: von innen gesehen von links nach rechts.

      Türseite: 'Innen' (Innenseite) oder 'Aussen' (Außenseite).


Beispiel: =Objektdaten('Grifftyp';'1';'innen')

Wird die Nummer des Türblatts weggelassen und die Türblätter haben verschiedene Grifftypen, kann kein eindeutiger Grifftyp ermittelt werden.
Falls auch noch die Türseite weggelassen wird, müssen alle Türgrifftypen innen und außen an allen Türblättern gleich sein, um einen eindeutigen Rückgabewert zu erhalten.


```python
Beispiele: 

=Objektdaten('windoorhandletype';'1','Innen')
=Objektdaten('Grifftyp';'2')


Die Funktion gibt den Typ des Türgriffs eines Türblatts zurück. Falls in 3D ein Symbol als Türgriff angezeigt wird, wird der Name des Symbols zurückgegeben.

Der zweite Parameter ist die Nummer des Türblatts, von innen gesehen von links nach rechts.

Der dritte Parameter ist die Seite des Türblatts, entweder 'Innen' oder 'Aussen'.

Der zweite und / oder der dritte Parameter können entfallen. 

Wird die Nummer des Türblatts weggelassen und die Türblätter haben verschiedene Grifftypen, kann kein eindeutiger Grifftyp ermittelt werden.

Falls auch noch die Türseite weggelassen wird, müssen alle Türgrifftypen innen und außen an allen Türblättern gleich sein, um einen eindeutigen Rückgabewert zu erhalten.



Für Funktionsnamen und Parameter stehen auch deutsche Übersetzungen zur Verfügung.
Es wird aber empfohlen, die englischen Bezeichnungen zu verwenden.


Hier die Zuordnungen der deutschen zu den englischen Bezeichnungen:

'windoorhandletype' = 'Grifftyp'

Seiten:

'inside' = 'Innen';
'outside' = 'Aussen';



Eine vollständige und aktuelle Übersetzungstabelle aller verfügbaren Parameter aller Tabellenfunktionen in Vectorworks finden Sie in der Textdatei "WorksheetFunctionOptionsRegistry.txt", die beim Programmstart von Vectorworks automatisch angelegt und im Plug-Ins-Ordner des Benutzerordners gespeichert wird, sowie im Expertenreiter des Fenster- oder Türendialogs.





```

#### __Dicke('Reveal'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der durchlaufenden Laibungsverkleidung zurück, sofern vorhanden. Optional kann noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll.



#### __Dicke('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!!



#### __Dicke('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Dicke der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Dicke an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen.



#### __Breite()__ ####

Gibt diejenige Breite der Tür zurück, die im Reiter 'Türbreite' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Breite ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Breite('FinishedBreiteInside')__ ####

Gibt das Fertigmaß Breite Rechts zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('FinishedBreiteOutside')__ ####

Gibt das Fertigmaß Breite Links zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('FittingsClearBreite')__ ####

Gibt die Lichte Breite Beschlag zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('FrameClearBreite')__ ####

Gibt das Lichte Durchgangsmaß Breite zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('FrameTotalBreite')__ ####

Gibt das Zargen-/Rahmenaußenmaß Breite zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('leaf'[;<# of door leaf>])__ ####

Gibt die Breite des Türblattes zurück. Optional kann die Nummer des Türblatts (von innen gesehen) übergeben werden. Wird keine Nummer übergeben und mehrere Türblätter haben unterschiedliche Breiten, ist der Wert nicht definiert.



#### __Breite('leaffill'[;<# of door leaf>])__ ####

Gibt die Breite der Türblattfüllung zurück. Optional kann die Nummer des Türblatts (von innen gesehen) übergeben werden. Wird keine Nummer übergeben und mehrere Türblätter haben unterschiedliche Füllungen, ist der Wert nicht definiert.



#### __Breite('LeftFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen linken Türrahmens zurück.



#### __Breite('NinetyDegreesClearBreite')__ ####

Gibt die Lichte Breite 90° zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('overallreveal'[;<inside|outside>])__ ####

Gibt die Breite des Verkleidungsaußenmaßes zurück, sofern die Tür eine Laibungsverkleidung besitzt. Wird kein optionaler Parameter angegeben und auf beiden Seiten ist eine Laibungsverkleidung vorhanden, entspricht der Rückgabewert dem Maß außen.



#### __Breite('Rebate')__ ####

Gibt das Zargen-/Rahmenfalzmaß zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('RightFrame')__ ####

Gibt die Breite des von der rechten Wandseite (innen) aus gesehen Türrahmens zurück.



#### __Breite('TopFrame')__ ####

Gibt die Breite des oberen Türrahmens zurück.



#### __Breite('UnfinishedBreite')__ ####

Gibt das Rohmaß Breite zurück. Das Rohmaß ist definiert als Fertigmaß + Überlappung + Montagefuge (siehe Laibungsdialog). Eine graphische Veranschaulichung finden Sie auch im Reiter 'Türbreite' des Türendialogs.



#### __Breite('unitsizehingeside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandseite der Tür zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Breite('unitsizestopside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandgegenseite der Tür zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türbreite' des Türendialogs.



#### __Höhe()__ ####

Gibt diejenige Höhe der Tür zurück, die im Reiter 'Türhöhe' eingestellt ist. Bitte beachten Sie, dass dies möglicherweise nicht diejenige Höhe ist, die in Bemaßungen oder Beschriftungen angezeigt wird.



#### __Höhe('cutplane')__ ####

Gibt die Höhe der Schnittebene der Tür in Bezug auf die Ebenenbasishöhe zurück. Verwendet die Tür die Schnitthöhe der Wand, in die sie eingefügt ist, wird stattdessen die Schnitthöhe der Wand zurückgegeben. Verwendet diese Wand die Schnitthöhe der Ebene, wird stattdessen die Schnitthöhe der Ebene zurückgegeben.



#### __Höhe('FinishedHöheWallInside')__ ####

Gibt das Fertigmaß Höhe rechts zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('FinishedHöheWallOutside')__ ####

Gibt das Fertigmaß Höhe links zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('FrameClearHöhe')__ ####

Gibt das Lichte Durchgangsmaß Höhe zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('FrameTotalHöhe')__ ####

Gibt das Zargen-/Rahmenaußenmaß Höhe zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('leaf'[;<# of door leaf>])__ ####

Gibt die Höhe des Türblattes zurück. Optional kann die Nummer des Türblatts (von innen gesehen) übergeben werden. Wird keine Nummer übergeben und mehrere Türblätter haben unterschiedliche Höhen, ist der Wert nicht definiert.



#### __Höhe('leaffill'[;<# of door leaf>])__ ####

Gibt die Höhe der Türblattfüllung zurück. Optional kann die Nummer des Türblatts (von innen gesehen) übergeben werden. Wird keine Nummer übergeben und mehrere Türblätter haben unterschiedliche Füllungen, ist der Wert nicht definiert.



#### __Höhe('Left')__ ####

Hilfsfunktion für die Automatische Bemaßung. Nicht für den Einsatz in Tabellen gedacht.



#### __Höhe('overallreveal'[;<inside|outside>])__ ####

Gibt die Höhe des Verkleidungsaußenmaßes zurück, sofern die Tür eine Laibungsverkleidung besitzt. Wird kein optionaler Parameter angegeben und auf beiden Seiten ist eine Laibungsverkleidung vorhanden, entspricht der Rückgabewert dem Maß außen.



#### __Höhe('Rebate')__ ####

Gibt das Zargen-/Rahmenfalzmaß zurück.  Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



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

Gibt das Bekleidungsaußenmaß an der Bandseite der Tür zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Höhe('unitsizestopside')__ ####

Gibt das Bekleidungsaußenmaß an der Bandgegenseite der Tür zurück. Eine bildliche Beschreibung dieses Wertes finden Sie im Reiter 'Türhöhe' des Türendialogs.



#### __Anzahl('Leaf')__ ####

Gibt die Anzahl der Türblätter zurück.



#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __Fläche('leaffill'[;<# of door leaf>])__ ####

Gibt die Fläche der Türblattfüllung eines Türblatts zurück. Die Nummer des Türblatts ist von innen gesehen. Wird keine Nummer übergeben, wird die Summe der Flächen aller Türblattfüllungen zurückgegeben.



#### __Länge('RevealExterior'[;<left|right|top|bottom>])__ ####

Gibt die Länge der Laibungsverkleidung an der Außenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Länge an welcher der vier Seiten ausgegeben werden soll. !!! Links/Rechts sind dabei - anders als bei anderen Objektdatenfunktionen - von außen her gesehen !!! Ist keine Seite angegeben, wird die Gesamtlänge aller Seiten ausgegeben.



#### __Länge('RevealInterior'[;<left|right|top|bottom>])__ ####

Gibt die Länge der Laibungsverkleidung an der Innenseite der Wand zurück, sofern vorhanden. Optional kann für nicht durchlaufende Laibungsverkleidungen noch angegeben werden, die Länge an welcher der vier Seiten ausgegeben werden soll. Links/Rechts sind dabei von innen her gesehen. Ist keine Seite angegeben, wird die Gesamtlänge aller Seiten ausgegeben.



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
=Grundfläche('Brutto')

Gibt die Bruttogrundfläche der Wand oder Wandschicht zurück.

=Grundfläche('Brutto', 'Schicht=Dämmung') gibt die Bruttogrundfläche der Schicht Dämmung zurück,

=Grundfläche('Brutto', 'Höhe=10cm') gibt die Bruttogrundfläche einer Wand oder Wandschicht, gemessen in einer Höhe von 10 Zentimeter oberhalb der Ebenenbasishöhe.


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
=Grundfläche('Netto')

Gibt die Nettogrundfläche der Wand oder Wandschicht zurück.

=Grundfläche('Netto', 'Min Öffnungsfläche=0,5m2') gibt die Nettogrundfläche der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 Quadratmeter ignoriert werden.

=Grundfläche('Netto', 'Min Öffnungsfläche=0,5m2', 'Max Öffnungsfläche=1m2') gibt die Nettogrundfläche der Wand oder Wandschicht zurück, wobei Öffnungen unter einem halben und über einem Quadratmeter ignoriert werden.

=Grundfläche('Netto', 'Öffnungstyp'='Tür') gibt die Nettogrundfläche der Wand oder Wandschicht zurück, wobei nur Öffnungen durch Türen berücksichtigt werden.

=Grundfläche('Netto', 'Öffnungstyp ausschließen=Tür') gibt  die Nettogrundfläche der Wand oder Wandschicht zurück, wobei Öffnungen durch Türen ignoriert werden.

=Grundfläche('Netto', 'Schicht=Dämmung') gibt ie Nettogrundfläche der Schicht Dämmung zurück.

=Grundfäche('Netto', 'Höhe=10cm' gibt die Nettgrundfläche der Wand oder Wandschicht zurück, gemessen in einer Höhe 10 Zentimeter oderhalb der Ebenenbasishöhe.


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
=Grundfläche('Öffnungen')

Gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück.

=Grundfläche('Öffnungen', 'Min Öffnungsfläche=0,5 m2') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 Quadratmeter ignoriert werden.

=Grundfläche('Öffnungen', 'Min Öffnungsfläche=0,5 m2', 'Max Öffnungsfläche=1 m2') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 oder über einem Quadratmeter ignoriert werden.

=Grundfläche('Öffnungen', 'Öffnungstyp=Tür') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück, wobei nur Öffnungen durch Türen berücksichtigt werden.

=Öffnungsfläche('Öffnungen', 'Öffnungstyp ausschließen=Tür') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück, wobei Öffnungen durch Türen ignoriert werden.

=Grundfläche('Öffnungen', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wandschicht Dämmung zurück.

Grundfläche('Öffnungen', 'Höhe=10cm') gibt die Gesamtfläche der Öffnungen auf der Grundfläche der Wand oder Wandschicht zurück,  gemessen in einer Höhe 10 Zentimeter oderhalb der Ebenenbasishöhe.


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
=Anzahl('Einfügungen')

Gibt die Anzahl der in der Wand eingefügten Objekte zurück.

=Anzahl('Einfügungen', 'Einfügungstyp=Fenster; Tür') gibt die Anzahl der eingefügten Fenster und Türen.

Der Unterschied zwischen Anzahl('Einfügungen') und Anzahl('Öffnungen') ist, dass in (seltenen) Fällen, in denen zwei eingefügte Objekte dieselbe Öffnung haben, Anzahl('Einfügungen') sie als getrennte Objekte, während Anzahl('Öffnungen') sie als eine einzige Öffnung behandelt.


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

'Höhe=...':  Die Höhe in Bezug zur Ebene, in der die Grundfläche und -l


```python
=Anzahl('Öffnungen')

Gibt die Anzahl der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Deck-Schicht zurück.

=Anzahl('Öffnungen', 'Min Öffnungsvolumen=10 cm3') gibt die Anzahl der Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern zurück.

=Anzahl('Öffnungen', 'Min Öffnungsfläche oben=0,5qm2', 'Max Öffnungsfläche oben=1 m2') gibt die Anzahl der Öffnungen zwischen 0,5 und einem Quadratmeter oben in Boden/Decke oder Boden/Decke-Schicht.

=Anzahl('Öffnungen', 'Min Öffnungsfläche unten=0,25m2'. 'Max Öffnungsvolumen=1m3') gibt die Anzahl der Öffnungen mit einer Fläche von mindestens 0,25 Quadratmeter unten in Boden/Decke oder Boden/Decke-Schicht und einem Volumen von höchstens einem Kubikmeter

=Anzahl('Öffnungen', 'Öffnungstyp=Fenster') gibt die Anzahl der Öffnungen durch Fenster zurück.

=Anzahl('Öffnungen', 'Schicht=Dämmung', 'Min Öffnungsvolumen=10cm3') gibt die Öffnungen mit einem Volumen von mindestens 10 Kubikzentimeter in der Schicht Dämmung zurück.

Der Unterschied zwischen Anzahl('Einfügungen') und Anzahl('Öffnungen') ist, dass in (seltenen) Fällen, in denen zwei eingefügte Objekte dieselbe Öffnung haben, Anzahl('Einfügungen') sie als getrennte Objekte, während Anzahl('Öffnungen') sie als eine einzige Öffnung behandelt.


```

#### __Winkel('Energos')__ ####

Gibt den Winkel zur Nordrichtung an, der in den Energieberechnungen für dieses Objekt verwendet wird.



#### __WandflächeNetto()__ ####

2D-Wandfläche einer Wand ohne Tür- und Fensterflächen.


```python
Objektliste:

=WANDFLÄCHENETTO

Gibt die Nettofläche einer Wand ohne Tür- und Fensteröffnungsflächen zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=WANDFLÄCHENETTO((T=WAND) & (SEL=WAHR))

Gibt die Nettofläche einer Wand zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __WandflächeBrutto()__ ####

2D-Wandfläche einer Wand inkl. Tür- und Fensterflächen.


```python
Objektliste:

=WANDFLÄCHEBRUTTO

Gibt die Bruttofläche einer Wand ohne Tür- und Fensteröffnungsflächen zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=WANDFLÄCHEBRUTTO((T=WAND) & (SEL=WAHR))

Gibt die Nettofläche einer Wand zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __DurchschnWandhöhe()__ ####

Durchschnittliche Wandhöhe inkl. der höchsten Punkte und verschiedener Anfangs- und Endhöhen.


```python
Objektliste:

=DURCHSCHNWANDHÖHE

Gibt die Durchschnittshöhe einer Wand zurück, wenn diese an ein Objekt angepasst wurde.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DURCHSCHNWANDHÖHE((T=WAND) & (SEL=WAHR))

Gibt die Durchschnittshöhe einer Wand zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Wanddicke()__ ####

Wanddicke.


```python
Objektliste:

=WANDDICKE

Gibt die Gesamtdicke einer Wand zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=WANDDICKE((T=WAND) & (SEL=WAHR))

Gibt die Gesamtdicke einer Wand zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Wandstilname()__ ####

Name des Wandstils.


```python
Objektliste:

=WANDSTIL

Gibt Namen des Wandstils zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=WANDSTIL((T='WAND') & (SEL=WAHR))

Gibt Namen des Wandstils zurück, wenn das aktive Objekt eine WAND ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
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
=Oberfläche'Mitte Brutto') gibt die Bruttofläche entlang der Mittellinie der Wand oder Wandschicht zurück.



Oberfläche('Mitte Brutto', 'Schicht=Dämmung') gibt die Bruttofläche entlang der Mittellinie der Wandschicht 'Dammung' zurück.
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
=Oberfläche('Mitte Netto') gibt die Fläche entlang der Mittellinie der Wand oder Wandschicht zurück, wobei alle Öffnungen berücksichtigt werden.



=Oberfläche('Mitte Netto', 'Min Öffnungsfläche=0.5 m2') gibt die Fläche entlang der Mittellinie der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



Oberfläche('Mitte Netto', 'Min Öffnungsfläche=0,5 m2', 'Max Öffnungsfläche=1 m2') gibt die Fläche entlang der Mittellinie der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



Oberfläche('Mitte Netto', 'Öffnungstyp=Fenster') gibt die Fläche entlang der Mittellinie der Wand oder Wandschicht zurück, wobei nur Öffnungen durch Fenster berücksichtigt werden.



Oberfläche('Mitte Netto', 'Öffnungstyp ausschließen=Fenster') gibt die Fläche entlang der Mittellinie der Wand oder Wandschicht zurück, wobei nur Öffnungen durch Fenster ignoriert werden.



Oberfläche('Mitte Netto', 'Schicht=Dämmung') gibt die Fläche entlang der Mittellinie der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Links Brutto') gibt die Bruttofläche der linken Seite der Wand oder Wandschicht zurück, wobei alle Öffnungen ignoriert werden.



=Oberfläche('Links Brutto', 'Schicht=Dämmung') gibt die Bruttofläche der linken Seite der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Links Netto') gibt die Fläche der linken Seite der Wand oder Wandschicht zurück, wobei alle Öffnungen berücksichtigt werden.



=Oberfläche('Links Netto', 'Min Öffnungsfläche=0.5 m2') gibt die Fläche der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden



=Oberfläche('Links Netto', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Fläche der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Links Netto', 'Öffnungstyp=Fenster') gibt die Fläche der linken Seite der Wand oder Wandschicht zurück, wobei nur Öffnungen von 'Fenster' berücksichtigt werden.



=Oberfläche('Links Netto', 'Öffnungstyp ausschließen=Fenster') gibt die Fläche der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen von 'Fenster' ignoriert werden.



=Oberfläche('Links Netto', 'Schicht=Dämmung') gibt die Fläche der linken Seite der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Öffnungen Mitte') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wand oder Wandschicht zurück.



=Oberfläche('Öffnungen Mitte', 'Min Öffnungsfläche=0.5 m2') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



=Oberfläche('Öffnungen Mitte', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Öffnungen Mitte', 'Öffnungstyp=Fenster') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wand oder Wandschicht zurück, wobei nur Öffnungen durch 'Fenster' berücksichtigt werden.



=Oberfläche('Öffnungen Mitte', 'Öffnungstyp ausschließen=Fenster') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wand oder Wandschicht zurück, wobei Öffnungen durch 'Fenster' ignoriert werden.



=Oberfläche('Öffnungen Mitte', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen entlang der Mittellinie der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Öffnungen links') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wand oder Wandschicht zurück.



=Oberfläche('Öffnungen links', 'Min Öffnungsfläche=0.5 m2') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



=Oberfläche('Öffnungen links', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Öffnungen links', 'Öffnungstyp=Fenster') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wand oder Wandschicht zurück, wobei nur Öffnungen durch 'Fenster' berücksichtigt werden.



=Oberfläche('Öffnungen links', 'Öffnungstyp ausschließen=Fenster') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wand oder Wandschicht zurück, wobei Öffnungen durch 'Fenster' ignoriert werden.



=Oberfläche('Öffnungen links', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen auf der linken Seite der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Öffnungen rechts') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wand oder Wandschicht zurück.



=Oberfläche('Öffnungen rechts', 'Min Öffnungsfläche=0.5 m2') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden.



=Oberfläche('Öffnungen rechts', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Öffnungen rechts', 'Öffnungstyp=Fenster') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wand oder Wandschicht zurück, wobei nur Öffnungen durch 'Fenster' berücksichtigt werden.



=Oberfläche('Öffnungen rechts', 'Öffnungstyp ausschließen=Fenster') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen durch 'Fenster' ignoriert werden.



=Oberfläche('Öffnungen rechts', 'Schicht=Dämmung') gibt die Gesamtfläche der Öffnungen auf der rechten Seite der Wandschicht 'Dämmung' zurück.
```

#### __Oberfläche('Rechts Brutto'; [optionale Parameter])__ ####

Fläche der rechten Wand- oder Wandschichtoberfläche. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.

'Versatz vom Start=...' / 'Versatz vom Ende=...': Falls angegeben, wird nur die Fläche zwischen dem Versatz am Start und am Ende des Wandpfades berechnet.


```python
=Oberfläche('Rechts Brutto') gibt die Bruttofläche der rechten Seite der Wand oder Wandschicht zurück, wobei alle Öffnungen ignoriert werden.



=Oberfläche('Rechts Brutto', 'Schicht=Dämmung') gibt die Bruttofläche der rechten Seite der Wandschicht 'Dämmung' zurück.
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
=Oberfläche('Rechts Netto') gibt die Fläche der rechten Seite der Wand oder Wandschicht zurück, wobei alle Öffnungen berücksichtigt werden.



=Oberfläche('Rechts Netto', 'Min Öffnungsfläche=0.5 m2') gibt die Fläche der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 ignoriert werden



=Oberfläche('Rechts Netto', 'Min Öffnungsfläche=0.5 m2', 'Max Öffnungsfläche=1 m2') gibt die Fläche der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen unter 0,5 m2 und über 1 m2 ignoriert werden.



=Oberfläche('Rechts Netto', 'Öffnungstyp=Fenster') gibt die Fläche der rechten Seite der Wand oder Wandschicht zurück, wobei nur Öffnungen von 'Fenster' berücksichtigt werden.



=Oberfläche('Rechts Netto', 'Öffnungstyp ausschließen=Fenster') gibt die Fläche der rechten Seite der Wand oder Wandschicht zurück, wobei Öffnungen von 'Fenster' ignoriert werden.



=Oberfläche('Rechts Netto', 'Schicht=Dämmung') gibt die Fläche der rechten Seite der Wandschicht 'Dämmung' zurück.
```

#### __Volumenn()__ ####

Das Volumen einer Wand, einer Decke oder Boden, eines Daches oder einer Dachfläche oder deren Schichten.



#### __Volumenn('Brutto'; [optionale Parameter])__ ####

Das Volumen einer Wand, Wandschicht, Boden/Decke oder Boden/Deckenschicht. Alle Öffnungen werden ignoriert.

'Schichtname=...': Es werden nur Schichten mit dem angegebenen Namen berücksichtigt.

'Schichtmaterial=...': Es werden nur Schichten mit dem angegebenen Material berücksichtigt.

'Schicht=...': Es werden nur die angegebenen Schichten berücksichtigt. Mögliche Werte sind links, rechts, Kern oder eine Zahl, die die Position der Schicht innerhalb der Wand angibt.


```python
=Volumen('Brutto')

Gibt das Bruttovolumen der Wand, Wandschicht, Boden/Decke und Boden/Decke-Schicht zurück.

=Volumen('Brutto', 'Schicht=Dämmung') gibt das Bruttovolumen der Wandschicht namens Dämmung zurück.


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
=Volumen('Netto')

Gibt das Volumen der Wand, Wandfläche, Boden/Decke und Boden/Decke-Schicht zurück.

=Volumen('Netto', 'Min Öffnungsvolumen=10 cm2') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern berücksichtigt werden.

=Volumen('Netto', 'Min Öffnungvolumen=10 cm2', 'Max Öffnungsvolumen=1 m3')  gibt das Volumen der Wand , Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nür Öffnungen mit einem Volumen zwischen 10 Kubikzentimetern und 1 Kubikmeter berücksichtigt werden.

=Volumen('Netto', 'Öffnungstyp=Fenster') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen durch Fenster berücksichtigt werden.

=Volumen('Netto', 'Öffnungstyp=Fenster; Tür') gibt das Volumen der Wand, Wandfläche, Boden/Decke, Boden/Decke-Schicht zurück, wobei nur Öffnungen durch Fenster und Türen berücksichtigt werden

=Volumen('Netto', 'Schicht=Dämmung', 'Min Öffnungsvolumen=10 cm3') gibt das Volumen der Wandschicht Dämmung zuück, wobei nur Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern berücksichtigt werden.


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
=Volumen('Öffnungen')

Gibt das Gesamtvolumen der Öffnungen in einer Wand, Wandschicht, Boden/Decke oder Boden/Decke-Schicht zurück.

=Volumen('Öffnungen', 'Min Öffnungsvolumen=10 cm3') gibt das Gesamtvolumen von Öffnungen mit einem Volumen von mindestens 10 Kubikzentimetern zurück.

=Volumen('Öffnungen', 'Min Öffnungsvolumen=10 cm3', 'Max Öffnungsvolumen=1 m3') gibt das Gesamtvolumen von Öffnungen mit einem Volumen zwischen 10 Kubikzentimetern und 1 Kubikmeter zurück.

=Volumen('Öffnungen', 'Öffnungstyp=Fenster') gibt das Gesamtvolumen der Öffnungen durch Fenster zurück.

=Volumen('Öffnungen', 'Schichtname=Dämmung', 'Min Öffnungsvolumen=10cm3') gibt das Gesamtvolumen von Öffnungen mit mindestens 10 Kubikzentimetern in der Wandschicht namens Dämmung.


```

#### __Wandhöhe()__ ####

Höhe von Wänden in der Zeichnung.


```python
Objektliste:

=WANDHÖHE

Gibt die Höhe einer Wand zurück. Bezogen auf die Höhe der Einfügeoptionen.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 

Alternativ für die Schichthöhen:

=IF((UNTEROBJEKTNAME='Schicht'), HÖHE(), '')



einzelne Zelle:

=WANDHÖHE((T=WAND) & (SEL=WAHR))

Gibt die Höhe einer Wand zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
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


#### __WECHSELN(Zahl; Wert1; Wert2; ... Wert_keine_Übereinstimmung)__ ####

Die Bedingung legt setzt einen Zähler (Zahl) und eine Liste mit Werten voraus. Zurückgegeben wird der Zahl entsprechende Wert in der Liste.


```python
=WECHSELN(3, 'Montag', 'Dienstag', 'Mittwoch', 'Donnerstag', 'Freitag', 'Samstag', 'Sonntag', 'no match')

Hierbei werden alle Wochentage aufgelistet. Im Zähler ist die Zahl 3 (welcher auch auf eine andere Zelle verwiesen werden kann). Die Liste wird nun durch gezählt bis zum Wert 3, was dem Mittwoch entspricht. Sollte der Wert 8 sein, so wird 'no match' zurückgegeben.


```

#### __IFS((Logik1); Wert1; (Logik2); Wert2; ...; (Logikn); Wertn))__ ####

IFS erlaubt die Prüfung von mehreren aufeinanderfolgende Ereignisse/Abfragen. Der erste zutreffende Wert wird zurückgegeben.


```python
=IFS(A1=40, 'ist gleich', A1>40, 'ist größer', A1<40, 'ist kleiner')

IFS erlaubt die Prüfung von mehreren aufeinanderfolgende Ereignisse/Abfragen. Der erste zutreffende Wert wird zurückgegeben.

Hierbei wird in einer folge geprüft, ob der Wert in der Zelle A1 gleichgross, größer oder kleiner als 40 ist. Wenn der gleich 40 wäre. Wird 'ist gleich' zurückgegeben. Ansonsten einer der darauf folgenden Werte 'ist größer' oder 'ist kleiner'.
```

#### __EXAKT(Wert1; Wert2)__ ####

Prüft, ob Wert 1 und Wert 2 identisch sind. Ist dem so, wird 'WAHR' zurückgegeben.


```python
=EXAKT('Erdgeschoss','Erdgeschoss') = WAHR

=EXAKT('Erdgeschoss','erdgeschoss') = FALSCH



Wenn die beiden Werte übereinstimmen wie 'Erdgeschoss' -> 'Erdgeschoss' wird 'WAHR' zurückgegeben. Unterscheiden sich diese durch Gross- /Kleinschreibung oder weichen grundsätzlich voneinander ab. So wird 'FALSCH' zurückgegeben.

Hierbei können Stings, Integer (Ganzzahl) oder Floating (reele Zahl) verglichen werden.
```

#### __ISTUNGÜLTIG(Wert)__ ####

Prüft, ob ein Wert ungültig ist. Gibt 'WAHR' zurück, wenn der Wert ungültig (N/A).


```python
=ISTUNGÜLTIG(OBJEKTDATEN('Lambda'))

Hierbei wird geprüft, ob der Wert einen ungültigen Wert N/A zurückgibt. Ist der Wert N/A, so wird 'WAHR' zurückgegeben.



Bemerkung: ISTUNGÜLTIG kann auch eine IF Abfrage in der Folge haben, um zum Beispiel 'WAHR' oder 'FALSCH' mit einem Text zu ersetzen.



=IF(ISTUNGÜLTIG(OBJEKTDATEN('Lambda')), 'kein Wert', 'Wert vorhanden').



Diese Funktion würde nun den Status des Lambda Wertes prüfen und ein 'WAHR' oder 'FALSCH' zurückgeben. Die IF-Funktion ersetzt dessen Resultat im Anschluss.

WAHR = 'kein Wert', FALSCH = 'Wert vorhanden'
```

#### __IFUNGÜLTIG(Wert; Wert_wenn_ungültig)__ ####

Ist ein Wert ungültig, wird N/A zurückgegeben. Dies kann mit IfUngültig abgefangen werden und bit einem bliebigen Text ersetzt werden.


```python
=IFUNGÜLTIG(A1, 'Wert nicht spezifiziert!')



Die Zelle A1 gibt den Wert N/A zurück. Mit der Bedingung 'Wert nicht spezifiziert!' wird der Fehler abgefangen und mit deren Inhalt ersetzt.




```

#### __ERSTERNICHTLEER(Wert1; Wert2; Wert3; ...)__ ####

Prüft die Werte einer Liste in der Reihenfolge, ob diese einen Wert haben. Ist das Datenfeld leer, wird das nächste geprüft. Der erste zutreffende Wert wird angezeigt.


```python
=ERSTERNICHTLEER(STILNAME, NAME, 'Bauteil hat kein Name')



Gibt ersten gültigen Wert zurück. Wenn das Objekt kein Stil hat, wird der Name in der Infopalette abgefragt. Hat dieser auch kein Wert wird 'Bauteil hat kein Namen' zurückgegeben.


```

#### __ISTFEHLER(Wert)__ ####

Prüft, ob der Wert einen Fehler verursacht. Trifft dies zu wird 'WAHR' zurückgegeben.



#### __IFFEHLER(Fehler; Wert_wenn_Fehler)__ ####

Prüft, ob die erste Bedingung einen Fehler beinhaltet. Trifft dies zu, wird auf die zweite Bedingung ausgewichen.



#### __IF((Bedingung); ‘dann’; ‘sonst’)__ ####

Verwendet einen gegeben Wert, wenn die vorabgegebene Bedingung erfüllt wird. Ansonsten wird ein anderer Wert zurückgegeben.


```python
=IF((B1 > 75), 'zu teuer', 'Preis OK')

Hierbei wird der der Wert aus der Zelle B1 verglichen. Ist dieser grösser als 75 wird der Wert 'zu teuer' zurückgegeben. Ist der Wert kleiner wird der Wert 'Preis OK' zurückgegeben.
```

## Math. Formeln


#### __RUNDEN(x)__ ####

Rundet auf eine Ganzezahl.


```python
=RUNDEN(2.345)

Rundet auf eine Ganzzahl. Wobei ⎡x.5⎤ aufgerundet wird und ⎣x.4⎦ abgerundet. Somit wird 2.345 zu 2.


```

#### __SIN(x)__ ####

Sinus von x.


```python
[RAD] = SIN(0.524) ≈ 0.5

[GRAD] = SIN(GRADRAD(30)) = 0.5 - um den SINUS in Grad zu rechnen.

In Kombination mit GRADRAD wird der Wert von in Grad ins Bogenmaß (RAD) umgerechnet. RAD = Grad * PI()/180.
```

#### __COS(x)__ ####

Cosinus des Winkels x.


```python
[RAD] = COS(1.0472) ≈ 0.5

[GRAD] = COS(GRADRAD(60)) = 0.5 - um den COSINUS in Grad zu rechnen.

In Kombination mit GRADRAD wird der Wert von in Grad ins Bogenmaß (RAD) umgerechnet. RAD = Grad * PI()/180.
```

#### __EXP(x)__ ####

Verwendet die eulerische Zahl/Exponential Funktion (e=2,71828182845904).


```python
=EXP(1)

wobei e^1 = 2,71828182845904 entspricht.


```

#### __LN(x)__ ####

Der natürliche Logarithmus (Basis e) von x.


```python
=LN(12)

Gibt den natürlichen Logarithmus der Zahl 12 zurück.


```

#### __WURZEL(x)__ ####

Gibt die Quadratwurzel einer Zahl zurück.


```python
=WURZEL(64)

Berechnet die Wurzel der Zahl 64. √(64) = 8


```

#### __ATAN(x)__ ####

Arcustangens des Winkels x.


```python
[RAD] = ATAN(1) ≈ 0.7854

[GRAD] = RADGRAD(ATAN(1)) = 45° - um den TANGENTS in Grad zu erhalten.

In Kombination mit RADGRAD wird der Winkel vom Bogenmaß (RAD) in GRAD umgerechnet. GRAD = RAD * 180/PI().
```

#### __RADGRAD(x)__ ####

Konvertiert Radianten in Grad (x Radianten => Resultat in Grad).


```python
=RADGRAD(0.5)

RADGRAD rechnet einen Wert vom Bogenmaß (RAD) in GRAD um. GRAD = RAD * 180/PI().


```

#### __GRADRAD(x)__ ####

Konvertiert Grad in Radianten (x Grad => Resultat in Radianten).


```python
=GRADRAD(0.5) 

GRADRAD rechnet einen Wert in GRAD in ein Bogenmaß (RAD) um.  RAD = Grad * PI()/180.


```

#### __ASIN(x)__ ####

Arcussinus des Winkels x.


```python
[RAD] = ASIN(0.5) ≈ 0.524

[GRAD] = RADGRAD(ASIN(0.5)) = 30° - um den SINUS in Grad zu erhalten.

In Kombination mit RADGRAD wird der Winkel vom Bogenmaß (RAD) in GRAD umgerechnet. GRAD = RAD * 180/PI().
```

#### __ACOS(x)__ ####

Arcuscosinus des Winkels x.


```python
[RAD] = ACOS(0.5) ≈ 1.0472

[GRAD] = RADGRAD(ACOS(0.5)) = 60° - um den COSINUS in Grad zu erhalten.

In Kombination mit RADGRAD wird der Winkel vom Bogenmaß (RAD) in GRAD umgerechnet. GRAD = RAD * 180/PI().
```

#### __ABRUNDEN(x; [Dezimalstellen])__ ####

Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen ab.


```python
=ABRUNDEN(2.345, 2)

Rundet einen Wert auf die zweite Dezimalstelle ab. Resultat = 2.34


```

#### __AUFRUNDEN(x; Dezimalstellen)__ ####

Rundet die Zahl auf eine bestimmte Anzahl von Dezimalstellen auf.


```python
=AUFRUNDEN(2.345, 2)

Rundet einen Wert auf die zweite Dezimalstelle. Resultat = 2.35


```

#### __BETRAG(x)__ ####

Gibt den absoluten Wert (Betrag |x|) einer reellen Zahl zu deren Abstand zum Nullpunkt zurück.


```python
=BETRAG(-5)

Hierbei ist der Betrag |a| der reelen Zahl -5 den Abstand zu Null und entspricht der Strecke 5.

Beispiele: |3| = 3, |-7| = 7


```

#### __QUOTIENT(Divident; Divisor)__ ####

Berechnet den Quotienten als Ganzenzahl einer Division.


```python
=QUOTIENT(5, 2)



Gibt die Anzahl Summanden zurück, welche als Ganzzahl in die Division passen.

Hierbei wäre 5 / 2 = ⎣2.5⎦, wobei 2.5 auf die Ganzzahl 2 abgerundet wird.
```

#### __GGT(x1; x2;...; xn)__ ####

Größter gemeinsamer Teiler einer Zahlengruppe.


```python
=GGT(5, 10, 20)



Gibt den ggT der Zahlenfolge (5, 10, 20) zurück. Hierbei also 5.


```

#### __KGV(x1; x2;...; xn)__ ####

Kleinstes gemeinsames Vielfaches in verschiedenen Zahlenreihen.


```python
=KGV(3, 4, 6)

Berechnet das kleinste gemeinsame Vielfache der drei Zahlenreihen, wobei das kgV = 12 ist.


```

#### __MEDIAN(x1; x2;..; xn)__ ####

Gibt den mittleren Wert einer Zahlenfolge zurück.


```python
=MEDIAN(1, 2, 3, 4, 5, 6)

Berechnet den Median der Zahlenfolge 1,2,...,5,6 mit dem Wert 3.5


```

#### __LOGX(x; Basis)__ ####

Der Logarithmus zur angegebenen Basis von x.


```python
=LOGX(16, 2) returns 4

Die Zahl ist die positive reelle Zahl, deren Logarithmus zur Basis x Sie berechnen möchten.

Hierbei wird der Logarithmus der Zahl 16 zur Basis 2 berechnet.


```

#### __EXPONENT(x; Exponent)__ ####

Berechnet den Exponenten n zur Basis x.


```python
=EXPONENT(10, 3)

Berechnet 10 ^ 3 = 1000. Der Basis 10 und dem Exponenten 3.


```

#### __WURZELPI(x)__ ####

Gibt die Wurzel aus der mit Pi multiplizierten Zahl zurück. √(x * pi).


```python
=WURZELPI(12)

Berechnet die Wurzel von der mit PI multiplizierten Zahl zurück. √(x * pi)

Hierbei wird PI direkt vom Syntax berücksichtigt und muss in der Bedingung nicht mehr angegeben werden.


```

#### __QUADRATSUMME(x1; x2;...; xn)__ ####

Gibt die Summe der quadrierten Werten zurück.


```python
=QUADRATSUMME(0, 1, 2, 3, 4, 5)

Berechnet direkt die Summe der quadrierten Werte in der Zahlenfolge.

QUADRATSUMME(0, 1, 2, 3, 4, 5) = 55




```

#### __ZUFALLSZAHLGENERATOR(x; y)__ ####

Eine zufällige Zahl zwischen dem unteren und oberen Wert, einschließlich dem unteren, jedoch nicht dem oberen Wert.


```python
=ZUFALLSZAHLGENERATOR(10, 100)

Gibt eine zufällige reele Zahl anhand eins gegebenen Definitionsbereiches [x,y] zurück.


```

#### __ZUFALLSZAHL(x)__ ####

Eine zufällige Zahl zwischen 0 und 1, einschließlich der 0, jedoch nicht die 1.


```python
=ZUFALLSZAHL()

Gibt eine zufällige reele Zahl im Definitionsbereich [0,1] zurück.


```

#### __AUFRUNDUNG(x; [Signifikanz])__ ####

Rundet x auf auf die nächstgrössere Zahl oder – falls angegeben – auf ein Vielfaches der Signifikanz.


```python
=AUFRUNDUNG(123.123, 0.01)

Rundet eine Zahl auf, von der Null weg, auf das nächstgelegene Vielfache eines angegebenen Wertes (der sogenannten „Signifikanz“ oder Schrittweite).

Die Zahl 123,123 wird auf das nächste Vielfache von 0,01 aufgerundet (von der Null weg).

Das nächste Vielfache oberhalb von 123,123 ist 123,13.
```

#### __ABRUNDUNG(x; [Signifikanz])__ ####

Rundet x ab auf die nächstkleinere Zahl oder – falls angegeben – auf ein Vielfaches der Signifikanz.


```python
=ABRUNDUNG(123.123, 0.01)

Rundet eine Zahl ab, in Richtung Null, auf das nächstgelegene Vielfache eines angegebenen Wertes (der sogenannten „Signifikanz“ oder Schrittweite).

Die Zahl 123,123 wird auf das nächste Vielfache von 0,01 abgerundet (in Richtung Null).

Das nächste Vielfache unterhalb von 123,123 ist 123,12.
```

#### __KÜRZEN(x; [Dezimalstellen])__ ####

Kürzt x auf die angegebenen Dezimalstellen.


```python
=KÜRZEN(123.123, 2)

Kürzt den gegebenen Zahlenwert, auf eine festgelegte Dezimalstelle, ohne den Wert zu runden.


```

#### __MITTELWERT(x1; x2;...; xn)__ ####

Berechnet den Mittelwert einer gegebene Zahlenfolge


```python
=MITTELWERT(A2,A10..A12)

Berechnet den Mittelwert der gegebenen Zahlenfolge und gibt diesen zurück.


```

#### __INT(x)__ ####

Macht aus einer reelen Zahl eine natürliche Zahl.


```python
=INT(3.8)

Macht aus einer reelen Zahl eine natürliche Zahl, wobei die Dezimalstellen abgerundet werden.


```

#### __LOG10(x)__ ####

Der Logarithmus zur Basis 10 (log) von x.


```python
=LOG(100)

Die Zahl ist die positive reelle Zahl, deren Logarithmus zur Basis 10 Sie berechnen möchten.

Hierbei wird der Logarithmus der Zahl 100 zur Basis 10 berechnet.
```

#### __MAX(x1; x2;...; xn)__ ####

Gibt die größte Zahl der Zahlengruppe zurück.


```python
=MAX(1,10,100)

Gibt den grössten Zahlenwert in einer Folge zurück. Bei der Zahlenfolge 1, 10, 100 wäre dies der Wert 100.


```

#### __MIN(x1; x2;...; xn)__ ####

Gibt die kleinste Zahl der Zahlengruppe zurück.


```python
=MIN(1,10,100)

Gibt den kleinsten Zahlenwert in einer Folge zurück. Bei der Zahlenfolge 1, 10, 100 wäre dies der Wert 1.


```

#### __TAN(x)__ ####

Tangens von x.


```python
[RAD] = TAN(0.7854) ≈ 1

[GRAD] = TAN(GRADRAD(45)) = 1 - um den TANGENTS in Grad zu rechnen.

In Kombination mit GRADRAD wird der Wert von in Grad ins Bogenmaß (RAD) umgerechnet. RAD = Grad * PI()/180.
```

#### __SUM(x1; x2; ...; xn)__ ####

Summiert die Zahlen in einem Zellenbereich x1, x2, ..., xn.


```python
=SUM(1,2,3,...,10)

Summiert die Zahlen in einem Zellenbereich x1, x2, ..., xn. Resultat der Summe der Werte (1,2,3,...,10) = 55.
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



#### __Objektdaten('z-unten Grundebene')__ ####

Gibt die Höhe des untersten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Grundebene.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'z-unten Grundebene) gibt die Höhe des untersten Punktes der Bounding Box des Symbols mit Symbolnamen 'Stuhl-1' bezogen auf die Grundebene zurück.



Objektliste:

=Objektdaten)'z-unten Grundebene') gibt die Höhe des untersten Punktes der Bounding Box des Objekts bezogen auf die Grundebene zurück.


```

#### __Objektdaten('z-unten Ebenenbasishöhe')__ ####

Gibt die Höhe des untersten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Ebenenbasishöhe.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'z-unten Ebenenbasishöhe') gibt die Höhe des untersten Punktes der Bounding Box des Symbols mit Symbolnamen 'Stuhl-1' bezogen auf die Ebenenbasishöhe zurück.



Objektliste:

Objektliste:

=Objektdaten('z-unten Ebenenbasishöhe) gibt die Höhe des untersten Punktes der Bounding Box des Objekts bezogen auf die Ebenenbasishöhe zurück.


```

#### __Objektdaten('z-unten Geschossbasishöhe')__ ####

Gibt die Höhe des untersten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Geschossbasishöhe.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'z-unten Geschossbasishöhe')  gibt die Höhe des untersten Punktesder Bounding Box des Symbols mit Symbolnamen 'Stuhl-1' bezogen auf die Geschossbasishöhe zurück.



Objektliste:

=Objektdaten)'z-unten Geschossbasishöhe') gibt die Höhe des untersten Punktes der Bounding Box des Objekts bezogen auf die Geschossbasishöhe zurück.


```

#### __Objektdaten('Bounding Box Abmessung x')__ ####

Gibt die Abmessung der Bounding Box in x-Richtung des Objekts zurück, auf das der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Bounding Box Abmessung x') gibt die Länge der Bounding Box in des Symbols mit Symbolnamen 'Stuhl-1'in x-Richtung zurück.



Objektliste:

=Objektdaten('Bounding Box Abmessung x') gibt die Länge der Bounding Box des Objekts in x-Richtung zurück.


```

#### __Objektdaten('Bounding Box Abmessung y')__ ####

Gibt die Abmessung der Bounding Box in y-Richtung des Objekts zurück, auf das der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Bounding Box Abmessung y') gibt die Länge der Bounding Box in des Symbols mit Symbolnamen 'Stuhl-1'in y-Richtung zurück.



Objektliste:

=Objektdaten('Bounding Box Abmessung y') gibt die Länge der Bounding Box des Objekts in y-Richtung zurück.


```

#### __Objektdaten('Bounding Box Abmessung z')__ ####

Gibt die Abmessung der Bounding Box in z-Richtung des Objekts zurück, auf das der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Bounding Box Abmessung z') gibt die Länge der Bounding Box in des Symbols mit Symbolnamen 'Stuhl-1'in z-Richtung zurück.



Objektliste:

=Objektdaten('Bounding Box Abmessung z') gibt die Länge der Bounding Box des Objekts in z-Richtung zurück.


```

#### __Objektdaten('Beschreibung Klasse')__ ####

Beschreibung der Klasse des Objekts.



#### __Objektdaten('Klassen-Tags')__ ####

Gibt die Tags zurück, die der Klasse zugewiesen sind, auf die der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(L'Erdgeschoss', 'Klassen-Tags') gibt die Tags zurück, die mit der Klasse des Objekts verknüpft sind, das auf der Konstruktionsebene 'Erdgeschoss' liegt.



Objektliste:

=Objektdaten('Klassen-Tags') gibt die Tags zurück, die der Klasse des Objekts zugewiesen sind.
```

#### __Objektdaten('Klassifikation'; Klassifikation_Index; Parameter_Index)__ ####

Gibt die Klassifikation des Objekts zurück.

Verfügbare Optionen für Klassifikation_Index:
1 -	Primäre Klassifikation
2 -	Sekundäre Klassifikation;
3 -	Tertiäre Klassifikation;

Verfügbare Optionen für Parameter_Index:
1 -	Ist klassifiziert;
2-	Standardname;3 -	Klassifikationscode;
4 -	Klassifikationsbeschreibung;
5 -	Klassifikationssystem;
6 -	Standardquelle;
7 -	Standardedition;
8 -	Standardeditionsdatum;
9 -	Standardort;
10 -	Standardbeschreibung;


```python
Verfügbare Optionen für Parameter_Index:

	1 - Ist klassifiziert

	2 - Standard Name

	3 - Klassifikationscode

	4 - Klassifikationsbeschreibung

	5- Klassifikationssystem

	6 - Standardquelle

	7 - Standardedition

	8 - Standardeditionsdatum

	9 - Standardort

	10 - Standardbeschreibung:



Beispiele:

	Objektliste:

	=Objektdaten('Klassifikation', 1, 1)		Gibt Wahr zurück, wenn die Primäre Klassifikation für jedes Objekt in der Tabellenzeile einen Wert hat.



	=Objektdaten('Klassifikation', 1, 2)		Gibt den Namen des Regel-Sets der Primären Klassifikation zurück, die für jedes Objekt in der Tabellenzeile gesetzt ist.



	=Objektdaten('Klassifikation', 2, 5)		Gibt den Systemnamen der Sekundären Klassifikation zurück, der für jedes Objekt in der Tabellenzeile gesetzt ist.r


	=Objektdaten('Klassifikation', 3, 10)		Gibt die Standardbeschreibung der Tertiären Klassifikation zurück, die für jedes Objekt in der Tabellenzeile gesetzt ist.r


	Einzelne Zeile:

	=Objektdaten(SEL=WAHR, 'Klassifikation', 1, 1) gibt WAHR zurück, wenn die Primäre Klassifikation für das ausgewählte Objekt einen Wert hat.



	=Objektdaten(SEL=WAHR,e'Klassifikation', 1, 2) gibt den Namen des Regel-Sets der Primären Klassifikation des ausgewählten Objekts zurück.r


	=Objektdaten(SEL=WAHR, 'Klassifikation', 2, 5) gibt den Systemnamen der Sekundären Klassifikation des ausgewählten Objekts zurück. r


	=Objektdaten(SEL=WAHR, Klassifikation, 3, 10) gibt die Standardbeschreibung der Tertiären Klassifikation des ausgewählten Objekts zurück.


```

#### __Objektdaten('Schicht'; <Wert> [; <Schichtindex>])__ ####

Bei einem Objekt gibt die Funktion den angegebenen <Wert> der Schicht des Objekts mit dem angegebenen <Schichtindex> zurück, oder die Kernschicht, wenn <Schichtindex> fehlt. Wird die Funktion für eine Schicht aufgerufen, gibt sie den angegebenen <Wert> für diese Schicht zurück. Wenn der optionale <Schichtindex> hinzugefügt wird, gibt die Funktion den Schichtwert nur für Schichten zurück, die mit dem angegebenen Index übereinstimmen.

Die folgenden Werte werden unterstützt: "Name", "Funktion", "Klasse", "Klassenbezeichnung", "Klassenbeschreibung", "Dicke", "Lambda", "Wert", "Nettofläche", "Nettovolumen".

Siehe das Beispiel für weitere Details.


```python
Verfügbare Optionen für <Wert>:

	- Name

	- Funktion

	- Klasse

	- Klassenbeschreibung

	- Dicke

	- Lambda

	- U-Wert

	- Nettofläche

	- Nettovolumen



Beispiele:

	# gibt Schichtname zurück

	Objektdaten('Schicht', 'Name')			# Kernschicht

	Objekt('Schicht', 'Name', 2)		# Schicht mit Index = 2

	

	
	# gibt den Wert der Funktion der Schicht zurück

	Objektdaten('Schicht', 'Funktion')		# Kernschicht

	Objektdaten('Schicht', 'Funktion', 2)	# Schicht mit Index = 2

	

	

	# gibt Klasse der Schicht zurück

	Objektdaten('Schicht', 'Klasse')		# Kernschicht

	Objektdaten('Schicht', 'Klasse', 2)		# Schicht mit Index = 2

	

	

	# gibt Klassenbeschreibung der Schicht zurück

	Objektdaten('Schicht', 'Klassenbeschreibung')			# Kernschicht

	Objektdaten('Schicht', 'Klassenbeschreibung', 2)		# Schicht mit Index = 2

	Objektdaten('Schicht', 'Klassenbeschreibung')	# Kernschicht
	Objektdaten('Schicht', 'Klassenbeschreibung', 2)	# Schicht mit Index = 2
	
	
	# gibt Schichtdicke zurück
	Objektdaten('Schicht', 'Dicke')		# Kernschicht
	Objektdaten('Schicht', 'Dicke', 2)		# Schicht mit Index = 2

	

	

	# gibt den Lambda-Wert der Schicht zurück

	Objektdaten('Schicht', 'Lambda')			# Kernschicht
	Objektdaten('Schicht', 'Lambda', 2)		# Schicht mit Index = 2
	
	
	# gibt U-Wert der Schicht zurück

	Objektdaten('Schicht', 'U-Wert')			# Kernschicht

	Objektdaten('Schicht', 'U-Wert', 2)		# Schicht mit Index = 2

	

	

	# gibt Nettofläche der Schicht zurück

	Objektdaten('Schicht', 'Nettofläche')			# Kernschicht

	Objektdaten('Schicht', 'Nettofläche', 2)		# Schicht mit Index = 2

	

	

	# gibt Nettovolumen der Schicht zurück
	Objektdaten('Schicht', 'Nettovolumen')		# Kernschicht

	Objektdaten('Schicht', 'Nettovolumen', 2)	# Schicht mit Index = 2

	


```

#### __Objektdaten('eval schematic device'; '<Datenbank>'; '<Feldname>')__ ####

Eigenschaftswert oder verbundene Datenbank des Objekts der Stromplanung.



#### __Objektdaten('Name')__ ####

Name des Objekts. Bei einem Symbol ohne Namen wird der Name der Symboldefinitionsressource zurückgegeben.


```python
Objektliste

=Objektdaten'Allgemeiner Name')        Gibt den Namen für jedes Objekt in der Listenzeile zurück

                                Wenn das Objekt ein Symbol ist, wird der Symbolnamen zurückgegeben


Einzelne Zelle:

=Objektdaten(SEL=WAHR, 'Allgemeiner Name')    Gibt den Namen des ausgewählten Objekts zurück

                                      Wenn das Objekt ein Symbol ist, wird der Symbolnamen zurückgegeben


```

#### __Objektdaten('Einfügepunkt x')__ ####

Gibt die x-Koordinate des Einfügepunkts des Objekts zurück, auf das der Filter verweist. Der Wert ist relativ zum Benutzernullpunkt.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Einfügepunkt x') gibt die x-Koordinate des Einfügepunkts des Symbols mit Symbolnamen 'Stuhl-1' zurück. Der Wert ist relativ zum Benutzernullpunkt.



Objektliste:
=Objektdaten('Einfügepunkt x') gibt die x-Koordinate des Einfügepunkts des Objekts zurück. Der Wert ist relativ zum Benutzernullpunkt.


```

#### __Objektdaten('Einfügepunkt y')__ ####

Gibt die y-Koordinate des Einfügepunkts des Objekts zurück, auf das der Filter verweist. Der Wert ist relativ zum Benutzernullpunkt.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Einfügepunkt y') gibt die y-Koordinate des Einfügepunkts des Symbols mit Symbolnamen 'Stuhl-1' zurück. Der Wert ist relativ zum Benutzernullpunkt.



Objektliste:
=Objektdaten('Einfügepunkt y') gibt die y-Koordinate des Einfügepunkts des Objekts zurück. Der Wert ist relativ zum Benutzernullpunkt.


```

#### __Objektdaten('Einfügepunkt z')__ ####

Gibt die z-Koordinate des Einfügepunkts des Objekts zurück, auf das der Filter verweist. Der Wert ist relativ zum Benutzernullpunkt.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Einfügepunkt z') gibt die z-Koordinate des Einfügepunkts des Symbols mit Symbolnamen 'Stuhl-1' zurück. Der Wert bezieht sich auf die Grundebene.



Objektliste:
=Objektdaten('Einfügepunkt z') gibt die z-Koordinate des Einfügepunkts des Objekts zurück. Der Wert bezieht sich auf die Grundebene.


```

#### __Objektdaten('Einfügepunkt Ebenenbasishöhe')__ ####

Gibt die z-Korrdinate des Einfügepunkts des Objekts zurück. Der Wert bezieht sich auf die Ebenenbasishöhe.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Einfügepunkt z Ebene') gibt die z-Koordinate des Einfügepunkts des Symbols mit Symbolnamen 'Stuhl-1' zurück. Der Wert bezieht sich auf die Ebenenbasishöhe.



Objektliste:
=Objektdaten('Einfügepunkt z Ebene') gibt die z-Koordinate des Einfügepunkts des Objekts zurück. Der Wert bezieht sich auf die Ebenenbasishöhe.


```

#### __Objektdaten('Einfügepunkt Geschossbasishöhe')__ ####

Gibt die z-Korrdinate des Einfügepunkts des Objekts zurück. Der Wert bezieht sich auf die Geschossbasishöhe.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Einfügepunkt z Geschoss') gibt die z-Koordinate des Einfügepunkts des Symbols mit Symbolnamen 'Stuhl-1' zurück. Der Wert bezieht sich auf die Geschossbasishöhe.



Objektliste:
=Objektdaten('Einfügepunkt z Geschoss') gibt die z-Koordinate des Einfügepunkts des Objekts zurück. Der Wert bezieht sich auf die Geschossbasishöhe.


```

#### __Objektdaten(Filter; 'Teilbestand'; part_univ_name; part_index)__ ####

Name des Bauteils im Bestand von einem Objekt, das den Bestand unterstützen.



#### __Objektdaten(Filter; 'Teilbestand Param'; part_univ_name; part_index; param_index)__ ####

Wert von Objekteinstellungen eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.



#### __Objektdaten(Filter; Teilbestand quantity'; part_univ_name; part_index)__ ####

Menge eines Bauteils im Bestand von einem Objekt, das den Bestand unterstützt.



#### __Objektdaten('Beschreibung Ebene')__ ####

Beschreibung der Ebene des Objekts.



#### __Objektdaten('Ebenen-Tags')__ ####

Gibt die Tags zurück, die der Ebene des Objekts zugewiesen sind, auf die der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(L'Erdgeschoss', 'Ebenen-Tags') gibt die Tags zurück, die mit der Ebene des Objekts verknüpft sind, das auf der Konstruktionsebene 'Erdgeschoss' liegt.



Objektliste:

=Objektdaten('Ebenen-Tags') gibt die Tags, die der Ebene des Objekts zugewiesen sind.
```

#### __Objektdaten('Lastinfo'; Objekteigenschaft; [Lastindex])__ ####

Informationen der Last eines Lastobjekts. Objekteigeschaft ist 'Position', ' Last-ID', 'Verteiltes Gewicht' und 'Gesamtgewicht'. Ist kein Lastindex angegeben,wird die erste Last verwendet.



#### __Objektdaten('Objekt Variable'; variable_index)__ ####

Objektvariable des Objekts.



#### __Objektdaten('Geschossreferenzhöhentyp')__ ####

Gibt den Referenzhöhentyp zurück, der mit dem Geschoss des Objekt verknüpft ist, auf das der Filter verweist.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Geschossreferenzhöhentyp') gibt den Referenzhöhentyp zurück, der mit dem Geschoss des Symbols 'Stuhl-1' verknüpft ist. 



Objektliste:

=Objektdaten('iEinfügepunkt z Geschoss') gibt den Referenzhöhentyp zurück, der mit dem Geschoss des Objekts verknüpft ist.
```

#### __Objektdaten('Geschoss Vorangestellt/Nachgestellt')__ ####

Gibt den voran- oder nachgestellten Zusatztext zum Ebenennamen des Geschosses des Objekts.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'Geschoss Vorangestellt/Nachgestellt') gibt den Zusatztext zurück, der dem Namen des Geschosses voran- oder nachgestellt ist,  auf dem das Symbol 'Stuhl-1' liegt.



Objektliste:

Objektdaten('Einfügepunkt z Geschoss') gibt den Zusatztext zurück, der dem Namen des Geschosses voran- oder nachgestellt ist, auf dem das Objekt liegt.
```

#### __Objektdaten('oben-z Grundebene')__ ####

Gibt die Höhe des höchsten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Grundebene.


```python
Einzelne Zelle:

=Objektdaten(S='Stuhl-1', 'z-oben Grundebene') gibt die Höhe es obersten Punktes der Bounding Box des Symbols mit Namen 'Stuhl-1' bezogen auf die Grundebene zurück



Objektliste:

=Objektdaten(z-oben Grundebene) gibt die Höhe des obersten Punktes der Bounding Box des Objekts bezogen auf die Grundebene zurück.
```

#### __Objektdaten('oben-z Ebenenbasishöhe')__ ####

Gibt die Höhe des höchsten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Ebenenbasishöhe.


```python
Einzelne Zelle:

=Objekdaten(S='Stuhl-1', 'z-oben Ebenenbasishöhe') gibt die Höhe des obersten Punktes der Bounding Box des Symbols mit Symbolnamen 'Stuhl-1' bezogen auf die Ebenenbasishöhe zurück.



Objektliste:

=Objektdaten)'z-oben Ebenenbasishöhe') gibt die Höhe des obersten Punktes der Bounding Box des Objekts bezogen auf die Ebenenbasishöhe zurück.


```

#### __Objektdaten('oben-z Geschossbasishöhe')__ ####

Gibt die Höhe des höchsten Punktes der Bounding Box des Objekts zurück. Der Wert bezieht sich auf die Geschossbasishöhe.


```python
Einzelne Zelle:

=Objekdaten(S='Stuhl-1', 'z-oben Ebenenbasishöhe') gibt die Höhe des obersten Punktes der Bounding Box des Symbols mit Symbolnamen 'Stuhl-1' bezogen auf die Geschossbasishöhe zurück.



Objektliste:

=Objektdaten)'z-oben Ebenenbasishöhe') gibt die Höhe des obersten Punktes der Bounding Box des Objekts bezogen auf die Geschossbasishöhe zurück.


```

#### __Objektdaten('Trim-Höhe')__ ####

Die Höhe des Rigging-Objekts wie in der Infopalette angezeigt.



#### __Objektdaten('Universal_Wert'; Format_Name; Feld_Name; [Ist Format])__ ####

Gibt den universellen Wert des angegebenen Feldes des Datensatzes oder des Formats zurück, wenn der optionale Parameter Wahr ist. Es funktioniert mit dem parametrischen Format, wenn Format_Name leer ist. Ergibt Ungültig (N/A), wenn das Objekt nicht mit dem Datensatz verknüpft ist oder das Format nicht existiert.


```python
Objektliste:

=Objektdaten('Allgemeiner Wert', 'MeineDatenbank-1', 'Daten')        Gibt für jedes Objekt in der Datenbankzeile das 'Daten'-Feld der verknüpften Datenbank 'MeineDatenbank-1' zurück. Gibt N/A zurück, wenn Datenbank oder Feld nicht vorhanden sind.

=Objektdaten('Allgemeiner Wert', 'MeineDatenbank-1', 'Daten', Wahr)  Gibt für jedes Objekt in der Datenbankzeile das Feld 'Daten' der verknüpften Datenbank 'MeineDatenbank-1' zurück. Gibt N/A zurück, wenn Datenbank oder Feld nicht vorhanden sind.

=Objektdaten('Allgemeiner Wert', '', 'Höhe')            Gibt den Wert des Feldes 'Höhe' für jedes Intelligente Objekt der Datenbankzeile zurück. Gibt N/A zurück, wenn das Feld nicht vorhanden oder das Objekt kein Intelligentes Objekt ist.

=Objektdaten('Allgemeiner Wert', '', 'Höhe', WAHR)      Gibt den Standardwert des Feldes 'Höhe' für jedes Intelligente Objekt in der Datenbankzeile  zurück. Gibt N/A zurück, wenn das Feld nicht vorhanden oder das Objekt kein Intelligentes Objekt ist.



Einzelne Zelle:

=Objektdaten(t=Wand, 'Allgemeiner Wert', 'MeineDatenbank-1', 'Daten')        Gibt das Feld 'Daten' für die verknüpfte Datenbank 'MeineDatenbank-1' für die Wand zurück. Gibt N/A zurück, wenn Datenbank oder Feld nicht vorhanden sind.
=Objektdaten(t=Wand, 'Allgemeiner Wert', 'MeineDatenbank-1', 'Daten', Wahr)  Gibt das Feld 'Daten' für die verknüpfte Datenbank 'MeineDatenbank-1' für die Wand zurück. Gibt N/A zurück, wenn Datenbank oder Feld nicht vorhanden sind.

=Objektdaten(PON='Tür', 'Allgemeiner Wert', '', 'Höhe')        Gibt das Feld 'höhe' des Intelligenten Objekts 'Tür' zurück. Gibt N/A zurück, wenn das Feld nicht vorhanden oder das Objekt kein Intelligentes Objekt ist.
=Objektdaten(PON='Tür', 'Allgemeiner Wert', '', 'Höhe', Wahr)  Gibt den Standardwert des Feldes 'Höhe' des Intelligenten Objekts zurück. Gibt N/A zurück, wenn das Feld nicht vorhanden oder das Objekt kein Intelligentes Objekt ist.


```

#### __Objekttyp()__ ####

ID-Nummer des Objekttyps.


```python
Objektliste:

=OBJEKTTYP

Gibt die Gibt die Objekt-ID z.B. 68 (Wand) des gefilterten Objektes zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBJEKTTYP(SEL=WAHR)

Filtert mit SEL die Objekt-ID des aktiven Objektes in der Zeichnung.

SEL = Aktive Selektion (selection status)
```

#### __Breite([optionale Parameter])__ ####

Breite (Delta x) von Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=BREITE

Gibt die Breite (Delta x) der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=BREITE((T = RECHTECK) & (C = 'Keine'))

Filtert nach dem Objekttyp 'RECHTECK' und der Klasse 'Keine' und gibt deren Breite zurück.

T = Objekttyp

C = Klasse


```

#### __Höhe([optionale Parameter])__ ####

Gibt das Delta y (Höhe) von Objekten zurück. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück. Die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=Höhe gibt die Höhe (Delta y) für jedes Objekt zurück.



Einzelne Zelle:

Höhe (SEL=WAHR) gibt den Wert der kombinierte Höhe (Delta y) der ausgewählten Objekte in der Zeichnung.


```

#### __Zählen([optionale Parameter])__ ####

Anzahl von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=ANZAHL

Gibt die Anzahl der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.



einzelne Zelle:

=ANZAHL((T = WAND) & (WST = 'WAA_XXX_480_TRA_2SM_D'))

Filtert nach dem Objekttyp 'WAND' und dem Wandstil 'WAA_XXX_480_TRA_2SM_D' und dessen Anzahl zurück.

T = Objekttyp

WST = Wandstil



Die Funktion ANZAHL lässt sich auch mit den Filtern SEL (selection status) und VSEL (visible selection status) nutzen.

Wobei SEL die Anzahl aktiver Objekte, wie der Status in der OIP zählt. =COUNT(SEL = WAHR)

Hingegen VSEL zählt auch Objekte in einer Gruppe mit. =COUNT(VSEL = WAHR)
```

#### __Anzahl('Unterobjekte'; [Unterobjektname])__ ####

Die Anzahl der Unterobjekte in einem intelligenten Objekt. Wird ein Unterobjektname angegeben, werden nur Unterobjekte mit diesem Namen gezählt. Wenn der Unterobjektname keinem Unterobjekt entspricht, wird er als Eigenschaft (Parameter) behandelt.



#### __Winkel()__ ####

Winkel von Geraden und Wänden, Innenwinkel von Kreisbögen (in Grad), Neigungswinkel von Dachflächen, Profilstützen und Böden (in Grad).


```python
Objektliste:

=WINKEL

Gibt den Winkel der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.



einzelne Zelle:

=WINKEL((T = WAND)&(C = 'KEINE'))

Filtert nach dem Objekttyp 'WAND' und der Klasse 'Keine' und gibt der Winkel deren Objekte zurück.

In der Regel wird die Summe aller Objekte zurückgegeben.

T = Objekttyp

C = Klasse
```

#### __Gespiegelt()__ ####

Gibt 1 zurück, wenn das Objekt gespiegelt ist, andernfalls wird 0 zurückgegeben.


```python
Objektliste:

=GESPIEGELT

Gibt den Wert 1 = 'WAHR' zurück, wenn das Objekt gespiegelt wurde, ansonsten 0 = 'FALSCH'.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=GESPIEGELT((SEL=WAHR))

Gibt booleschen Status (1/0) vom aktiven Objekt zurück, obe dieses gespiegelt ist.

SEL = Aktive Selektion (selection status)
```

#### __xKoordinate()__ ####

x-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Objektliste:

=XKOORDINATE

Gibt die X-Koordinate von Objekten zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=XKOORDINATE((SEL=WAHR))

Gibt die X-Koordinate vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __yKoordinate()__ ####

y-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Objektliste:

=YKOORDINATE

Gibt die y-Koordinate von Objekten zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=YKOORDINATE((SEL=WAHR))

Gibt die Y-Koordinate vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __zKoordinate()__ ####

z-Wert eines Objektes relativ zum Benutzernullpunkt.


```python
Objektliste:

=ZKOORDINATE

Gibt die Z-Koordinate von Objekten zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=ZKOORDINATE((SEL=WAHR))

Gibt die Z-Koordinate vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __Fläche()__ ####

Gesamtfläche von Objekten in der Zeichnung. Die optionalen Parameter geben spezifische Werte für bestimmte Objekte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=FLÄCHE

Gibt die Fläche der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FLÄCHE((T = RECHTECK) & (C = 'Keine'))

Filtert nach dem Objekttyp 'RECHTECK' und der Klasse 'Keine' und gibt deren Fläche zurück.

T = Objekttyp

C = Klasse




```

#### __UnterKante()__ ####

Am weitesten unten liegender Punkt (kleinster y-Wert) von Objekten in der Zeichnung.


```python
Objektliste:

=UNTERKANTE

Gibt die untere Kante der Boundingbox vom Objekt auf der Y-Achse zurück. 

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=UNTERKANTE((SEL=WAHR))

Gibt die untere Kante der Boundingbox vom Objekt auf der Y-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __OberKante()__ ####

Am weitesten oben liegender Punkt (größter y-Wert) von Objekten in der Zeichnung.


```python
Objektliste:

=OBERKANTE

Gibt die obere Kante der Boundingbox vom Objekt auf der Y-Achse zurück. 

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBERKANTE((SEL=WAHR))

Gibt die obere Kante der Boundingbox vom Objekt auf der Y-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __LinkeKante()__ ####

Am weitesten links liegender Punkt (kleinster x-Wert) von Objekten in der Zeichnung.


```python
Objektliste:

=LinkeKanteKANTE

Gibt die linke Kante der Boundingbox vom Objekt auf der X-Achse zurück. 

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=LINKEKANTE((SEL=WAHR))

Gibt die linke Kante der Boundingbox vom Objekt auf der X-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __RechteKante()__ ####

Am weitesten rechts liegender Punkt (größter x-Wert) von Objekten in der Zeichnung.


```python
Objektliste:

=RECHTEKANTE

Gibt die rechte Kante der Boundingbox vom Objekt auf der X-Achse zurück. 

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=RECHTEKANTE(SEL=WAHR)

Gibt die rechte Kante der Boundingbox vom Objekt auf der X-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __Umfang([optionale Parameter])__ ####

Umfang des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=UMFANG

Gibt den Umfang der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=UMFANG((T = RECHTECK) & (C = 'Keine'))

Filtert nach dem Objekttyp 'RECHTECK' und der Klasse 'Keine' und gibt deren Länge zurück.

T = Objekttyp

C = Klasse


```

#### __Länge([optionale Parameter])__ ####

Länge von Geraden und Wänden in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=LÄNGE

Gibt die Länge der Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 

Eher bei linearen Geometrien (Line, Polygon, Polyline) anwendbar. Für Kantenlängen von Flächen, wäre eher 'BREITE' und 'HÖHE' anzuwenden.



einzelne Zelle:

=LÄNGE((T = POLYGON) & (C = 'Keine'))

Filtert nach dem Objekttyp 'POLYGON' und der Klasse 'Keine' und gibt deren Länge zurück.

T = Objekttyp

C = Klasse


```

#### __xMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in x-Richtung.


```python
Objektliste:

=XMITTE

Gibt die Mitte auf der X-Achse von Objekten zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=XMITTE((SEL=WAHR))

Gibt die Mitte auf der X-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __yMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in y-Richtung.


```python
Objektliste:

=YMITTE

Gibt die Mitte auf der Y-Achse von Objekten zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=YMITTE((SEL=WAHR))

Gibt die Mitte auf der Y-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __zMitte()__ ####

Mittelpunkt von Objekten in der Zeichnung in z-Richtung.


```python
Objektliste:

=ZMITTE

Gibt die Mitte auf der Z-Achse von Objekten zurück

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=ZMITTE((SEL=WAHR))

Gibt die Mitte auf der Z-Achse vom aktiven Objekt zurück.

SEL = Aktive Selektion (selection status)
```

#### __Oberfläche([optionale Parameter])__ ####

Oberfläche von 3D-Objekten in der Zeichnung. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=OBERFÄCHE

Gibt die Oberfläche von 3D-Objekte in der Objektliste zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBERFLÄCHE((ST = HALBKUGEL) & (C = 'Keine'))

Filtert nach dem Objekttyp 'HALBKUGEL' und der Klasse 'Keine' und gibt deren Oberfläche zurück.

ST = Objekttyp (Unterobjekt)

C = Klasse


```

#### __Volumenn([optionale Parameter])__ ####

Volumen des Objekts. Die optionalen Parameter geben für bestimmte Objekte spezifische Werte zurück und die verfügbaren Optionen werden separat aufgeführt.


```python
Objektliste:

=VOLUMEN

Gibt das Volumen eines Objektes zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=VOLUMEN(SEL=WAHR)

Gibt das Volumen des aktiven Objektes in der Zeichnung zurück

SEL = Aktive Selektion (selection status)


```

#### __Grafik()__ ####

Grafische Abbildung von Objekten in der Zeichnung.


```python
Objektliste:

=GRAFIK

Gibt eine grafische Abbildung des Objektes in der Zeichnung zurück.

Diese kann über die Tabelle im Reiter 'Format' > 'Bildformat' weiter definiert werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.
```

#### __ObjU-Wert()__ ####

U-Wert der Objekte.


```python
Objektliste:

=ObjR_Wert gibt den U-Wert für jede Wand, Dach, Dachfläche, Boden/Decke, Tür und Fenster zurück.



Einzelne Zelle:

ObjU_Wert(n) gibt den U-Wert des Objekts mit dem angegebenen Namen zurück, z.B.

ObjU_Wert(n='Wand-1') gibt den R-Wert der Wand mit Namen Wand-1 zurück.


```

#### __ObjR-Wert()__ ####

R-Wert der Objekte.


```python
Objektliste:

=ObjR_Wert gibt den R-Wert für jede Wand, Dach, Dachfläche, Boden/Decke, Tür und Fenster zurück.



Einzelne Zelle:

ObjR_Wert(n) gibt den R-Wert des Objekts mit dem angegebenen Namen zurück, z.B.

ObjR_Wert(n='Wand-1') gibt den R-Wert der Wand mit Namen Wand-1 zurück.


```

#### __ObjInEnergos()__ ####

Gibt den Wert 1 zurück, wenn das Objekt in den Energieberechnungen berücksichtigt wird. Andernfalls wird der Wert 0 Zurückgegeben.


```python
Objektliste:

=OBJINENERGOS

Gibt den booleschen Wert (1 = 'WAHR'/0 = 'FALSCH') zurück, ob ein Bauteil für dei Energos Berechnungen berücksichtigt wird.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBJINENERGOS((T=WAND) & (SEL=WAHR))

Gibt den booleschen Wert (1='WAHR'/0='FALSCH') zurück, ob ein Bauteil für dei Energos Berechnungen berücksichtigt wird, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Objektstilname()__ ####

Gibt den Stilnamen zurück, den das Intelligente Objekts verwendet,


```python
Objektliste:

=STILNAME

Listet die Stilnamen des gefilterten Objektes auf.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=STILNAME((PON='Door CW') & (SEL=WAHR))

Gibt den Stilnamen einer aktiven Tür in der Zeichnung zurück.

PON = Unterobjekt PlugIn-Objekt

SEL = Aktive Selektion (selection status)
```

#### __Ebene()__ ####

Name der Ebene der Objekt.


```python
Objektliste:

=EBENE

Gibt die zugehörige Konstruktionsebene des gefilterten Objektes zurück. Kann auch mit =L (Layer) definiert werden

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=EBENE(SEL=WAHR)

Filtert mit SEL die Objektnamen (z.B. Wand) des aktiven Objektes in der Zeichnung.

SEL = Aktive Selektion (selection status)Objektliste:


```

#### __Klasse()__ ####

Name der Klasse der Objekte.


```python
Objektliste:

=KLASSE

Listet alle Klassennamen auf, welche von einem Objekt verwendet werden. Kann auch mit =C (Class) definiert werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=KLASSE(T=RECHTECK)

Listet die Klassennamen auf, welche bei Rechtecken verwendet werden.

T = Objekttyp
```

#### __ObjektTypName()__ ####

Name der Objekttypen.


```python
Objektliste:

=OBJEKTTYP

Gibt die Gibt die Objektnamen (z.B. Wand) des gefilterten Objektes zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBJEKTTYP(SEL=WAHR)

Filtert mit SEL die Objektnamen (z.B. Wand) des aktiven Objektes in der Zeichnung.

SEL = Aktive Selektion (selection status)
```

#### __Name()__ ####

Name der Objekte.


```python
Objektliste:

=Name

Gibt den Namen in der Infopalette des Objektes zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBJEKTTYP(SEL=WAHR)

Gibt den Namen in der Infopalette des aktiven Objektes in der Zeichnung zurück.

SEL = Aktive Selektion (selection status)




```

#### __Geschoss()__ ####

Name des Geschosses, auf welchem die Objekte liegen.


```python
Objektliste:

=Geschoss gibt den Namen des Geschosses für jedes Objekt zurück.



Einzelne Zelle:

Geschoss (SEL=WAHR) gibt den Namen des Geschosses der ausgewählten Objekte in der Zeichnung zurück.


```

#### __Mosaikfüllung()__ ####

Name des Mosaiks, mit dem die Objekte gefüllt sind.


```python
Objektliste:

=MOSAIKFÜLLUNG

Listet alle Namen der Verläufe auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MOSAIKFÜLLUNG(T=RECHTECK)

Listet den Namen der Verläufe auf, welche bei Rechtecken verwendet werden.

T = Objekttyp


```

#### __Schraffurfüllung()__ ####

Name der Schraffur, mit der die Objekte gefüllt sind.


```python
Objektliste:

=SCHRAFFURFÜLLUNG

Listet alle Namen der Schraffuren auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHRAFFURFÜLLUNG(T=RECHTECK)

Listet den Namen der Schraffuren auf, welche bei Rechtecken verwendet werden.

T = Objekttyp


```

#### __Verlauffüllung()__ ####

Name des Verlaufs, mit dem die Objekte gefüllt sind.


```python
Objektliste:

=VERLAUFFÜLLUNG

Listet alle Namen der Verläufe auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=VERLAUFFÜLLUNG(T=RECHTECK)

Listet den Namen der Verläufe auf, welche bei Rechtecken verwendet werden.

T = Objekttyp


```

#### __Objekttextur()__ ####

Name der Textur, das den Objekten zugewiesen ist.


```python
Objektliste:

=OBJEKTTEXTUR

Listet alle Namen der Texturen auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=OBJEKTTEXTUR(SEL=WAHR)

Listet den Namen der Textur, des aktiven Objektes auf.

SEL = Selektierte Auswahl (Selected status)
```

#### __Skizzenstil()__ ####

Name des Skizzenstils der Objekte.


```python
Objektliste:

=SKIZZENSTIL

Listet den aktiven Skizzenstil in der Zeichnung auf.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SKIZZENSTIL(SEL=WAHR)

Listet den aktuellen Skizzenstil, des aktiven Objektes auf.

SEL = Selektierte Auswahl (Selected status)
```

#### __Linienart()__ ####

Name der Linienart der Objekte.


```python
Objektliste:

=LINIENART

Listet die Linienarten auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=LINIENART(T=POLYGON)

Listet die Linienart auf, welche bei Polygonen verwendet werden.

T = Objekttyp
```

#### __Bildfüllung()__ ####

Name der Bildfüllung der Objekte.


```python
Objektliste:

=BILDFÜLLUNG

Listet alle Namen der Bildfüllungen auf, welche von einem Objekt verwendet werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=BILDFÜLLUNG(T=RECHTECK)

Listet den Namen der Bildfüllungen auf, welche bei Rechtecken verwendet werden.

T = Objekttyp


```

#### __GetCOBieSource(Tabellenname.Spaltenname.Land.Version)__ ####

Gibt die Datenquelle einer COBie-Eigenschaft (COBie property) eines Objekts zurück.


```python
=GETCOBIESOURCE ('space.floorname')r
Gibt die Datenquelle des Wertes FloorName für Objekte zurück, deren COBie-Eigenschaft Space ist.r

```

#### __GetCOBieProperty(Tabellenname.Spaltenname.Land.Version)__ ####

Gibt den Wert einer COBie-Eigenschaft (COBie property) zurück.


```python
=GETCOBIEPROPERTY ('space.floorname')r
Gibt den Wert für FloorName für Objekte zurück, deren COBie-Eigenschaft Space ist.r

```

#### __Symbolname()__ ####

Name des Symbols.


```python
Objektliste:

=SYMBOLNAME

Listet alle Namen der in der Zeichnung eingestzten Symbole auf.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SYMBOLNAME(SEL=WAHR)

Listet alle Namen der in der Zeichnung selektierten Symbole auf.

SEL = Selektierte Auswahl (Selected status) 


```

#### __DatenstempelFeld(Feldname)__ ####

Gibt den Wert des angegebenen Feldes für die Datenstempelobjekte zurück. Feldname ist der Name des Feldes im Datenstempellayout.


```python
Objektliste:

=DATENSTEMPELFELD('WS')

Liest das angegebene Datenfeld des Datenstempels 'WS' aus und gibt den Inhalt zurück. Der Feldname ist der Name des Feldes im Datenstempellayout.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=DATENSTEMPELFELD(SEL=WAHR, 'WS')

Liest das Datenfeld des Datenstempels 'WS' aus, wenn diese selektiert sind und gibt den Inhalt zurück.

SEL = Selektierte Auswahl (Selected status)

WS = Datenstempel 'Wandstil' (Default Content) 


```

#### __Grafik_Ansichtsber(Ansichtsbereichsname)__ ####

Erstellt ein Bild der Objekte mit dem Farbschema des angegebenen Ansichtsbereichs.


```python
Objektliste:

=GRAFIK_ANSICHTSBER('1/Lay-1')

Gibt eine grafische Abildung des Objektes aus dem gegebenen Ansichtsbereichen zurück. Wobei die Darstellung einer Datenvisualisierung auch berücksichtigt wird.

Diese kann über die Tabelle im Reiter 'Format' > 'Bildformat' weiter definiert werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.
```

#### __Grafik_Datenvis(DatenvisName)__ ####

Erstellt ein Bild des Objekts mit dem Farbschema des angegebenen Ansichtsbereichs.


```python
Objektliste:

=GRAFIK_DATENVIS('Allgemein - Objekte mit IFC-Daten')

Gibt eine grafische Abbildung des Zustandes vom Objekt innerhalb der gegebenen Datenvisualiserung zurück.

Diese kann über die Tabelle im Reiter 'Format' > 'Bildformat' weiter definiert werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.
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
Objektliste:

=UNTEROBJEKTNAME

Gibt die Namen der Unterobjekte zurück. Gibt den Namen des Objekttyps zurück, wenn das Objekt kein Unterobjekt ist.

Damit gelangt man an spezifische Eigenschaften eines Unterobjektes. Als Beispiel:

=IF((UNTEROBJEKTNAME='Schicht'), GEWICHT('gross'), '')

Das Gewicht (Brutto) einer Wandschicht.
```

#### __Füllvordergrundfarbe()__ ####

Die Vordergrundfarbe der Füllung des Objekts, auf die der Filter verweist.


```python
Objektliste:

=FÜLLVORDERGRUNDFARBE

Listet alle Namen der Vordergrundfarben auf, welche von einem Objekt verwendet werden. Wichtig, es wird den Namen der Farbe bezogen. Ist kein Namen vorhanden wird ein leerer String zurückgegeben.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FÜLLVORDERGRUNDFARBE(T=RECHTECK)

Listet den Namen der Vordergrundfarben auf, welche bei Rechtecken verwendet werden.

T = Objekttyp
```

#### __Füllhintergrundfarbe()__ ####

Die Hintergrundfarbe der Füllung des Objekts.


```python
Objektliste:

=FÜLLHINTERGRUNDFARBE

Listet alle Namen der Hintergrundfarben auf, welche von einem Objekt verwendet werden. Wichtig, es wird den Namen der Farbe bezogen. Ist kein Namen vorhanden wird ein leerer String zurückgegeben.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=FÜLLHINTERGRUNDFARBE(T=RECHTECK)

Listet den Namen der Hintergrundfarben auf, welche bei Rechtecken verwendet werden.

T = Objekttyp
```

#### __Stiftvordergrfarbe()__ ####

Die Vordergrundfarbe des Stifts des Objekts.


```python
Objektliste:

=STIFTVORDERGRFARBE

Listet alle Namen der Hintergrundfarben auf, welche von einem Objekt verwendet werden. Wichtig, es wird den Namen der Farbe bezogen. Ist kein Namen vorhanden wird ein leerer String zurückgegeben.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=STIFTVORDERGRFARBE(T=RECHTECK)

Listet den Namen der Hintergrundfarben auf, welche bei Rechtecken verwendet werden.

T = Objekttyp
```

#### __Stifthintergrfarbe()__ ####

Die Hintergrundfarbe des Stifts des Objekts.


```python
Objektliste:

=STIFTHINTERGRFARBE

Listet alle Namen der Vordergrundfarben auf, welche von einem Objekt verwendet werden. Wichtig, es wird den Namen der Farbe bezogen. Ist kein Namen vorhanden wird ein leerer String zurückgegeben.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=STIFTHINTERGRFARBE(T=RECHTECK)

Listet den Namen der Vordergrundfarben auf, welche bei Rechtecken verwendet werden.

T = Objekttyp


```

#### __HatFüllung()__ ####

Gibt 1 zurück, wenn das Objekt eine Füllung hat. Andernfalls wird 0 zurückgegeben.


```python
=HATFÜLLUNG

Prüft, ob Objekte eine Füllung haben. Gibt 1 für 'WAHR' und 0 für 'FALSCH' zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 

Kann alternativ auch mit

=IF(HATFÜLLUNG=1, 'hat eine Füllung', 'hat keine Füllung')

erweitert werden. Statt 1 oder 0 wird 'hat eine Füllung' oder 'hat keine Füllung' zurückgegeben.



einzelne Zelle:

=HATFÜLLUNG(T=RECHTECK)

Prüft, ob Rechtecke eine Füllung haben. Gibt 1 für 'WAHR' und 0 für 'FALSCH' zurück.

T = Objekttyp


```

#### __AnsichtsberStilname()__ ####

Der Name des vom Objekt verwendeten Ansichtsbereichstils


```python
Objektliste:

=ANSICHTSBEREICHSTIL

Gibt die Stilnamen der vorhandenen Ansichtsbereichen zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=ANSICHTSBEREICHSTIL(N = '1/Lay-1')

Filtert den Ansichtsbereich mit dem Namen '1/Lay-1' und gibt den Titel des Ansichtsbereichstils zurück.

N = Objektname (OIP)


```

#### __Stilname()__ ####

Gibt den Namen des Stils zurück, der vom Objekt verwendet wird.


```python
Objektliste:

=Stilname gibt den Namen des Stils für das Objekt zurück.



Einzelne Zelle

Stilname(T='Wand') gibt den Namen des Stil für das Objekt, dessen Objekttyp Wand ist.


```

#### __IstGestilt()__ ####

Gibt WAHR zurück, wenn das Objekt gestilt ist, andernfalls FALSCH.


```python
Database cell:
=IsStyled returns TRUE if the object is styled, otherwise returns FALSE

Spreadsheet cell:
=IsStyled(PON='Space') returns TRUE if the object of plug-in type space is styled, otherwise returns FALSE

```

#### __Füllungstyp()__ ####

Gibt den Füllungstyp des Objekts zurück.


```python
Objektliste:

=Füllungstyp gibt den Füllungstyp für jedes Objekt zurück.



Einzelne Zelle:

Füllungstyp (SEL=WAHR) gibt den Füllungstyp der ausgewählten Objekte in der Zeichnung zurück.


```

#### __Stifttyp()__ ####

Gibt den Stifttyp des Objekts zurück.


```python
Objektliste:

=Stifttyp gibt den Stifttyp für jedes Objekt zurück.



Einzelne Zelle:

Stifttyp (SEL=WAHR) gibt den Stifttyp der ausgewählten Objekte in der Zeichnung zurück.


```

### Auslaufende Funktionen


#### __Schichtfläche(Index)__ ####

Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.


```python
Objektliste:

=SCHICHTFLÄCHE(1)

Gibt die Nettofläche (Länge x Höhe) der Schicht im Index [1] (von Innen) abzüglich von Wandöffnungen zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_KLASSE((T=WAND) & (SEL=WAHR), 1)

Gibt die Nettofläche der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtvolumen(Index)__ ####

Fläche von Schichten, abzüglich von Löchern die sich in dem 3D-Objekt befinden.


```python
Objektliste:

=SCHICHTVOLUMEN(1)

Gibt das Volumen der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTVOLUMEN((T=WAND) & (SEL=WAHR), 1)

Gibt das Volumen der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __Schichtname(Index)__ ####

Name einer Schicht.


```python
Objektliste:

=SCHICHTNAME(1)

Gibt den Schichtname der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTNAME((T=WAND) & (SEL=WAHR), 1)

Gibt den Schichtname der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __IFCEigenschaft(Eigenschaftenset.Eigenschaft)__ ####

Eigenschaft (property field) von IFC-Daten (instance). Beispiel: IFC-Eigenschaft(‘IfcWallStandardCase.Description’).


```python
Objektliste:

=IFCEIGENSCHAFT('pset_wallcommon.isexternal')

Gibt den Wert der Eigenschaft (property field) 'IsExternal' (IstTragend) aus dem Eigenschaftenset (property set) 'WallCommon' zurück. Der Wert kann als ZAHL, STRING oder BOOLEAN zurückgegeben werden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=IFCEIGENSCHAFT((T=WAND) & (SEL=WAHR), 'pset_wallcommon.isexternal')

Gibt den Wert der Eigenschaft 'IsExternal' (IstTragend) aus dem Eigenschaftenset 'WallCommon' zurück, wenn das aktive Objekt eine Wand ist.

Optional: Im Filter kann die Klasse des Pfostens verwendet werden, um zusätzlich zu filtern.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtLambda(Index)__ ####

Lambda-Wert der Schicht.


```python
Objektliste:

=SCHICHTLAMBDA(1)

Gibt den Lambdawert der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTLAMBDA((T=WAND) & (SEL=WAHR), 1)

Gibt den Lambda der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtU-Wert(Index)__ ####

U-Wert der Schicht.


```python
Objektliste:

=SCHICHTU_WERT(1)

Gibt den U-Wert der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTU_WERT((T=WAND) & (SEL=WAHR), 1)

Gibt den U-Wert der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __SchichtR-Wert(Index)__ ####

R-Wert der Schicht.


```python
Objektliste:

=SCHICHTR_WERT(1)

Gibt den R-Wert der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTR_WERT((T=WAND) & (SEL=WAHR), 1)

Gibt den R-Wert der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __SchichtDicke(Index)__ ####

Die Dicke der Schicht.


```python
Objektliste:

=SCHICHTDICKE(1)

Gibt die Dicke der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTDICKE((T=WAND) & (SEL=WAHR), 1)

Gibt die Dicke der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __Schichtfläche_Klasse(Klasse)__ ####

Fläche der von der Klasse bestimmten Schichten, abzüglich aller Öffnungen. Liegen mehrere Schichten in der Klasse, werden die Flächen addiert.


```python
Objektliste:

=SCHICHTFLÄCHE_KLASSE('Keine')

Gibt die Nettofläche (Länge x Höhe) einer Schicht (Wand, Boden/Decke, Dach etc.), abzüglich aller Öffnungen, anhand der Klasse zurück. Ist die Klasse bei mehreren Schichten vergeben, so wird die Fläche addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTFLÄCHE_KLASSE((T=WAND) & (SEL=WAHR), 'Keine')

Gibt die Nettofläche der Schicht zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __SchichtLambda_Klasse(Klasse)__ ####

Lambda-Wert vonderKlasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Wert der ersten gefundenen Schicht angezeigt.


```python
Objektliste:

=SCHICHTLAMBDA_KLASSE('Keine')

Gibt den Lambdawert einer Schicht (Wand, Boden/Decke, Dach etc.) anhand der Klasse zurück. Haben mehrere Schichten den gleichen Namen, wird der Wert der ersten Schicht angezeigt, die gefunden wird.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTLAMBDA_KLASSE((T=WAND) & (SEL=WAHR), 'Keine')

Gibt den Lambdawert der Schicht zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtname_Klasse(Klasse)__ ####

Der Name von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, wird der Name der ersten gefundenen Schicht angezeigt.


```python
Objektliste:

=SCHICHTNAME_KLASSE('Keine')

Gibt den Namen einer Schicht (Wand, Boden/Decke, Dach etc.) anhand der Klasse zurück. Liegen mehrere Schichten in der Klasse, wird der Name der ersten gefundenen Schicht angezeigt.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTNAME_KLASSE((T=WAND) & (SEL=WAHR), 'Keine')

Gibt der Namen der Schicht zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtRWert_Klasse(Klasse)__ ####

Der R-Wert einer von der Klasse bestimmten Schicht. Liegen mehrere Schichten in der Klasse, werden die R-Werte der Schichten addiert.


```python
Objektliste:

=SCHICHTUWERT_KLASSE('Keine')

Gibt den R-Wert der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand der Klasse der Schicht zurück. Ist die Klasse bei mehreren Schichten vergeben, so wird der R-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_KLASSE((T=WAND) & (SEL=WAHR), 'Klasse')

Gibt den R-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtdicke_Klasse(Klasse)__ ####

Dicke der von der Klasse bestimmen Schicht. Liegen mehrere Schichten in der Klasse, werden die Dicken addiert.


```python
Objektliste:

=SCHICHTDICKE_KLASSE('Keine')

Gibt die Dicke einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand der Klasse zurück. Ist die Klasse bei mehreren Schichten vergeben, so wird die Dicke addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTDICKE_MAT((T=WAND) & (SEL=WAHR), 'Keine')

Gibt die Dicke der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtUWert_Klasse(Klasse)__ ####

Der U-Wert der von der Klasse bestimmter Schicht. Liegen mehrere Schichten in der Klasse, werden die U-Werte der Schichten addiert.


```python
Objektliste:

=SCHICHTUWERT_KLASSE('Keine')

Gibt den U-Wert der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand der Klasse der Schicht zurück. Ist die Klasse bei mehreren Schichten vergeben, so wird der U-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_KLASSE((T=WAND) & (SEL=WAHR), 'Klasse')

Gibt den U-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtvol_Klasse(Klasse)__ ####

Volumen der Schichten, die in der angegebenen Klasse liegen. Liegen mehrere Schichten in der Klasse, werden die Volumen addiert.


```python
Objektliste:

=SCHICHTVOL_KLASSE('keine')

Gibt das Volumen der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand der Klasse der Schicht zurück. Ist die Klasse bei mehreren Schichten vergeben, so wird das Volumen addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTVOL_KLASSE((T=WAND) & (SEL=WAHR), 'keine')

Gibt das Volumen der Schicht(en) zurück, wenn das aktive Objekt eine Wand in der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtfläche_Name(Name)__ ####

Fläche der vom Namen bestimmen Schicht, abzüglich aller Öffnungen. Haben mehrere Schichten den gleichen Namen, werden die Flächen addiert.


```python
Objektliste:

=SCHICHTFLÄCHE_NAME('Mauerwerk')

Gibt die Nettofläche (Länge x Höhe) einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Schichtnamen zurück. Ist der Namen bei mehreren Schichten vergeben, so wird die Fläche addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTFLÄCHE_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt die Nettofläche der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Namen 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __SchichtLambda_Name(Name)__ ####

Lambda-Wert einer Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, wird der Wert der ersten Schicht angezeigt, die gefunden wird.


```python
Objektliste:

=SCHICHTLAMBDA_NAME('Mauerwerk')

Gibt den Lambdawert einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Schichtnamens zurück. Haben mehrere Schichten den gleichen Namen, wird der Wert der ersten Schicht angezeigt, die gefunden wird.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTLAMBDA_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt den Lambdawert der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Namen 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtklasse_Name(Name)__ ####

Die Klasse der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, wird die Klasse der ersten gefundenen Schicht angezeigt.


```python
Objektliste:

=SCHICHTKLASSE_NAME('Mauerwerk')

Gibt die Klasse einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Schichtnamens zurück. Haben mehrere Schichten den gleichen Namen, wird die Klasse der ersten gefundenen Schicht angezeigt.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTKLASSE_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt die Klasse der Schicht zurück, wenn das aktive Objekt eine Wand mit der Schichtname 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtRWert_Name(Name)__ ####

Der R-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die R-Werte der Schichten addiert.


```python
Objektliste:

=SCHICHTRWERT_NAME('Mauerwerk')

Gibt den R-Wert einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Schichtnames zurück. Ist der Namen bei mehreren Schichten vergeben, so wird der R-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTRWERT_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt den R-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Schicht 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtdicke_Name(Name)__ ####

Dicke der Schicht, die den angegebenen Namen hat. Haben mehrere Schichten den gleichen Namen, werden die Dicken addiert.


```python
Objektliste:

=SCHICHTDICKE_NAME('Mauerwerk')

Gibt die Dicke einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Schichtnames zurück. Ist der Namen bei mehreren Schichten vergeben, so wird die Dicke addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTDICKE_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt die Dicke der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Schicht 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtUWert_Name(Name)__ ####

Der U-Wert der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die U-Werte der Schichten addiert.


```python
Objektliste:

=SCHICHTUWERT_NAME('Mauerwerk')

Gibt den U-Wert einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Schichtnames zurück. Ist der Namen bei mehreren Schichten vergeben, so wird der U-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt den U-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Schicht 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtvolumen_Name(Name)__ ####

Volumen der vom Namen bestimmten Schicht. Haben mehrere Schichten den gleichen Namen, werden die Volumen addiert.


```python
Objektliste:

=SCHICHTVOLUMEN_NAME('Mauerwerk')

Gibt das Volumen einer Bauteils (Wand, Boden/Decke, Dach etc.) anhand des Schichtnames zurück. Ist der Namen bei mehreren Schichten vergeben, so wird das Volumen addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTVOLUMEN_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt das Volumen der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit der Schicht 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)




```

#### __Schichtmat_Klasse(Klasse)__ ####

Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten dieselbe Klasse verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTMAT_KLASSE('Keine')

Gibt den Materialnamen einer Schicht (Wand, Boden/Decke, Dach etc.) anhand der Klasse zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTMAT_KLASSE((T=WAND) & (SEL=WAHR), 'Keine')

Gibt der Namen der Schicht zurück, wenn das aktive Objekt eine Wand mit der Klasse 'Keine' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtmaterial_Name(Name)__ ####

Das Material der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über die Klasse definiert. Wenn mehrere Schichten denselben Namen verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTMATERIAL_NAME('Mauerwerk')

Gibt den Materialnamen einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Schichtnamens zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTMATERIAL_NAME((T=WAND) & (SEL=WAHR), 'Mauerwerk')

Gibt der Namen der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Schichtnamens 'Mauerwerk' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtfläche_Mat(Material)__ ####

Die Fläche einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTFLÄCHE_MAT('Backstein MAT')

Gibt die Nettofläche (Länge x Höhe) einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Materials zurück. Ist das Material bei mehreren Schichten vergeben, so wird die Fläche addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTFLÄCHE_NAME((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt die Nettofläche der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)


```

#### __Schichtklasse_Mat(Material)__ ####

Die Klasse der Wand-, Boden/Decke- oder Dachschichen. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird die Klasse der ersten Schicht zurückgegeben.


```python
Objektliste:

=SCHICHTKLASSE_MAT('Backstein MAT')

Gibt die Klasse einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Materials zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTKLASSE_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt die Klasse der Schicht zurück, wenn das aktive Objekt eine Wand mit des Materials 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtlamdba_Mat(Material)__ ####

Der Lambdawert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Lambdawert der ersten Schicht zurückgegeben.


```python
Objektliste:

=SCHICHTLAMBDA_MAT('Backstein MAT')

Gibt den Lambdawert einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Materials zurück. Ist der Lambdawert bei mehreren Schichten vergeben, so wird dieser addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTLAMBDA_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt den Lambdawert der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtname_Material(Material)__ ####

Der Name der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, wird der Name der ersten Schicht zurückgegeben.


```python
Objektliste:

=SCHICHTNAME_MATERIAL('Backstein MAT')

Gibt den Namen einer Schicht (Wand, Boden/Decke, Dach etc.) anhand des Materials zurück. Wenn mehrere Schichten dasselbe Material verwenden, wird der Name der ersten Schicht zurückgegeben.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTNAME_MATERIAL(T=WAND, 'Backstein MAT') 

Gibt der Namen der Schicht zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtRWert_Mat(Material)__ ####

Der R-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTUWERT_MAT('Backstein MAT')

Gibt den R-Wert der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand des Materials der Schicht zurück. Ist das Material bei mehreren Schichten vergeben, so wird der R-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt den R-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtdicke_Mat(Material)__ ####

Die Dicke der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTDICKE_MAT('Backstein MAT')

Gibt die Dicke einer Schicht(en) (Wand, Boden/Decke, Dach etc.) anhand des Materials zurück. Ist das Material bei mehreren Schichten vergeben, so wird die Dicke addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTDICKE_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt die Dicke der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __SchichtUWert_Mat(Material)__ ####

Der U-Wert der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTUWERT_MAT('Backstein MAT')

Gibt den U-Wert der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand des Materials der Schicht zurück. Ist das Material bei mehreren Schichten vergeben, so wird der U-Wert addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTUWERT_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt den U-Wert der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtvolumen_Mat(Material)__ ####

Das Volumen einer Seite der Wand-, Boden/Decke- oder Dachschichten. Die Schicht wird über das Material definiert. Wenn mehrere Schichten dasselbe Material verwenden, werden die Werte addiert.


```python
Objektliste:

=SCHICHTVOLUMEN_MAT('Backstein MAT') 

Gibt das Volumen der Schichten(en) eines Bauteils (Wand, Boden/Decke, Dach etc.) anhand des Materials der Schicht zurück. Ist das Material bei mehreren Schichten vergeben, so wird das Volumen addiert.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTVOLUMEN_MAT((T=WAND) & (SEL=WAHR), 'Backstein MAT')

Gibt das Volumen der Schicht(en) zurück, wenn das aktive Objekt eine Wand mit dem Material 'Backstein MAT' ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

### Material


#### __MaterialName()__ ####

Material der Objekte.


```python
Objektliste:

=MATERIALNAME

Gibt den Materialname eines Objektes zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALNAME(T=TIEFENKÖRPER) 

Zählt, ob am Objekt ein Material hinzugefügt wurde und gibt die Summe zurück.

T = Objekttyp


```

#### __MaterialZählen()__ ####

Anzahl an Materialien der Objekte.


```python
Objektliste:

=MATERIALZÄHLEN 

Zählt, wie oft ein Material verwendet wird. Hierbei bietet es sich an, die einzelnen Zeilen zusammenzufassen, um jeweils eine Summe pro Material zu erhalten. 

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALZÄHLEN(T=Tiefenkörper) 

Zählt, ob am Objekt ein Material hinzugefügt wurde und gibt die Summe zurück.

T = Objekttyp


```

#### __MaterialTextur()__ ####

Gibt den Namen der Texturzuweisung des Materials für Objekte zurück.


```python
Objektliste:

=MATERIALTEXTUR() 

Gibt den Namen der Textur zurück, welche im Material verwendet wird.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALTEXTUR(T=Tiefenkörper) 

Gibt den Namen der Textur zurück, welche im Materials verwendet wird, sofern das Objekt ei Tiefenkörper ist.

T = Objekttyp


```

#### __MaterialDatenfeld_Name(Materialname; IFC-Datenfeld)__ ####

Gibt das angegebene IFC-Datenfeld für das angegebene Material zurück.


```python
Objektliste:

=MATDATENFELD_NAME('Backstein MAT', 'MaterialLambda')

Gibt gibt den Lambda-Wert des angegeben Materials zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 

Alternativ kann mit

=MATDATENFELD_NAME(SCHICHTMATERIAL(1), 'MaterialLambda')

die spezifische Materialeigenschaft aus der Schicht (von Innen gezählt) direkt bezogen werden.



Verfügbare Eigenschaften:



- Allgemeine Informationen (Bitte englische Titel nutzen)

	Beschreibung 				= 'MaterialDescription'

	ID-Nummer 					= 'MaterialMark'

	Bauelementschlüssel 		= 'MaterialKeynote'



- Physikalische Werte (Bitte englische Titel nutzen)

	Spezifisches Gewicht		= 'MaterialSpecificGravity' 			als BOOLEAN: 'MaterialUsesSpecificGravity'

	Elastizitätsmodul			= 'MaterialModulusOfElasticity' 		als BOOLEAN: 'MaterialUsesModulusOfElasticity'

	Streckgrenze				= 'MaterialYieldStrength' 				als BOOLEAN: 'MaterialUsesYieldStrength'

	Zugfestigkeit				= 'MaterialTensileStrength' 			als BOOLEAN: 'MaterialUsesTensileStrength'

	Spezifische Wärmkapazität	= 'MaterialSpecificHeat' 				als BOOLEAN: 'MaterialUsesSpecificHeat'

	Emissionsgrad				= 'MaterialEmissivity' 					als BOOLEAN: 'MaterialUsesEmissivity'

	Albedo						= 'MaterialAlbedo' 						als BOOLEAN: 'MaterialUsesAlbedo'

	Ausdehnungskoeffizient		= 'MaterialThermalExpansionCoefficient' als BOOLEAN: 'MaterialUsesThermalExpansionCoefficient'

	Lambda						= 'MaterialLambda' 						als BOOLEAN: 'MaterialUsesLambda'

	CO2-Fußabdruck				= 'MaterialEmbodiedCarbon' 				als BOOLEAN: 'MaterialUsesEmbodiedCarbon'

	Schallgeschwindigkeit		= 'MaterialSoundVelocity' 				als BOOLEAN: 'MaterialUsesSoundVelocity'

	Dichte						= 'MaterialDensity' 					als BOOLEAN: 'MaterialUsesDensity'

	Schallimpedanz				= 'MaterialAcousticImpedance' 			als BOOLEAN: 'MaterialUsesAcousticImpedance'

	Rutschsicherheitswert		= 'MaterialSlipResistance' 				als BOOLEAN: 'MaterialUsesSlipResistance'



- Konstruktion (Bitte englische Titel nutzen)

	Kategorie					= 'MaterialCategory'

	Materialkassifikationen		= 'MaterialClassificationDescription'



	Hersteller					= 'MaterialManufacturer'

	Produktmodellnummer			= 'MaterialProductModel'

	Produktname					= 'MaterialProductName'

	Produktbeschreibung			= 'MaterialProductDescription'

	Produkt-URL					= 'MaterialProductURL'

	Produktherkunft				= 'MaterialSource'

	Produktoberfläche			= 'MaterialFinish'

	Produktkosten				= 'MaterialCost'



	IstSchichtfläche (Bool)		= 'MaterialIsSurfaceAreaMeasure'

	IstVolumen (Bool)			= 'MaterialIsVolumetric'

	'MaterialReferenceID'

	'MaterialStandard'
```

#### __MaterialIstEinfach()__ ####

Gibt den booleschen Wert Wahr zurück, wenn das Material der Objekte ein einfaches Material ist.


```python
Objektliste:

=MATERIALISTEINFACH 

Gibt den booleschen Wert 1 (1 = WAHR/ 0 = FALSCH) zurück, wenn ein Objekt ein einfaches Material verwendet. Ansonsten 0.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind.
```

#### __MaterialBauteilname(Materialname)__ ####

Der Name des Bauteils, dem das Material zugewiesen ist.


```python
Objektliste:

=MATERIALBAUTEILNAME('Backstein MAT')

Gibt den Schichtennamen der ersten zutreffenden Schicht (von Innen gezählt) zurück, welche das gegebene Material verwenden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALBAUTEILNAME(T=WAND, 'Backstein MAT')

Gibt den Schichtennamen der ersten zutreffenden Schicht (von Innen gezählt) zurück, welche das gegebene Material verwenden und auf den Objekttypen 'WAND' verweisen.

T = Objekttyp
```

#### __MaterialOberfläche() __ ####

Die Oberfläche der Objekte mit dem angegebenen Material.


```python
Objektliste:

=MATERIALOBERFLÄCHE('Backstein MAT')

Gibt die Oberfläche (Netto) der Schichten zurück, welche das gegebene Material verwenden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALOBERFLÄCHE(T=WAND, 'Backstein MAT')

Gibt die Oberfläche der Schichten zurück, welche das gegebene Material verwenden und auf den Objekttypen 'WAND' verweisen.

T = Objekttyp
```

#### __MaterialVolumenn()__ ####

Das Volumen der Objekte mit dem angegebenen Material.


```python
Objektliste:

=MATERIALVOLUMEN('Backstein MAT')

Gibt das Volumen der Schichten zurück, welche das gegebene Material verwenden.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALVOLUMEN(T=WAND,'Backstein MAT') 

Gibt das Volumen der Schichten zurück, welche das gegebene Material verwenden und auf den Objekttypen 'WAND' verweisen.

T = Objekttyp
```

#### __MaterialProzent(Materialname)__ ####

Der prozentuale Anteil des Material, das Objekten zugewiesen ist.


```python
Objektliste:

=MATERIALPROZENT('Backstein MAT') 

Gibt den prozentuale Anteil des Materials, welches einem Objekt zugewiesen ist zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALPROZENT(SEL=WAHR, 'Beton CH MAT')

Gibt den prozentuale Anteil des Materials vom aktiven Objekt zurück, wenn dieses das Material 'Beton CH MAT' verwendet.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __Schichtmaterial(Index)__ ####

Das Material der Schichten, auf die der Filter verweist.


```python
Objektliste:

=SCHICHTMATERIAL(1)

Gibt den Materialname der Schicht im Index [1] (von Innen) zurück.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=SCHICHTMATERIAL((T=WAND) & (SEL=WAHR), 1)

Gibt den Materialname der Schicht im Index [1] zurück, wenn das aktive Objekt eine Wand ist.

T = Objekttyp

SEL = Aktive Selektion (selection status)
```

#### __MaterialDatenfeld(IFC-Datenfeld)__ ####

Gibt das angegebene IFC-Datenfeld für das  Material zurück.


```python
Objektliste:

=MATERIALDATENFELD('MaterialLambda') 

Wiedergibt den hinterlegten Lambda-Wert des Materials.

Bei mehrschichtigen Bauteilen kann das Material über die Schicht (Unterobjekt) bezogen werden. Siehe hierzu Funktion: MatDatenfeld_Name.

Braucht keine weiteren Filter, da diese bereits von der Objektliste definiert sind. 



einzelne Zelle:

=MATERIALDATENFELD((T=Material) & (N='Backstein MAT'), 'MaterialManufacturer') 

Gibt in einer einzelnen Zelle die Information des Herstellers im verwendeten Material zurück.



Verfügbare Eigenschaften:



- Allgemeine Informationen (Bitte englische Titel nutzen)

	Beschreibung 			= 'MaterialDescription'

	ID-Nummer 				= 'MaterialMark'

	Bauelementschlüssel 	= 'MaterialKeynote'



- Physikalische Werte (Bitte englische Titel nutzen)

	Spezifisches Gewicht	= 'MaterialSpecificGravity' 			als BOOLEAN: 'MaterialUsesSpecificGravity'

	Elastizitätsmodul		= 'MaterialModulusOfElasticity' 		als BOOLEAN: 'MaterialUsesModulusOfElasticity'

	Streckgrenze			= 'MaterialYieldStrength' 				als BOOLEAN: 'MaterialUsesYieldStrength'

	Zugfestigkeit			= 'MaterialTensileStrength' 			als BOOLEAN: 'MaterialUsesTensileStrength'

	Spezfische Wärekapazität= 'MaterialSpecificHeat' 				als BOOLEAN: 'MaterialUsesSpecificHeat'

	Emissionsgrad			= 'MaterialEmissivity' 					als BOOLEAN: 'MaterialUsesEmissivity'

	Albedo					= 'MaterialAlbedo' 						als BOOLEAN: 'MaterialUsesAlbedo'

	Ausdehnungskoeffizient	= 'MaterialThermalExpansionCoefficient' als BOOLEAN: 'MaterialUsesThermalExpansionCoefficient'

	Lambda					= 'MaterialLambda' 						als BOOLEAN: 'MaterialUsesLambda'

	CO2-Fußabdruck			= 'MaterialEmbodiedCarbon' 				als BOOLEAN: 'MaterialUsesEmbodiedCarbon'

	Schallgeschwindigkeit	= 'MaterialSoundVelocity' 				als BOOLEAN: 'MaterialUsesSoundVelocity'

	Dichte					= 'MaterialDensity' 					als BOOLEAN: 'MaterialUsesDensity'

	Schallimpedanz			= 'MaterialAcousticImpedance' 			als BOOLEAN: 'MaterialUsesAcousticImpedance'

	Rutschsicherheitswert	= 'MaterialSlipResistance' 				als BOOLEAN: 'MaterialUsesSlipResistance'



- Konstruktion (Bitte englische Titel nutzen)

	Kategorie				= 'MaterialCategory'

	Materialklassifikationen	= 'MaterialClassificationDescription'



	Hersteller				= 'MaterialManufacturer'

	Produktmodellnummer		= 'MaterialProductModel'

	Produktname				= 'MaterialProductName'

	Produktbeschreibung		= 'MaterialProductDescription'

	Produkt-URL				= 'MaterialProductURL'

	Produktherkunft			= 'MaterialSource'

	Produktoberfläche		= 'MaterialFinish'

	Produktkosten			= 'MaterialCost'



	IstSchichtfläche (Bool)	= 'MaterialIsSurfaceAreaMeasure'

	IstVolumen (Bool)		= 'MaterialIsVolumetric'

	'MaterialReferenceID'

	'MaterialStandard'

```

### Phasen


#### __AktivePhase()__ ####

Gibt die aktuell aktive Phase in der Zeichnung zurück.



#### __ErstelltInPhase()__ ####

Gibt die Phase zurück, in der das Objekt erzeugt wurde.



#### __EntferntInPhase()__ ####

Gibt die Phase zurück, in der das Objekt entfernt wurde.



#### __WiederverwendetInPhase()__ ####

Gibt die Phase zurück, in der das Objekt wiederverwendet wurde.



#### __PhaseIstWiederverwenden()__ ####

Gibt WAHR zurück, wenn die Option "Wiederverwenden" für das Objekt ausgewählt wurde.



#### __PhaseIstTemporär()__ ####

Gibt WAHR zurück, wenn die Option "Temporär" für das Objekt ausgewählt wurde.



#### __PhaseVerwendetAltAttr()__ ####

Gibt WAHR zurück, wenn die Option "Alternative Attribute verwenden" für das Objekt mit Status "Abbruch" oder "Entfernt" ausgewählt ist.



#### __Phasenstatus('Phasenname')__ ####

Gibt den Status des Objekts in der angegebenen Phase zurück.


```python
Beispiel:

	=IFS ((PHASESTATUS('Phase 1')='NEU'), MATERIALVOLUME, ELSE, 0)
```

#### __VorhandenInPhase('Phasenname')__ ####

Gibt WAHR zurück, wenn das Objekt in der angegebenen Phase vorhanden ist.



#### __PhaseIfcStatus('Phasenname')__ ####

Gibt den IFC-Status für die Objekte in der angegebenen Phase zurück, auf die der Filter verweist. Objekte werden als NEU (das Objekt wird in dieser Phase erzeugt ABBRUCH (das Objekt wird in dieser Phase entfernt) oder VORHANDEN (das Objekt wurde zuvor erzeugt und in dieser Phase nicht entfernt) klassifiziert. Objekte, für die die Option "Temporär" aktiviert ist, werden als TEMPORÄR klassifiziert. Die erste Phase bildet eine Ausnahme: Sie enthält nur VORHANDENE Objekte.


```python
Beispiel:

	=IFS((PHASEIFCSTATUS('Phase 1')='VORHANDEN'), MATERIALVOLUME, ELSE, 0)
```

#### __PhaseIfcExport()__ ####

Gibt die im Dialogfeld "IFC-Projekt exportieren" für den Export angegebene Phase zurück. Wenn explizit keine Phase ausgewählt ist, gibt die Funktion standardmäßig die aktive Phase zurück.


```python
Beispiel:

	=IFS((PHASEIFCEXPORT()='PHASE 1'), MATERIALVOLUME, ELSE, 0)
```

## Tabellensuche


#### __VTabellensuche(Zelle; [opt_Param]; Erg_Spaltenindex; nicht_gefunden; Zellenbereich)__ ####

Kann anhand eines Suchbegrifes einen Zellenbereich einer Tabelle durchsuchen.


```python
Kann anhand eines Suchbegrifes einen Zellenbereich einer Tabelle durchsuchen.



=VTABELLENSUCHE(Wert, [opt_Param], KeinWert, Spaltenindex_Res, Zellenbereich[Array])

=VTABELLENSUCHE(B1, 2, 'no email', B3..C6)



  Wert              - Inhalt in der Zelle 'B1'. kann aber auch direkt als String angegeben werden.

  opt_Param         - hierbei nicht angegeben.  Wird genutzt für den REGEX Filter.

  KeinWert          - wird zurückgegeben, wenn es im Zellenbereich keine Übereinstimmung gibt.

  Spaltenindex_Res  - Die Spalte B als Index [2], welche nach einem passenden Begriff durchsucht wird.

  Zellenbereich     - Ist der Zellenbereich welcher durchsucht wird. Wobei im Beispiel die erste Spalte durchsucht wird und die im 'Spaltenindex_Res' angegebenen Werte als Resultat zurückgegeben werden.



|      |    A    |    B     |           C              |

|------|---------|----------|--------------------------|

| 1    | Suche:  | tech     |                          |

| 2    |         |          |                          |

| 3    |         | support  | support@vectorworks.net  |

| 4    |         | tech     | tech@vectorworks.net     |

| 5    |         | PR       | PR@vectorworks.net       |

| 6    |         |          |                          |

| 7    | Res:    |          | tech@vectorworks.net     |



Hierbei wird der Wert in B1 als Suchbegriff verwendet und mit den Werten B3..B6 abgeglichen. Wenn dieser gefunden wird, wird der Wert aus Spalte C zurückgegeben. Ansonsten 'no email'.

In Zelle C7 wird hierbei die Funktion =VTABELLENSUCHE(B1, 2, 'no email', B3..C6) eingegeben.



=VTABELLENSUCHE(A8, 2, 'no email', 'Beispiel-Tabelle':B8..C10)

Indem das beim Zellenbreich [B8...C10] den Namen der Tabelle 'Beispiel-Tabelle' vorgesetzt wird. Kann von einer anderen Tabelle den gesuchten Wert in eine Zelle geschrieben werden.



Wenn der optionale Parameter [opt_Param] weggelassen wird oder den Wert 'FALSCH' hat, wird der Wert genau verglichen (exakte Übereinstimmung).

Wenn der optionale Parameter [opt_Param] den Wert 'WAHR' hat, wird erwartet, dass der Wert ein regulärer Ausdruck ist, der für die Suche verwendet wird.



Hier finden Sie weitere Informationen zur Syntax von regulären Ausdrücken (ECMAScript-Standard):: https://cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript

Und hier ist ein Web-Tool, das beim Erstellen und Testen von regulären Ausdrücken hilft: https://regexr.com/
```

#### __XTabellensuche(Zelle; [opt_Param]; nicht_gefunden; Zellenbereich_Such; Zellenbereich_Erg)__ ####

Sucht den Inhalt der Zelle im Zellenbereich_Such und gibt den Inhalt der gefundenen Zelle aus Zellenbereich_Erg zurück. Die Zellenbereiche dürfen nur eine Spalte haben. Verwendet ECMAScript syntax für die Textverarbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript


```python
Kann anhand eines Suchbegriffes zwei Zeilenbereiche in zwei verschiedenen Tabellen durchsuchen. Hierzu wird ein Array in einer Tabelle definiert mit den Suchbegriffen, welche abgeglichen werden und ein anderes Array in einer zweiten Tabellen mit den Bezugswerten. Wichtig ist, das beide Tabellen über den selben Zellenbereich verfügen.



=XTABELLENSUCHE(Wert, [opt_Param], KeinWert, Suche[Array], Bezug[Array])

=XTABELLENSUCHE('tech', 'not found', 'Suche':A1..A3, 'Bezug':B1..B3)



  Wert          - Inhalt in der Zelle 'B1'. kann aber auch direkt als String angegeben werden.

  opt_Param     - hierbei nicht angegeben. Wird genutzt für den REGEX Filter.

  KeinWert      - wird zurückgegeben, wenn es im Zellenbereich keine Übereinstimmung gibt.

  Suche[Array]  - hierbei wird in einer Tabelle ein Array als Spalte definiert, welches die Begriffe beinhaltet, die abgeglichen werden.

  Bezug[Array]  - hierbei wird in einer anderen Tabelle ein Array als Spalte definiert, welches die Begriffe beinhaltet, welche bezogen werden.



Abbildung der Tabelle mit den Suchbegriffen:

In der Spalte A [Array:A1..A3] werden sie Suchbegriffe definiert. Wobei hierbei in der Spalte B jeweils XTABELLENSUCHE angewendet wird.

Tabellenname: Suche

|      |    A    |           B              |

|------|---------|--------------------------|

| 1    | support | support@vectorworks.net  |

| 2    | tech    | tech@vectorworks.net     |

| 3    | PR      | PR@vectorworks.net       |

|      |         |                          |      





Abbildung der Tabelle mit den Bezugsbegriffen:

In der Spalte B [Array:A1..A3] sind die Bezugswerte definiert. Spalte A repräsentiert unabhängige andere Werte.

Tabellenname: Bezug

|      |    A    |           B              |

|------|---------|--------------------------|

| 1    | 1234    | support@vectorworks.net  |

| 2    | 1235    | tech@vectorworks.net     |

| 3    | 1236    | PR@vectorworks.net       |

|      |         |                          |      



Betrachten Sie den Syntax =XTABELLENSUCHE('tech', 'not found', 'Suche':A1..A3, 'Bezug':B1..B3)

Hierbei wird direkt als String nach 'tech' gesucht. Dieser wird in der Tabelle 'Suche' im Array [A1..A3] abgeglichen. Wird einen passenden Wert gefunden. Wird aus der zweiten Tabelle 'Bezug' aus dem Array [B1..B3] den zutreffenden Wert bezogen.

Ist der [opt_Param] nicht angegeben, so wird ein Wert der Reihe nach im Array [B1..B3]. Für eine Präzisere Suche müsste man einen REGEX Filter anwenden.



Wenn der optionale Parameter [opt_Param] weggelassen wird oder den Wert 'FALSCH' hat, wird der Wert genau verglichen (exakte Übereinstimmung).

Wenn der optionale Parameter [opt_Param] den Wert 'WAHR' hat, wird erwartet, dass der Wert ein regulärer Ausdruck ist, der für die Suche verwendet wird.



Hier finden Sie weitere Informationen zur Syntax von regulären Ausdrücken (ECMAScript-Standard):: https://cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript

Und hier ist ein Web-Tool, das beim Erstellen und Testen von regulären Ausdrücken hilft: https://regexr.com/
```

## Text


#### __VERKETTEN(Text1; Text2;...;Textn)__ ####

Verknüpft einzelne Texte zu einem gesamten Text.


```python
=VERKETTEN(ANZAHL('Ecken'), ' Ecken')

Hierbei wird der Parameter der Anzahl 'Ecken' als Zahl bezogen und mit einem Text ' Ecken' verknüpft.

Daraus entsteht das Feedback z.B. '6 Ecken'.
```

#### __TEILSTRING(Text; Trennzeichen; [Index])__ ####

Zerlegt eine Zeichenkette in eizelne Arrays anhand eines Trennzeichens. Der Index bestimmt den Teiltext.


```python
=TEILSTRING('Küche;Schlafzimmer;Wohnzimmer;Flur', ';', 2)

Zerlegt eine Zeichenkette in einzelne Arrays anhand eines Trennzeichens. Der Index bestimmt den Teiltext.

Wobei das ';' den Unterbruch vorgibt. Der Index zählt die einzelnen Arrays und gibt den String 'Schlafzimmer' zurück.
```

#### __TXT(Wert; ZuEinheit; [Param1]; [Param2]; ...)__ ####

Verwandelt einen numerischen Wert von Dokumenteinheiten in die angegebene Einheit und gibt eine String-Darstellung zurück, wobei die Optionen zur Formatierung verwendet werden. Weitere Informationen finden Sie im Beispiel.


```python
Der Syntax TXT(Wert, ToUnit, [Param1], [Param2], ...) gibt eine Reihenfolge der Parameter vor.



BEISPIELE: 



Parameter Details:

- ToUnit - muss gegeben sein und definiert den Typen der Einheit.

	Mögliche Optionen aus den Dokument-Einstellungen:

		Dim				- lineare Einheit (Länge) 

		Area			- quadratische Einheit (Fläche)

		Volume			- kubische Einheit (Volumen)

		Angle			- Winkel

		

	Allgemeine Optionen (formatunabhängig):

		General			- als reele Zahl

		Sci				- als wissenschaftliche Zahl

		Percent			- als Prozentwert

	

	Spezifische lineare Einheiten (nur ein Parameter):

		FeetNInches, Inches, Feet, Miles, Yards, Microns, Millimeters, Centimeters, Meters, Kilometers, Degrees, Ares

	

	Spezifische Flächeneinheiten (n
```

#### __ISTALPHANUM(Text)__ ####

Gibt 'WAHR' zurück, wenn alle Zeichen im String Buchstaben und/oder Ziffern sind, andernfalls 'FALSCH'.


```python
=ISTALPHANUM('DIN461')

Gibt WAHR zurück, da es sich um eine alphanumerische Zusammenstellung handelt. Es werden nur Buchstaben und natürliche Zahlen berücksichtigt. Leerschläge sind auszulassen.


```

#### __ISTTEXT(Text)__ ####

'WAHR', wenn alle Zeichen in der Zeichenfolge Buchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls 'FALSCH'.


```python
=ISTTEXT('HelloWorld')

Gibt 'WAHR' zurück.


```

#### __ISTZAHL(Text)__ ####

'WAHR', wenn alle Zeichen in der Zeichenfolge Zahlen sind und mindestens ein Zeichen vorhanden ist, andernfalls 'FALSCH'.


```python
=ISTZAHL('721011081081113287111114108100')

Gibt 'WAHR' zurück.


```

#### __ISTKLEINBUCHSTABEN(text)__ ####

'WAHR', wenn alle Zeichen in der Zeichenfolge Kleinbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls 'FALSCH'. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben 'WAHR' zurück.


```python
=ISTKLEINBUCHSTABEN('hello world')

gibt 'WAHR' zurück, da keine Grossbuchstaben vorhanden.


```

#### __ISTLEERZEICHEN(Text)__ ####

'WAHR', wenn alle Zeichen in der Zeichenfolge Leerzeichen sind und mindestens ein Zeichen vorhanden ist, andernfalls 'FALSCH'.


```python
=ISTLEERZEICHEN('')

Gibt 'WAHR' zurück. Hilfreich, um leere Datenfelder auf Leerschläge zu durchsuchen.


```

#### __ISTWÖRTERGROSS(Text)__ ####

'WAHR', wenn jedes Wort mit einem Großbuchstaben beginnt andernfalls 'FALSCH'.


```python
=ISTWÖRTERGROSS('Katzen Sind Keine Hunde')

Gibt 'WAHR' zurück.


```

#### __ISTGROSSBUCHSTABEN(Text)__ ####

'WAHR', wenn alle Zeichen in der Zeichenfolge Großbuchstaben sind und mindestens ein Zeichen vorhanden ist, andernfalls 'FALSCH'. Nicht alphabetische Zeichen haben keine Groß- und Kleinschreibung und geben 'WAHR' zurück.


```python
=ISTGROSSBUCHSTABEN('HELLO WORLD')

Gibt 'WAHR' zurück.


```

#### __TEXTVERKETTEN([Trennzeichen]; Text1; Text2; …)__ ####

Verknüpft einzelne Texte zu einem durch das Trennzeichen getrennten String.


```python
=TEXTVERKETTEN('; ', Weil, Wörter, gerne, getrennt, sind)

Gibt den String 'Weil; Wörter; gerne; getrennt; sind'


```

#### __KLEINBUCHSTABEN(Text)__ ####

Alle Buchstaben des Textes werden in Kleinbuchstaben verwandelt.


```python
=KLEINBUCHSTABEN('HELLO World')

gibt den STRING 'hello world' zurück.


```

#### __WEGSCHNEIDENLINKS(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von links aus der Zeichenkette.


```python
=WEGSCHNEIDENLINKS('abchelloworld', 'abc')

Gibt den STRING 'helloworld' zurück.


```

#### __ERSETZEN(Text; altText; neuText; [Zähler])__ ####

Kann Teilbereiche aus einem gegebenen Text ersetzen. Wobei der Zähler ein optionaler Parameter ist.


```python
=ERSETZEN('Äpfel, Bananen, Kiwis, Orangen, Kiwis', 'Kiwis', 'Birnen', 1)



Hierbei wiederholt sich das Wort 'Kiwis' zweimal und die erste Instanz mit dem Zähler 1 durch 'Birnen' ersetzt wird. Der Output ist folgender Text: 'Äpfel, Bananen, Birnen, Orangen, Kiwis'

Der Zähler ist optional und muss nicht angeben werden. Folgend werden alle 'Kiwis' durch 'Birnen' ersetzt.
```

#### __WEGSCHNEIDENRECHTS(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von rechts aus der Zeichenkette.


```python
=WEGSCHNEIDENRECHTS('helloworldabc', 'abc')

Gibt den STRING 'helloworld' zurück.


```

#### __WEGSCHNEIDEN(Text; [Zeichen])__ ####

Entfernt die angegebenen Zeichen von beiden Seiten aus der Zeichenkette.


```python
=WEGSCHNEIDEN('abchelloworldabc', 'abc')

Gibt den STRING 'helloworld' zurück.


```

#### __GROSSSCHREIBEN(Text)__ ####

Jedes Wort wird mit einem großen Anfangsbuchstaben geschrieben.


```python
=GROSSSCHREIBEN('hello world')

Gibt den STRING 'Hello World' zurück.
```

#### __GROSSBUCHSTABEN(Text)__ ####

Alle Buchstaben des Textes werden in Großbuchstaben verwandelt.


```python
=GROSSBUCHSTABEN('hello wolrd')

Gibt den STRING 'HELLO WORLD' zurück.
```

#### __LÄNGE(Text)__ ####

Gibt die Länge (Anzahl Zeichen) des Textes zurück.


```python
=LÄNGE('hello world')

Zählt die Anzahl Zeichen und gibt den Wert 11 zurück.


```

#### __EINFÜGEN(Text; [Index]; Einfügetext)__ ####

Fügt den Einfügetext an der mit Index bezeichneten Stelle in den Text ein.


```python
=EINFÜGEN('Erdbeeren gehören zum Gemüse.', 18, ' nicht')

Fügt an der Stelle des Index 18 den Text ' nicht' ein.
```

#### __LINKS(Text; [Index])__ ####

Behält die Anzahl Zeichen von der linken Seite bis zur Position vom Index.


```python
=LINKS('EG00-GR', 4)

Zählt die Anzahl Zeichen von links bsi zum Index und gibt 'EG00' zurück.


```

#### __RECHTS(Text; Anzahl)__ ####

Behält die Anzahl Zeichen von der rechten Seite bis zur Position vom Index.


```python
=RECHTS('EG00-GR', 2)

Zählt die Anzahl Zeichen von rechts bis zum Index und gibt 'GR' zurück.


```

#### __MITTE(Text; [Index]; Anzahl)__ ####

Gibt einen Teiltext zurück, der bei Index beginnt und die Länge hat, die in Anzahl angeben ist. Ist Index negativ, wird die Startposition des Teilstrings vom Ende des Textes rückwärts bestimmt.


```python
=MITTE('Vectorworks', 1, 6)

Beginnt bei 'V' (von links gezählt) und zählt 6 Zeichen vorwärts. Gibt den Teilstring 'Vector' zurück.

=MITTE('Vectorworks', -1, -5)

Beginnt bei 's' (von rechts gezählt) und zählt -5 Zeichen zurück. Gibt den Teilstring 'works' zurück.

=MITTE('Vectorworks', -5, 4)

Beginnt bei 'w' (von rechts gezählt) und zählt 4 Zeichen vorwärts. Gibt den Teilstring 'work' zurück.
```

#### __LÖSCHEN(Text; [Index]; Anzahl)__ ####

Teilstring, der an der Position Index beginnt und die Länge Anzahl hat.


```python
=LÖSCHEN('EG00-GR', 4, 3)

Beginnt bei 'E' (von links gezählt) und zählt 4 Zeichen vorwärts und löscht ab dort angegebene Anzahl Zeichen. Gibt den Teilstring 'EG00' zurück.


```

#### __ANFÜHRUNGSZEICHEN(Text)__ ####

Setzt einen Text in Anführungszeichen.


```python
=ANFÜHRUNGSZEICHEN('Hello World')

Setzt den gegebenen Sting 'Hello World' in Anführungszeichen. Also "Hello World"
```

#### __WDH(Text; Anzahl)__ ####

Wiederholt den Text so oft, wie angegeben.


```python
=WDH('Miau ', 3)

Wiederholt den Text um die gegebene Anzahl. Also 'Miau Miau Miau '.


```

#### __FESTEDEZIMALSTELLEN(Zahl; [Dezimalstellen])__ ####

Formatiert eine Zahl als Text mit einer festen Anzahl von Dezimalstellen.


```python
=FESTEDEZIMALSTELLEN(10.12345, 3)

Formatiert die Zahl 10.12345 als Text und rundet diese aud drei Dezimalstellen, also 10.123.


```

#### __NULLENVORANSTELLEN(Zahl; Dezimalstellen)__ ####

Gibt eine Zahl als Zeichenkette mit führenden Nullen zurück, sodass die Gesamtlänge der Zeichenkette der angegebenen Breite entspricht. Ist die Breite kleiner als die ursprüngliche Länge, bleibt der Originalwert erhalten..


```python
=NULLENVORANSTELLEN(10.123, 8)

Die gegebene Zeichenkette 10.123 wird mit Nullen ergänzt, bis die Zeichenkette die Anzahl Dezimalstellen erreicht hat. Also 0010.123.
```

#### __CHAR(Zahl)__ ####

Fügt den angegeben UNICODE-Character als Zahlcode oder auch via Text als hexadezimal ein.


```python
=CHAR(8734)

Hierbei wird der nummerische Wert des UNICODE-Characters verwendet und gibt '∞' zurück.

=char('U+221E') also returns ∞

Alternativ ein Character auch hexadezimal angegeben werden, wobei dies als String geschrieben werden muss. Gibt auch '∞' zurück.



Liste von möglichen UNICODE-Characters:

https://www.vertex42.com/ExcelTips/unicode-symbols.html



Characters können auf Windows und MacOS auch direkt über die Zeichenübersicht eingefügt werden, ohne die Funktion zu verwenden.
```

#### __CODE(Text)__ ####

Gibt den Dezimalwert des UNICODE-Characters zurück.


```python
=CODE('∞')

Ist die Umkehrfunktion der Funktion 'Char' und gibt den Dezimalwert des UNICODE-Characters zurück. Also 8734.


```

#### __SUCHEN(Teiltext; Text; [GroßKleinschreibung])__ ####

Zählt die Anzahlzeichen bis der gegebene Text im Index kommt und gibt die Anzahl Zeichen zurück. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf 'WAHR' gesetzt ist. Das Ergebnis ist -1, wenn der Teiltext nicht gefunden wird.


```python
=SUCHEN('Text', 'Hier kommt ein Text', WAHR)

Zählt die Anzahl Zeichen bis der gegebene Text im Index kommt und gibt die Anzahl Zeichen zurück. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf 'WAHR' gesetzt ist. Das Ergebnis ist -1, wenn der Teiltext nicht gefunden wird.

Im Beispiel werden 15 Zeichen gezählt bis 'Text' im String kommt. Leerschläge werden hierbei auch berücksichtigt.
```

#### __SUCHENSUCHBEGRIFF(Suchbegriff; Text; [GroßKleinschreibung])__ ####

Die erste Stelle (Index) im Text, an der der Suchbegriff gefunden wird. Groß-/Kleinschreibung wird berücksichtigt, wenn das optionale Argument auf 'WAHR' gesetzt ist. Der Suchbegriff ist eine Folge von Zeichen, die ein Suchmuster angibt. Das Ergebnis ist -1, wenn der Begriff nicht gefunden wird.Verwendet ECMAScript-Syntax für die Textbearbeitung: https://www.cplusplus.com/reference/regex/ECMAScript/?kw=ECMAScript.


```python
=SUCHENSUCHBEGRIFF('(Soft)(.*)', 'soft Software', True) returns 5


```

#### __WERT(text)__ ####

Konvertiert Zahlen, welche als Text (String) geschrieben wurden in Zahlen.


```python
BEISPIEL: 'Anzahl: 5 Stk.' ist ein String mit der Zahl 5.

=WERT(TEILSTRNIG('Anzahl: 5 Stk.', ' ', 2))



Hierbei wird der Text mit ' ' in einzelne Arrays zerlegt und mit dem Index 2 die Zahl 5 extrahiert. Folgend wird diese mit 'WERT' in eine reele Zahl umgewandelt.
```

