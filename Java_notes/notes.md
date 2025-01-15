# Java Lernziele

## 1. JavaDoc
- **Vorteile gegenüber normalen Kommentaren:**
  - Automatische HTML-Dokumentation
  - Standardisiertes Format
  - IDE-Integration mit Autovervollständigung

- **Syntax:**
```java
/**
 * Berechnet die Summe zweier Zahlen
 * @param a erste Zahl
 * @param b zweite Zahl
 * @return Summe von a und b
 * @throws IllegalArgumentException wenn negative Zahlen übergeben werden
 */
public int addiere(int a, int b) { ... }
```

## 2. JUnit Tests
- **Grundstruktur eines Tests:**
```java
import org.junit.Test;
import static org.junit.Assert.*;

public class RechnerTest {
    @Test
    public void testAddition() {
        Rechner rechner = new Rechner();
        int ergebnis = rechner.addiere(2, 2);
        assertEquals(4, ergebnis);
        assertTrue(ergebnis > 0);
        assertFalse(ergebnis < 0);
    }
}
```

## 3. Vererbung & Abstraktion
### Vererbung
```java
class Tier {
    protected String name;
    
    public Tier(String name) {
        this.name = name;
    }
    
    public void machGeräusch() {
        System.out.println("???");
    }
}

class Hund extends Tier {
    public Hund(String name) {
        super(name);  // Ruft Tier-Konstruktor auf
    }
    
    @Override
    public void machGeräusch() {
        super.machGeräusch();  // Optional: Ruft Elternmethode auf
        System.out.println("Wuff!");
    }
}
```

### Abstrakte Klassen
```java
abstract class Form {
    abstract double berechneFläche();  // Muss von Unterklassen implementiert werden
    
    double berechneUmfang() {  // Kann implementiert werden
        return 0.0;
    }
}
```

### Interfaces
```java
interface Schwimmfähig {
    void schwimme();
    void tauche();
}

class Fisch implements Schwimmfähig {
    @Override
    public void schwimme() { ... }
    
    @Override
    public void tauche() { ... }
}
```

### Interface vs. Abstract
- **Interface:**
  - Nur Methodensignaturen (seit Java 8 auch default Methoden)
  - Mehrfachimplementierung möglich
  - Keine Konstruktoren
  - Alle Methoden public

- **Abstrakte Klasse:**
  - Kann Implementierungen haben
  - Nur einfache Vererbung
  - Hat Konstruktoren
  - Verschiedene Sichtbarkeiten möglich

## 4. Polymorphie
### Runtime Polymorphie (Überschreiben)
```java
List<Tier> tiere = new ArrayList<>();
tiere.add(new Hund("Bello"));
tiere.add(new Katze("Mimi"));

// Jedes Tier macht sein eigenes Geräusch
for(Tier tier : tiere) {
    tier.machGeräusch();  // Ruft die spezifische Implementierung auf
}
```

### Compile-time Polymorphie (Überladen)
```java
class Rechner {
    int addiere(int a, int b) { return a + b; }
    double addiere(double a, double b) { return a + b; }
    String addiere(String a, String b) { return a + b; }
}
```

## 5. Wichtige Keywords
### super
- **Konstruktor:** `super()` oder `super(parameter)`
- **Methoden:** `super.methodenName()`
- Wird implizit bei Konstruktoren aufgerufen wenn nicht explizit angegeben

### static
- Gehört zur Klasse, nicht zur Instanz
- Beispiel: `Math.random()`, `Arrays.asList()`
- Zugriff ohne Objektinstanz möglich

### final
- Bei Variablen: Wert kann nicht geändert werden
- Bei Methoden: Kann nicht überschrieben werden
- Bei Klassen: Kann nicht vererbt werden

## 6. Generics
```java
// Typsichere Collections
ArrayList<String> namen = new ArrayList<>();
namen.add("Hans");  // OK
namen.add(123);     // Compilerfehler!

// Eigene generische Klasse
class Box<T> {
    private T inhalt;
    
    public void setInhalt(T inhalt) {
        this.inhalt = inhalt;
    }
    
    public T getInhalt() {
        return inhalt;
    }
}
```
