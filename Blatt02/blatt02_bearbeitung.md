Git-Spiel

"Ändern Sie eine Datei, die im Branch end nicht verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch."

1. Auf branch master sein
2. Eine Datei ändern, die in end nicht verändert wurde
3. Änderung mit git add für den Commit vormerken
4. Mit git commit einen neuen Commit auf master erzeugen
5. end mit git merge end in master zusammenführen
6. git status/git log zur Kontrolle nutzen


"Ändern Sie nun eine Datei, die auch im Branch end verändert wurde. Achten Sie dabei darauf, die Änderung an einer anderen Stelle in der Datei vorzunehmen. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch."

1. Auf dem Branch master sein
2. Eine Datei auswählen, die im Branch end ebenfalls verändert wurde (bei Aufgabe 1 mit git diff herausgefunden)
3. Datei bearbeiten
4. Die Datei mit git add zum Commit hinzufügen
5. Auf master mit git commit einen neuen Commit anlegen
6. Danach end mit git merge end in master zusammenführen
7. Mit git status und git log prüfen, ob alles korrekt übernommen wurde


"Wie (2), aber ändern Sie nun eine Stelle, die auch im Branch end verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch."

1. Auf master genau die Stelle ändern, die in end ebenfalls geändert wurde
2. Änderung mit git add für den Commit vormerken
3. Mit git commit einen neuen Commit auf master erzeugen
4. Branch end mit git merge end in master zusammenführen


"Was passiert, wenn die Änderung im master identisch zu der in end ist?"
Dann gibt es normalerweise keinen Konflikt. Beide Branches wollen an der Stelle ja das Gleiche, also kann Git das einfach übernehmen und der Merge läuft durch.

"Wenn die Änderung im master anders ist als in end"
Dann gibt es meist einen Merge-Konflikt. Es stoppt den Merge und markiert die Stelle in der Datei.

"Wie (2), aber setzen Sie bitte den Branch end auf die Spitze von master, bevor Sie end in master mergen."

1. Auf dem Branch master sein
2. Eine Datei ändern, die auch im Branch end verändert wurde, aber an einer anderen Stelle
3. Änderung mit git add vormerken
4. Mit git commit einen neuen Commit auf master erzeugen
5. Auf den Branch end wechseln
6. end auf den neuesten Stand von master bringen mit git rebase master
7. Konflikt entsteht: Konflikt lösen und rebase fertig machen
8. Danach zurück auf master wechseln
9. end mit git merge end in master zusammenführen


Katzen-Cafe Aufgaben: 
https://github.com/Lennart1703/prog2_ybel_catcafe
