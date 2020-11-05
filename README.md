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

# Schritt 1: re importieren

Um Wörter oder Buchstaden zu ersetzten brauchen wir die Anweisung re.

```import re```

# Schritt 2:  Listen erstellen um Zombies einzubauen

Um die Menschen im Buch mit Zombies zu ersetzten müssen wir Listen erstellen, die die Wörter beeinhalten, die wir ersetzen möchten.
Damit beispielsweise "man" zu "zombie" wird. Es soll aber auch die Mehrzahl, also "men" zu "zombies" ersetzt werden.
Deshalb benötigen wir dafür 2 Listen, eine für die Einzahl und eine für die Mehrzahl

# Schritt 3: Menschen mit Zombies ersetzten

Dafür benötigen wir nun die Anweisung re. 
  
```for word in plural_nouns:
    text = re.sub(r'\b{0}\b'.format(word), "zombies", text)```
        
```for word in singular_nouns:
        text= re.sub(r'\b{0}\b'.format(word), "zombie", text)```

# Schritt 4:  Auch Wörter mit großem Anfangsbuchstaben ersetzten

```plural_nouns = plural_nouns + [word.title() for word in plural_nouns]```


# Schritt 5: Zombiegeräusche hinzufügen mithilfe 2 weiterer Listen

Die erste Liste beinhaltet alle Wörter die ersetzt werden sollen, zum Beispiel "said".
Die zweite Liste beinhaltet alle Wörter die eingesetzt werden sollen, zum Beispiel "groaned"

# Schritt 6: choice von der Random Bibiliothek importieren

```from random import choice```

# Schritt 7: die Zombiesprache anwenden

 
```for word in speaking:
        text = re.sub(r'\b{0}\b'.format(word), choice(zombie_sounds), text)```
        
# Schritt 8: Die Datei einfügen

Dafür importieren wir voerst unser module "request", was wir zu Beginn installiert haben.
Dann wird die Datei importiert:


```url = "gutenberg.txt"```
```r = open(url,encoding= "utf8").read()```
```text = r```

Damit am Ende eine neue Datei mit dem Namen "Zombie" erstellt wird, benötigen wir noch diesen Code am Ende:

```with open("Zombie.txt", "w", encoding="utf-8") as f:
    f.write(text)```
    
# Schritt 9: Einzelne Buchstaben ersetzen, um die Zombiesprache darzustellen
      
