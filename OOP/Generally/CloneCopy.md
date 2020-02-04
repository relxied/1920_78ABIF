### OOP - Klonen von Objekten ###
----
#### Markus Mühleder
---
- Erläutern Sie oberflächliches und tiefes Klonen von Objekten (auf welche Arten können Objekte geklont werden)
---
#### Oberflächliches Klonen

Dies beinhaltet das Kopieren des Inhalts eines Objekts in eine andere Instanz der gleichen Klasse, wodurch ein Spiegelbild erzeugt wird. Aufgrund des direkten Kopierens von Referenzen und Zeigern teilen sich die zwei Objekte denselben extern enthaltenen Inhalt des anderen Objekts. 

<pre><code class='language-cs'>
public Person(Person person) //Konstruktor für oberflächliches Klonen
        {
            Name = person.Name;
            Mum = person.Mum;
            Dad = person.Dad;                
        }

...... Anwendung

            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = new Person(p1);

            p2.Mum.Name = "PH"; // p1.Mum.Name und p2.Mum.Name ist nun PH

</code></pre>

#### Tiefes Klonen
Dabei wird der Inhalt eines Objekts verwendet, um eine weitere Instanz derselben Klasse zu erstellen. In einer tiefen Kopie enthalten die beiden Objekte möglicherweise dieselben Informationen, aber das Zielobjekt hat eigene Puffer und Ressourcen. Die Zerstörung eines der Objekte wirkt sich nicht auf das verbleibende Objekt aus. Der überladene Zuweisungsoperator würde eine tiefe Kopie von Objekten erstellen. 
<pre><code class='language-cs'>
        public Person(Person person) //Konstruktor für tiefes Klonen
        {
            Name = new Person(person.Name);
            
            if (person.Mum != null)
            {
                Mum = new Person(person.Mum);
            }
            if (person.Dad != null)
            {
                Dad = new Person(person.Dad);
            }      
        }
...... Anwendung
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = new Person(p1);

            p2.Mum.Name = "PH"; // p1.Mum.Name bleibt Mum of Hans p2.Mum.Name ist nun PH
</code></pre>

Wenn das Objekt über Zeiger verfügt, muss eine tiefe Kopie ausgeführt werden. Bei der tiefen Kopie eines Objekts wird dem Objekt im freien Speicher Speicher zugewiesen, und die Elemente, auf die verwiesen wird, werden kopiert. Eine tiefe Kopie wird für Objekte verwendet, die von einer Funktion zurückgegeben werden.

Lösung in C# mit ICloneable:

Oberflächlich:
<pre><code class='language-cs'>
    class Person : ICloneable
    {
......
        public object Clone() // Oberflächlich Klonen
        {        
            return this.MemberwiseClone(); 
        }

...... Anwendung
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = (Person)p1.Clone();
    }
</code></pre>

Tief:
<pre><code class='language-cs'>
    class Person : ICloneable
    {
......
        public object Clone() // Tief Klonen
        {        
              Person ret = new Person(Name);
            ret.Mum = new Person(Mum);
            ret.Dad = new Person(Dad);
            return ret; 
        }       
</code></pre>