Git Status erklären


Changes not staged for commit:
Es gibt Änderungen in Dateien, die Git schon erkannt hat, aber sie sind noch nicht zum commit vorgemerkt (nicht “gestaged”)


"modified: CONTRIBUTING.md
modified: homework/b03.md"

CONTRIBUTING und homework/b03 wurden umgeschrieben.

Git schlägt vor:

git add <file> um sie zu stagen
git restore <file> um sie zu verwerfen

Untracked files:
foo.java ist neu und wird von Git noch nicht verfolgt (noch nie committed, nicht gestaged).

git add foo.java würde die Datei “tracken” und stagen.

no changes added to commit

Im git add Bereich ist gerade nichts, daher kann man so noch keinen Commit machen.



Geben Sie eine Befehlssequenz an, mit der Sie nur die Änderungen in foo.java committen können.

git add foo.java
git commit -m "..."

Da CONTRIBUTING.md und homework/b03.md noch nicht gestaged wurden würde nach git add foo.java bei einem commit nur foo.java hinzugefügt werden.


Git-Spiel

Was passiert an Tag 1? 
Mein Vorgehen: Das Herausfinden der commit ID von Tag01 mit Hilfe von git log. Dadurch bekommt man mit git show id folgenden Text (Beschreibung von dem was an Tag 1 passiert)

Lösung:
 In einer düsteren und mysteriösen Welt wagte sich ein furchtloser Held namens Markus in einen gefährlichen Dungeon. Es wurde erzählt, dass in diesem Dungeon Monster lauerten, die die Kerkerebenen terrorisierten. Markus war jedoch fest entschlossen, die Monster zu besiegen und das Amulet zu finden.

Mit seinem Schwert in der Hand und und einer leichten Rüstung bekleidet stieg Markus tapfer in den Dungeon ein. Schon bald stieß er auf die ersten Monster - grässliche, rattenähnliche Wesen.




Wann hat der Held zum ersten Mal 4 experience Punkte?

Vorgehen: Testen der einzelnen commits mit git show.

Lösung: Noch an Tag 1; Bei "Tag 1.3" wurde stats.md geändert:

Es riecht hier irgendwie seltsam, abgestanden und moderig. Von irgendwo kommt eine schwache Beleuchtung her. Ich schleiche vorsichtig die Gänge entlang und sehe in der Ferne eine Tür.
Vorsichtig öffne ich die Tür. Direkt dahinter ist wieder eine Ratte - aber sie schläft. Ich merke, dass mein Schwert gegen ein schlafendes Monster wirkungsvoller ist.
diff --git a/stats.md b/stats.md
index 063fa8c..8a7ae47 100644
--- a/stats.md
+++ b/stats.md
@@ -3,7 +3,7 @@
 | Property   | Value         |
 |------------|---------------|
 | health     | 10            |
-| experience | 2             |
+| experience | 4             |
 | hunger     | 0             |
 | weapon     | sword (3 dmg) |
 | armor      | light (2 dmg) |



 Wann hat der Held zum ersten mal 10 Hunger?

Vorgehen: git log --oneline stats.md
mit git show die stats.md tabellen vergleichen

Lösung:
Tag 2: 
| Property   | Value         |
 |------------|---------------|
-| health     | 10            |
-| experience | 4             |
-| hunger     | 4             |
+| health     | 5             |
+| experience | 10            |
+| hunger     | 10            |
 | weapon     | sword (3 dmg) |
 | armor      | light (2 dmg) |


Wieviele Heiltränke hat der Held insgesamt im Rucksack gehabt?
Vorgehen: git log --oneline rucksack.md
dann mit git show ...:rucksack.md die Tabellen vergleichen

Lösung: Er hatte ingesamt 2 Heiltränke im Inventar, aber davon wurde einer verbraucht.


Was hat der Held im Shop gekauft? Und wie viel Gold hat er dafür bezahlt?
Vorgehen: git log --oneline shopkeeper.md, git diff... git show...

Lösung: 
Was wurde gekauft?

tag 03.9 Brot
tag 03.14 Heiltrank

