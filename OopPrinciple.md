# Prinzipien
**Ordner:** Principle  
**Datei:** OopPrinciple.md
## by Martin Pechak
## Erklären Sie die folgenden Prinzipien, die in der OOP angewendet werden (gegebenenfalls können Sie auf die Prozedurale Programmierung verweisen):
- Abstraktion,
- Datenkapselung (information hiding),
- Vererbung,
- Polymorphismus

## Antworten
#### Abstraktion
Als Abstraktion versteht man nur diejenigen Dinge von einem Objekt zu nehmen, die auch benötigt werden.  
Abstraktion einers Schülers:
```
public class Pupil()
{
    public string Firstname { get; set; }
    public string Lastname { get; set; }
    public string Class { get; set; }
    public int Age { get; set;}
}
```
Abstraktion eines Lehrers:
```
public class Teacher()
{
    public string Firstname { get; set; }
    public string Lastname { get; set; }
    public int Age { get; set; }
    public bool HasDriverLicence { get; set; }
    public Date Hiredate { get; private set; }
}
```
Das obige Beispiel zeigt deutlich welche Merkmale eines Schülers und welche eines Lehrers wichtig sind für die Anwendung. Allgemeine Sachen, wie zum Beispiel die Sozialversicherungsnummer , die sowohl ein Schüler als auch ein Lehrer besitzen, ist für diese Anwendung nicht relevant.

#### Datenkapselung (information hiding)
Als Datenkapselung versteht man das Verbergen von Informationen vor dem direkten Zugriff von außen.
Ein direkter Zugriff auf die interne Datenstruktur wird damit unterbunden und wird per definierte Schnittstellen (Interfaces) ermöglicht.
In der Objektorientierten Programmierung (OOP) ist die Datenkapselung auch ein wichtiges Prinzip.  
Sie wird verwendet, damit Klassen nicht den internen Zustand anderer Klassen lesen oder sogar verändern können. Durch die Kapselung werden nur Angaben über das "WAS" (Funktionswiese) nach außen sichtbar aber nicht das "WIE" (die interne Darstellung)  
Verwendete Zugriffsarten in C#:
+ **public (+)**  
  Zugreifbar für alle Objekte (auch die der anderen Klassen)
+ **private (-)**  
  Nur für Objekte der eigenen Klasse zugreifbar
+ **protected (#)**  
  Nur für Objekte der eigenen Klasse und von Spezialisierungen derselben zugreifbar

#### Vererbung
##### Allgemeine Typen der Vererbung (Inheritance):
In der OOP gibt es einige Arten der Vererbung. Die nachstehenede Liste beschreibt diese und erläutert, welche der vier angeführten Vererbungen in C# möglich sind.
+ **Einfache Vererbung (single inheritance)**
  Mit der einfachen Vererbung erbt eine Klasse von der anderen. Dies ist ein mögliches Szenario in C#
```
public class A
{
    // members
}
public class B : A
{
    // members
}
```
+ **Mehrfache Vererbung (multiple inheritance)**
  Die mehrfache Vererbung erlaubt es, dass eine Klasse von mehreren Basis-Klassen ableitet. Dieses Szenario ist in C# nicht möglich, es gibt jedoch die Möglichkeit, von mehreren Schnittstellen (Interfaces) abzuleiten  

Folgene Darstellung ist in C# **nicht** möglich!
```
public class A
{
    // members
}

public class B
{
    // members
}

public class C : A, B
{
    // members
}
```
+ **Mehrstufige Vererbung (multilevel inheritance)**
  Die mehrstufige Vererbung ermöglicht die Vererbung über mehrerer Ebenen.  

Folgende Darstellung zeigt, dass B von A erbt und C wiederrum von B erbt:
```
public class A
{
    // members
}

public class B : A
{
    // members
}

public class C : B
{
    // members
}
```

+ **Schnittstellen Vererbung (inferface inheritance)**
  Die Schnittstellen Verebbung ermöglicht, dass eine Klasse oder eine Schnittstelle von mehreren Schnittstellen ableitet.

```
public interface IIdentifiable
{
    // members
}

public interface ICopyable
{
    // members
}

// Mögliches Szenario wenn eine Schnittstelle von mehrern Schnitstellen ableitet:

public interface IMyInterface : IIdentifiable, ICopyable<IMyInterface>
{
    // members
}

// Mögliches Szenario wenn eine Klasse von mehrern Schnitstellen ableitet:

public abstract class GenericController<I, M> : ControllerBase
        where I : IIdentifiable
        where M : Transfer.TransferObject, I, Contracts.ICopyable<I>, new()
{
    // members
}

```
#### Polymorphismus
Polymorphie erlaubt eine dynamische Methodenauswahl zur Laufzeit. Der Compiler erzeugt dazu eine virtuelle Liste mit allen möglichen Methoden, die zur Laufzeit in Frage kommen. Erst zur Laufzeit wird anhand des Typs entschieden, welche Methode aufgerufen wird.
```
public class Shape
{
    public virtual void Draw() => Console.WriteLine($"Shape with {Position} and {Size}");
}

public class Position
{
    public int X { get; set; }
    public int Y { get; set; }
    public ovverride string ToString() => $"X: {X}, Y: {Y}"
}

public class Size
{
    public int Width { get; set; }
    public int Height { get; set; }
    public ovverride string ToString() => $"Width: {Width}, Height: {Height}"
}

public class Rectangle : Shape
{
    public override void Draw() => Console.WriteLine($"Rectangle with {Position} and {Size}")
}

static void Main(string[] args)
{
    var r = new Rectangle();
    r.Position.X = 33;
    r.Position.Y = 22;
    r.Size.Width = 200;
    r.Size.Height = 100;
    r.Draw()                // Rechtangle with X: 33, Y: 22 and Width: 200, Height: 100
}
```
