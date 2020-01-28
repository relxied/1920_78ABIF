# Technik/Serialisierung

### Erklären Sie die Technik 'Serialisierung von Objekten' und 'Deserialisierung von Objekten'.

Bei der Serialisierung wird ein Objekt in einen Stream konvertiert, um das Objekt zu speichern oder in den Speicher, eine Datenbank oder eine Datei zu übertragen.
Auch bei der Übertragung von  Der Hauptzweck ein Objekts zu speichern, um es bei Bedarf neu erstellen zu können. Der umgekehrte Vorgang wird Deserialisierung gennatn.

Im .Net Framework gibt verschieden vorgefertigte Serializer z.B. XML, JSONoder Binary, 
Als Beispiel die Seralisierung und Deserealisierung einer Klasse in eine Datei.
 
```csharp
[Serializable]
class Test
{
    public string Name {get; set;}
    ...
}

//Serealisierung
public static void Serialize()
{
    IFormatter formatter = new BinaryFormatter();
    Stream stream = new FileStream(filepath, FileMode.Create, FileAccess.Write);

    formatter.Serialize(stream, tests);
    stream.Close();
}

//Deserealisierung
public static void Deserialize()
{
    IFormatter formatter = new BinaryFormatter();
    Stream stream = new FileStream(filepath, FileMode.Open, FileAccess.Read);
    var tests = (List<Test>)formatter.Deserialize(stream);

}

```


### Serialisierung und Deserialisierung ist eine wichtige Basistechnik für weitere höhere (Architektur-)Konzepte. Nennen Sie eine weitere Technik, welche Serialisierung und Deserialisierung als Basis verwendet.

remoteservices
signal a 
https://www.it-visions.de/glossar/alle/835/lexikon.aspx

 .NET Remoting

