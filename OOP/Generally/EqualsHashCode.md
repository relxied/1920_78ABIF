- Erklären Sie die Gleichheit von Objekten (erklären Sie wann 2 Objekte gleich sind und erläutern Sie den Equals/HashCode Vertrag)
----
Grundsätzlich wird zwischen Typengleichehit, Wertgleichheit und Verweisgleichheit.
#### Verweisgleichheit ####
Beide Instanzen greifen auf den Selben Speicher zu, Equalsoperator muss nicht überschriben werden.
<pre><code class='language-cs'>
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = p1; 
           
            //Refereenzgleichheit --> Typengleichheit und Wertgleichheit
            Console.WriteLine(p2 == p1); //True
</code></pre>

#### Typengelichheit ####
Bedeutet, dass die Typen zweier Instanzen gleich sind. Dies kann über den is Opderator überprüft werden und somit beim überschreiben der Equalsmethode angewendet werden.
<pre><code class='language-cs'>
        public override bool Equals(Object obj)
        {
            if (obj is Worker) return true;
            return false;
        }
</code></pre>

#### Wertegleichheit ###
Wertegelichheit besteht wenn die Werte zweier Instanzen gleich sind und geht grundsätzlich mit der Typengelichheit einher.
<pre><code class='language-cs'>
        public override bool Equals(Object obj)
        {
            Worker personObj = obj as Worker;
            if (personObj == null)
                return false;
            else
                return Name.Equals(personObj.Name) && Age.Equals(personObj.Age); 
        }
</pre></code>


Wird Equals() überschieben so muss auch immer GetHashCode() überschrieben werden.



#### Equals Vertrag #####

- x.Equals(x) returns true, except in cases that involve floating-point types. 
- x.Equals(y) returns the same value as y.Equals(x).
- x.Equals(y) returns true if both x and y are NaN.
- If (x.Equals(y) && y.Equals(z)) returns true, then x.Equals(z) returns true.
- Successive calls to x.Equals(y) return the same value as long as the objects referenced by x and y are not modified.
x.Equals(null) returns false.

Implementations of Equals must not throw exceptions; they should always return a value. For example, if obj is null, the Equals method should return false instead of throwing an ArgumentNullException.

#### HashCode Vertrag #####

internal consistency : Der Wert von hashCode () kann sich nur ändern, wenn a 
Eigenschaft, die sich in equals () ändert equals Konsistenz : Objekte, die einander gleich sind, müssen 
gib den gleichen Hashcode zurück collisions : ungleiche Objekte können den gleichen Hash-Code haben 

