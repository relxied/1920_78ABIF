### Konzept/Vererbung (Hlavacek)
**Datei:** Inheritance.md

- Erklären Sie die Relation der _Vererbung_ und geben Sie Entscheidungshilfen zur Evaluierung von _Vererbungsstrukturen_ an (nennen Sie mindestens ein Beispiel für eine gültige und eine ungültige Vererbung).  

- Erklären Sie welche Bedeutung die _Konstruktoren_ in der Vererbung haben und geben Sie anhand eines Beispiels an, wie die unterschiedlichen _Konstruktoren_ miteinander verkettet werden können.  

<span style="color:darkblue">Parameter können mit dem Schlüsselwort :base an den Konstruktor der Oberklasse weitergegeben werden. Durch das Schlüsselwort :base wird immer zuerst der Konstruktor der Oberklasse aufgerufen (ClassA) bevor der Block des Konstruktors (ClassB) aufgerufen wird. Dadurch wird Kodeverdoppelung vermieden.

Beispiel:</span>


```csharp
public ClassA
{
	public ClassA(int x,int y)
	{
		result = x + y;
	}
}

public ClassB : ClassA
{
	public ClassB(int x, int y): base(x,y)
	{
	}
}
```

- Erläutern Sie das Konzept _Interface_  und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Erklären Sie das Konzept 'Polymorphie' und geben Sie ein konkretes Beispiel, welches den Einsatz dieses Konzeptes demonstriert, an.

- Erklären Sie das „_Überschreiben von Instanzmethoden_&quot; und das dynamische Binden von Methoden (verwenden Sie zur Erläuterung ein konkretes Beispiel).

- Erläutern Sie das Konzept _Abstrakte Klassen_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Erläutern Sie das Konzept _Mehrfachvererbung_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Stellen Sie die beiden Konzepte _Vererbung_ und _Komposition_ gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

- Stellen Sie die beiden Konzepte _Abstrakte Klassen_  und _Interfaces_  gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.


### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters