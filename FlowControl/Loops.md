# Schleifen und deren Einsatzzweck

Es gibt viele Situationen, in denen eine Anweisung nicht nur einmal, 
sondern mehrfach ausgeführt werden soll. 
Dazu könnte man grundsätzlich die Anweisung im Programmcode einfach mehrmals hintereinander
notieren, so oft wie es das Programm erfordern würde:

![anweisungsfolge](https://homepages.fhv.at/fw/fhvwbt/img/07_001_anweisungsfolge2.gif)

Ist jedoch sehr aufwändig und fehleranfällig.
Deshalb gibt es verschiedene Schleifen um diese Arbeit zu erleichtern.

- **Bedingungsgesteuerte Schleifen:**

Eine bedingungsgesteuerte Schleife ermöglicht es, 
eine Anweisung ausführen zu lassen, 
solange eine klar definierte und logisch überprüfbare (true/false) Bedingung erfüllt ist.

![bedingsgesteuerte Schleife](https://homepages.fhv.at/fw/fhvwbt/img/07_003_schleife2.gif)

- Abweisende Schleife / While-Schleife (kopfgesteuert):

Bei der abweisenden Schleife erfolgt die Bedingungsprüfung am Beginn der Schleife.
Falls das Resultat dieser Prüfung das Ergebnis "true" liefert, 
wird die Anweisung ausgeführt. Anschließend wird die Bedingung erneut geprüft usw. 
Die Anweisung wird solange ausgeführt, 
bis die Überprüfung der Schleifenbedingung das Ergebnis "false" liefert.

	while (bedingung){
       anweisung
	}

![Flussdiagramm](https://homepages.fhv.at/fw/fhvwbt/img/07_005_while_schleife-flussidagr.gif)

- Durchlaufende Schleife / Do-While-Schleife (fußgesteuert):

Gleich wie die While-Schleife mit Ausnahme, dass die Anweisung vor Überprüfung der Bedingung erfolgt.

![Fluss-Do-While](https://homepages.fhv.at/fw/fhvwbt/img/07_010_do_while.gif)

- Zählschleife / For-Schleife:

Die Zählschleife wird dann verwendet, 
wenn die Anzahl der Schleifendurchläufe festgelegt werden soll. 
Bei einer for-Schleife wird eine spezielle Variable, 
die so genannte Zählvariable verwendet, um die Anzahl der Schleifendurchläufe zu zählen. 
Die for-Schleife wird beendet, 
wenn der Wert der Zählvariablen eine bestimmte Bedingung nicht mehr erfüllt.

	for (Initialisierung; Abbruchbedingung; Wertänderung) {
     Anweisungen
	}

![Fluss-For](https://homepages.fhv.at/fw/fhvwbt/img/07_014_for_schleife-flussdiagr.gif)

- Foreach-Schleife (in C#)

In CSharp gibt es eine weitere Art von Schleifen, die "foreach" Schleife. Sie wird bei
"Sammlungen" verwendet. Zum Beispiel bei Listen, Arrays, usw. Grundsätzlich bei iterierbaren
Objekten. Mit der foreach-Schleife erspart man sich das deklarieren von Variablen um überhaupt über das
Objekt iterieren zu können. Wie schon der Name sagt führt diese Schleife die Anweisung für jedes vorhandene
Objekt in der Sammlung aus

Beispiel:

	int[] example = new int[] {1, 2, 3, 4, 5};

mit for-Schleife:

	for (i = 0, i < example.length; i++)
	{
		Console.WriteLine(example[i]);
	}

mit foreach:

	foreach(int number in example)
	{
		Console.WriteLine(number);
	}

