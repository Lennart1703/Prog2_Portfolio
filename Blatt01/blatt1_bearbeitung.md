Git Status erklären







Git-Spiel

Was passiert an Tag 1? 
Mein Vorgehen: Das Herausfinden der commit ID von Tag01 mit Hilfe von git log. Dadurch bekommt man mit git show id folgenden Text (Beschreibung von dem was an Tag 1 passiert)

Lösung:
 In einer düsteren und mysteriösen Welt wagte sich ein furchtloser Held namens Markus in einen gefährlichen Dungeon. Es wurde erzählt, dass in diesem Dungeon Monster lauerten, die die Kerkerebenen terrorisierten. Markus war jedoch fest entschlossen, die Monster zu besiegen und das Amulet zu finden.

Mit seinem Schwert in der Hand und und einer leichten Rüstung bekleidet stieg Markus tapfer in den Dungeon ein. Schon bald stieß er auf die ersten Monster - grässliche, rattenähnliche Wesen.




Wann hat der Held zum ersten Mal 4 experience Punkte?

Vorgehen: Testen der einzelnen commits mit git show.

Lösung: Noch an Tag 1; Bei "Tag 1.3" wurde stats.md geändert:

-Es riecht hier irgendwie seltsam, abgestanden und moderig. Von irgendwo kommt eine schwache Beleuchtung her. Ich schleiche vorsichtig die Gänge entlang und sehe in der Ferne eine Tür.
+Vorsichtig öffne ich die Tür. Direkt dahinter ist wieder eine Ratte - aber sie schläft. Ich merke, dass mein Schwert gegen ein schlafendes Monster wirkungsvoller ist.
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





