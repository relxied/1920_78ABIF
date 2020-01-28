## Terms
### Ordnen Sie die nachfolgenden Begriffe nach ihrer Entstehung und erläutern Sie die Bedeutung:
**Verantwortlicher:** Engleder Michael

- Bibliothek
- Unterprogramm
- Prozedur
- Klasse
- Funktion
- Package
- Modul

-------------------------------------
#### Unterprogramme
Unterprogramme oder Methoden sind Codeblöcke mit Anweisungen. 
Ein Programm ruft eine Methode auf und alle Anweisungen innerhalb dieser Metoden werden ausgeführt!   
Dabei können Unterprogramme sowohl Werte zurückgeben, oder Werte als Parameter vom Aufrufer erhalten.
Weiter können Methoden mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden. 
Siehe Prozedur / Funktion

#### Prozedur
Prozeduren werden von einem Programm aufgerufen, geben aber **keinen Wert (void)** zurück  
````
    class Program
    {
        static void Main(string[] args)
        {
            WriteHelloWorld
        }
        public static void WriteHelloWorld()
        {
            Console.WriteLine("Hello World!");
        }
    }
````

#### Funktion
Funktionen werden von einem Programm aufgerufen und geben **einen Wert** zurück 
````
    class Program
    {
        static void Main(string[] args)
        {
            int sum = Sum(1, 2);
        }

        private static int Sum(int num1, int num2)
        {
            return num1 + num2;
        }
    }
````
#### Klassen
Klassen beschreiben **Eigenschaften und Fähigkeiten** von Objekten.
Klassen werden in C# mit **class** deklariert und können mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden. 
Diese können Fields, Properties und Methoden als sogenannte Members beinhalten.
Klassen können von anderen Klassen oder Interfaces deren Members erben.
Instanziert werden Klassen mit dem Schlüsselwort new(). Dabei wird der Konstruktor aufgerufen, welchen auch Parameter zur Instanzierung übergeben werden können.  

````
    public class Car
    {
        private int fuelTank;
        public string Brand { get; set; }
        public Car(int maxFuelLevel)
        {
            this.fuelTank = maxFuelLevel;
        }
        public void StartEngine()
        {

        }
    }
````
Abbildung Klassendiagramm  
![alt text](CarClassDiagram.png "Klassendiagramm Car")

#### Bibliothek
Bibliotheken sind Sammlungen von Unterprogrammen, die von Programmen angefordert werden können.
Im Unterschied zu Programmen stellen Bibliotheken keine eigenen lauffähigen Einheiten dar!
Nach der Kompilierung werden Bibliotheken in DLL-Dateien übersetzt!

#### Package
Bibliotheken sind Sammlungen von Unterprogrammen, die von Programmen angefordert werden können.
Im Unterschied zu Programmen stellen Bibliotheken keine eigenen lauffähigen Einheiten dar!
Nach der Kompilierung werden Bibliotheken in DLL-Dateien übersetzt!
