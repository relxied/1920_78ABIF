### Model View Control (MVC) Pattern (Walchetseder)
**Datei** Mvc.md  


Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck  
  Trennung zwischen *Datenverarbeitung, Repräsentation und Eingaben*.  

- **Entwurfsproblem und wie das Muster das Problem löst**  
  Jede interaktive Anwendung besteht aus Eingaben, Daten und der Darstellung der Daten auf dem Bildschirm. Problematisch wäre es vor allem bei größeren Anwendungen diese drei Elemente in einer Klasse (Formular) zusammenzufassen.  
   MVC ist deswegen in drei Komponenten geteilt  
  1) Model  
  2) View  
  3) Controller  
  sind verantwortlich für die Steuerung der Anwendung durch den Benutzer. Sie überwachen alle Eingabegeräte, werten die Eingabedaten aus und leiten sie weiter. Änderungen der Modelldaten werden also vom Controller eingeleitet.  
View und Controller bilden zusammen die Benutzungsoberfläche. 
- Anwendbarkeit
- Struktur des Musters  
  