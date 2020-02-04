- Erklären Sie die Gleichheit von Objekten (erklären Sie wann 2 Objekte gleich sind und erläutern Sie den Equals/HashCode Vertrag)
----
Grundsätzlich wird zwischen Typengleichehit, Wertgleichheit und Verweisgleichheit.
#### Verweisgleichheit ####
Beide Instanzen greifen auf den Selben Speicher zu, Equalsoperator muss nicht überschriben werden.
<pre><code class='language-cs'>
public Person(Person person) //Konstruktor für oberflächliches Klonen
        {
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = p1; 
           
            //Refereenzgleichheit --> Typengleichheit und Wertgleichheit
            Console.WriteLine(p2 == p1); //True
</code></pre>

#### Wertgleichheit ####
Bedeutet, dass die werte zweier Instanzen gelich sind.