Wieviel Gold hat er bezahlt? 
Für das Brot: 5 Gold
Für den Heiltrank: 5 Gold


Was passiert zwischen Tag 3 und 4? 

git diff 2ffebcf 39568d5

Der Held gibt sein Gold aus beim Shop und dafür heilt er sich und er isst.



Hat der Held etwas gegessen? Falls ja, was und wann?


Vorgehen: Durch vorheriger Aufgabe weiß ich das der Held bei Tag 03.9 Brot gekauft hat

Mit git log --oneline rucksack.md alle Tage der Änderungen am Rucksack anzeigen

mit git diff und dem gegebene Tag 03.9 herausfinden wann das Brot gegessen wird

Lösung: An Tag 03.17 wird das Brot gegessen.

Beim letzten Commit (tag 04.5) ist etwas schief gelaufen, es wurden versehentlich zu wenig experience Punkte eingestellt. Ändern Sie diesen letzten Commit und passen Sie die experience Punkte auf 42 an.

Vorgehen: Im editor die 40 experience in stats.md zu 42 umändern.
Dann git commit --amend --no-edit


Schreiben Sie die Geschichte in der Datei questlog.md fort und erzeugen Sie einen neuen Commit für tag 04.6. Ändern Sie bitte hierzu nur die eine Datei questlog.md.

Vorgehen:
1. Datei "questlog.md" geöffnet"
2. einen Satz hinzugefügt
3. git status (test: ist questlog.md modified?)
4. git add questlog.md
5. git commit -m "tag 04.6"


Schreiben Sie die Geschichte noch weiter fort (tag 04.7), aber ändern Sie diesmal mehrere Dateien, die an diesem Tag (neuer Commit) gemeinsam eingecheckt werden sollen.

Vorgehen:
1. in "questlog.md" weitergeschrieben, rucksack.md einen Schlüssel hinzugefügt, in stats.md experience von 42 auf 43 geändert.
2. git status 
3. git add questlog.md ...
4. git commit -m "tag 04.7"


Fälschlicherweise wurden die Statuspunkte und die Ausrüstung bisher gemeinsam in der Datei stats.md geführt. Korrigieren Sie das und verschieben Sie die Ausrüstungsgegenstände aus der Datei stats.md in eine neue Datei gear.md. Checken Sie Ihre Änderungen als tag 04.8 (neuer Commit) gemeinsam ein.

Vorgehen:
1. weapon und armor aus stats.md gelöscht
2. neue Datei "gear.md" und dort eine Tabelle erstellt mit armor und weapon.
3. git add stats.md gear.md
4. git status: new file: gear.md, modified: stats.md
5. git commit -m "tag 04.8"



Gradle

Neues Projekt:
gradle init 

Dann jeweils ausgewählt:

Type: Application
Language: Java
Target Java: 25
Build Script DSL: Groovy
Test Framework: JUnit Jupiter

Wie finden Sie auf der Konsole heraus, welche Tasks es gibt?

In der Konsole:
gradle tasks


Erklären Sie, in welche Abschnitte das generierte Buildskript unterteilt ist und welche Aufgaben diese Abschnitte jeweils erfüllen.
plugins
Über Plugins wird die Unterstützung für Java und das Bauen von Applikationen aktiviert.

repositories
Legt fest, wo Abhängigkeiten herkommen.

dependencies
Definiert Bibliotheken für Compile und Tests.

application
Konfiguration für die ausführbare Anwendung.


Gehen Sie dabei im Detail auf das Plugin application und die dort bereitgestellten Tasks und deren Abhängigkeiten untereinander ein.


gradle run: zum Starten der Anwendung
gradle test / gradle check: Führt die Tests aus
gradle compileJava: Kompiliert den Hauptcode
gradle classes: Baut die „Main classes“, also das Ergebnis für die Anwendung



Projektlayout

.gradle/: Hilfsordner von Gradle
app/src/main/java/: Java Code der Anwendung
app/src/main/resources/: Ressourcen der Anwendung
app/src/test/java/: JUnit-Tests
app/src/test/resources/: Test Ressourcen
build/: generierte Dateien
settings.gradle: andere Einstellungen













