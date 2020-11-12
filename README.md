# zombie
# Projekt Aufgaben

In diesem Projekt "Zombie" werden wir die Gesichte von Jane Austen in eine Geschichte für Zombies umwandeln, dabei werden wir:
* Zeichnen Linien und drehen sich mit Python Turtle
* Ändern die Stiftfarbe nach dem Zufallsprinzip
* Verwenden Schleifen, um einige Anweisungen zu wiederholen und Formen zu erstellen
* Verwenden mehr Schleifen, um Spiralmuster zu erstellen
* Erstellen eine Funktion zum Zeichnen einer Schneeflocke

# Was wird benötigt?

* Python 3
* Das module requests. Das müssen wir zuerst installieren.
Bei MacOs oder Linux: ```sudo pip3 install requests```
Bei Windows: ```pip install requests```

# Schritt 1:  Importieren

Um Wörter oder Buchstaden zu ersetzten brauchen wir die Anweisung re.

```import re```

Für zufällige Anweisungen benötigen wir choice.

```from random import choice```

Für das Speichern von Dateien benötigen wir requests, was wir zuvor installiert haben.

```import requests```

# Schritt 2: Datei holen

Wir holen uns das Buch als Datei und speichern es als variable.

```url = "gutenberg.txt"```
```r = open(url,encoding= "utf8").read()```
```text = r```

# Schritt 3:  Listen erstellen um Zombies einzubauen

Um die Menschen im Buch mit Zombies zu ersetzten müssen wir Listen erstellen, die die Wörter beeinhalten, die wir ersetzen möchten.
Damit beispielsweise "man" zu "zombie" wird. Es soll aber auch die Mehrzahl, also "men" zu "zombies" ersetzt werden.
Deshalb benötigen wir dafür 2 Listen, eine für die Einzahl und eine für die Mehrzahl.

Zum Ersetzen benutzen wir diese Codes:

```for word in plural_nouns: text = re.sub(r'\b{0}\b'.format(word), "zombies", text)```

```for word in singular_nouns: text= re.sub(r'\b{0}\b'.format(word), "zombie", text)```

# Schritt 4:  Auch Wörter mit großem Anfangsbuchstaben ersetzten

Nicht nur die kleingeschriebenen wörter sollen ersetzt werden. Sonst werden die Wörter die am Satzanfang stehen nicht ersetzt. Dafür benötigen wir diese Anweisung:

```plural_nouns = plural_nouns + [word.title() for word in plural_nouns]```


# Schritt 5: Zombiegeräusche hinzufügen mithilfe 2 weiterer Listen

Da Zombies nicht sprechen, sondern eher stöhnen, muss die Sprache angepasst werden.

Die erste Liste beinhaltet alle Wörter die ersetzt werden sollen, zum Beispiel "said".
Die zweite Liste beinhaltet alle Wörter die eingesetzt werden sollen, zum Beispiel "groaned"

Dann verwenden wir nun das module "choice", so kann der Begriff mit einem zufälligen Zombie-Geräusch aus unserer Liste ersetzt werden.
 
```for word in speaking: text = re.sub(r'\b{0}\b'.format(word), choice(zombie_sounds), text)```

Außerdem wollen wir noch die Sprache innerhalb der " " verändern. Denn Zombies sprechen nicht so wie wir Menschen, also ersetzten wir einzelne Buchstaben, die Zombies nicht sagen würden mit anderen Buchstaben. So wird das Gesprochene für uns unverständlich, das ist realistischer! ;)
        
# Schritt 8: Die Datei einfügen

Damit am Ende eine neue Datei mit dem Namen "Zombie" erstellt wird, benötigen wir noch diesen Code am Ende:

```with open("Zombie.txt", "w", encoding="utf-8") as f: f.write(text)```
    

      
