# Sekvenser

I matematikken kan sekvenser av tall representeres på ulike former, f.eks. kan
sekvensen: 2, 5, 8, 11, 14, 17, ... representeres ved

![seqequation](http://bit.ly/1zEh4ki)

hvor ![an](http://bit.ly/1zEjfVb) er det n'te elementet i sekvensen,
![a1](http://bit.ly/1K0EznJ) er det første elementet i sekvensen og d er
differansen mellom etterfølgende medlemmer i sekvensen. I sekvensen ovenfor er
![a1](http://bit.ly/1K0EznJ) = 2 og d = 3. Da vil det 5'te elementet i sekvensen
være ![a5equation](http://bit.ly/1K0GoRk).
Denne sekvensen kalles en aritmetisk sekvens.

Slike sekvenser kan representeres som en klasse i Java. Klassen må ha to feltvariabler.

```java
	int d, a1;
```

**Task 1:** Angi klassedeklarasjonen og konstruktøren til en `ArithmeticSequence`
klasse som skal representere den generelle funksjonen beskrevet ovenfor.
Konstruktøren skal initialisere de to feltvariablene.

**Task 2:** Klassen skal ha metoden:

```java
public int getElement(int n){}
```

Metoden skal returnere det n'te elementet gitt av
![seqequation](http://bit.ly/1zEh4ki), hvor n er parameter til metoden og a1 og
d er feltvariabler. Lag metoden.

**Task 3:** Klassen skal også ha metoden:

```java
public int sum(int n){}
```

Denne metoden skal returnere summen av alle elementene i sekvensen opp til og
med n (fra og med det første elementet). Lag denne metoden.

![sumai](http://bit.ly/1zEpGaF)

Hint: Her kan man bruke en for-løkke. Man kan også bruke `getElement(int n)`.

**Task 4:** Klassen skal også implementere metoden:

```java
public String toString(){}
```

Under er det vist hva `toString()` skal generere ved utskrift, gitt at
feltvariablene er ![a1](http://bit.ly/1K0EznJ) = 2 og d = 3.

	2, 5, 8, 11, 14, 17, 20, 23, 26, 29, ...

Dvs. den skal ta med de ti første elementene i sekvensen.

**Task 5:** I Listing 7 er det spesifisert en kontrakt som en sekvens skal
implementere. Angi klassedeklarasjonen for `ArithmeticSequence` klassen slik at
den implementerer `Sequence` kontrakten. Hvilke øvrige endringer er også
nødvendige for å tilfredsstille kontrakten?

```java
package main.java.uis.no.intro;

public interface Sequence {
	public int getElement(int n);
	public int sum(int n);
	public int product(int n);
}
```
**Task 6:** Lag en abstrakt klasse `AbstractSequence` som implementerer
`Sequence`, men som kun implementerer `sum()` og `product()` metodene. Den
abstrakte klassen skal ikke ha feltvariabler eller konstruktør.

Hint: Ved å bruke `getElement(int n)` metoden kan man implementere både
`sum(int n)` og `product(int n)` på en generell måte uten å gi en implementasjon
av `getElement(int n)` metoden i `AbstractSequence`.

**Task 7:** Endre klassedeklarasjonen til `ArithmeticSequence` til å arve fra
`AbstractSequence`. Hvilke metoder må implementeres i `ArithmeticSequence`?

**Task 8:** For en aritmetisk sekvens kan summen finnes ved følgende kortform:

![effsum](http://bit.ly/1EME4xu)

Hva må man gjøre for å bruke kortformen (som er mer effektiv) for å bergene
summen for en aritmetisk sekvens, men samtidig beholde den generelle
summasjonsteknikken for sekvenser som ikke har tilsvarende kortform.

------

Det eksisterer andre sekvenser som også passer med Sequence kontrakten. F.eks. en
geometrisk sekvens: a, ar, ar2, ar3, ar4, ..., hvor a er en skaleringsfaktor og
`r != 0` er et felles forholdstall. Et eksempel på en geometrisk sekvens er:
1, 2, 4, 8, 16, 32, ..., hvor a = 1 og r = 2.

**Task 9:** Lag klassen GeometricSequence. Klassen skal ha med: klassedeklarasjon,
feltvariable, konstruktør, færrest mulig metoder (flest mulig skal arves).

**Task 10:** Legg til en mekanisme i `sum()` og `product()` som avviser innverdier
`n < 1`. Når verdier `n < 1` avvises skal det kastes et `IllegalArgumentException`
unntak.

**Task 11:** Lag en effektiv søkealgortime/metode:

```java
public int findElementIn(int k, int max){}
```

Metoden skal finne ut om et gitt tall k eksisterer i sekvensen. Hvis tallet finnes,
skal metoden returnere elementnummeret til tallet (posisjonen i sekvensen).
Hvis tallet ikke finnes i sekvensen skal -1 returneres. Parameteren max skal
brukes for å begrense søket til en endelig sekvenselengde.
Anta økende (sorterte) sekvenser, hvor `getElement(j) < getElement(j+1)`.

<!--**Task 12:** Lag en klasse SequenceBuffer som skal kunne lagre alle typer sekvenser i en ta-
bell. Tabellen skal utvides ved behov. Klassen skal ha en metode addSequence()
fora legge til nye sekvenser. Klasse skal ogsa ha en metode fora skrive ut alle
sekvensene writeOutAll(). Vis hvordan klassen kan brukes fra en main() me-
tode ved a legge inn
ere ulike sekvenser.-->

