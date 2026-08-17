# Level 0 bis 6

Zusammenfassung der Linux-Befehle und Konzepte, die ich beim Durchspielen von Level 0 bis 6 im [Bandit](https://overthewire.org/wargames/bandit/)-Wargame (OverTheWire) gelernt und geübt habe.

*(Hinweis: Aus den Regeln von OverTheWire folgt, dass hier keine Level-Passwörter veröffentlicht werden.)*

## SSH-Verbindung

```
ssh BENUTZER@bandit.labs.overthewire.org -p 2220
```

Verbindung zum Bandit-Server über den dedizierten Port 2220.

## Navigation und Erkundung

```
ls          # sichtbare Dateien auflisten
ls -a       # versteckte Dateien einschließen
ls -la      # Details + versteckte Dateien (Rechte, Eigentümer, Größe...)
cd ORDNER   # in ein Verzeichnis wechseln
cd ..       # zurück ins übergeordnete Verzeichnis
cat DATEI   # Inhalt einer Datei anzeigen
```

## Sonderfälle bei Dateinamen

```
cat ./-file07                       # Datei, deren Name mit einem Bindestrich beginnt
cat "./--spaces in this filename--" # Datei mit Leerzeichen im Namen
```

`./` erzwingt, dass der Name als Pfad interpretiert wird und nicht als Befehlsoption.

## Unix-Rechte

Format `-rw-r-----`: Dateityp, gefolgt von den Rechten für Eigentümer / Gruppe / Andere (Lesen, Schreiben, Ausführen).

## Dateien identifizieren

```
file DATEINAME   # den tatsächlichen Inhaltstyp bestimmen
file ./*          # alle sichtbaren Dateien im aktuellen Verzeichnis analysieren
```

## Erweiterte Suche mit find

```
find . -type f                              # alle regulären Dateien
find . -type d                              # alle Verzeichnisse
find . -type f -size 1033c ! -executable    # exakte Größe, nicht ausführbar
find . -type f -size 1033c -executable      # exakte Größe, ausführbar
```

## Umrechnung Bit / Byte

1 Byte = 1 Octet = 8 Bit. Nützlich, wenn eine Aufgabe eine Größe in Bit angibt, `find -size` aber Bytes erwartet (`c`).

## Vorgehensweise

1. Aufgabenstellung des Levels lesen.
2. Passende Befehle identifizieren.
3. Ausführen und gesuchte Information finden.
4. Über SSH mit dem nächsten Level verbinden.
