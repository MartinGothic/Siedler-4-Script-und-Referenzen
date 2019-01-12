# Siedler-4-Script-und-Referenzen
(Vorab: die englische version ist mehr up-to-date, aber ich habe keine lust das zu übersetzen, tschüss)
Eine Liste vieler Scripte vieler Missionen und eine .rtf Datei die Informationen über die verschiedenen Funktionen gibt. Von mir erstellt vor 2 Jahren (2015). Die meisten lua scripts in /source/ stammen von ANDY.
Aktuell befindet sich auch eine Liste mit allen Funktionen und dessen Parameter und Rückgabewerte (nicht für alle Funktionen) in /custom/ um dir beim Einstieg in das Scripten zu vereinfachen.
# HOW TO: Lua-Script aus einer Map ziehen
Es gibt viele Möglichkeiten das zu machen. Die Siedler IV erstellt bei speziellen Maps eine spezielle Arbeitsspeicher-Region, in der ein Lua-Script ohne Enkodierung abgespeichert wird.
Ein einfacher Weg diese zu kopieren, wäre mit dem Programm ![Cheat Engine](http://cheatengine.org). Dieses Besitzt ein Memory Viewer. Darin enthalten kann man ganz einfach nach einem Text in dem Arbeitsspeicher suchen. So gut wie alle Lua-Scripts besitzen eine function mit dem Namen 
register_functions(). Diese wird vom Spiel selber gelesen und registriert die im Lua Code enthaltenn Funktionen. Somit kann man sehr einfach im Memory Viewer unter Search->Find Memory den text "function register_functions()" eingeben und man findet dort die Speicherregion, in der der Script abgelegt ist. Dort nun nur noch die Anfangs-Adresse und End-Adresse vom Script kopieren, dann auf File->Save Memory Region gehen und die beiden adressen eingeben. Cheat Engine kann dann den Speicher Ausschnitt speichern und diesen kann man dann z.B. mit Notepad++ öffnen bzw. ansehen.

# Settlers-4-Script-and-references
A folder containing scripts from a lot of maps and another folder listings all lua functions, some with documented parameters, some enumerations from all tables aswell as a deprecated .rtf file with information about some functions (really unnecessary). Documentation started 4 years ago and that's all that has come together. Almost all files in /source/ are from the old ANDROID MOBILE version of The Settlers 4, which indeed differs from the PC version somewhat.
In /custom/ you can see the useless .rtf file, the actually only important file "LUA_S4_TABLES.txt" which was first generated by dumping all tables and all functions inside those tables and then improved by hand. 
If you want to dump all functions yourself you can just put the YOURMAPNAME.txt into the S4/Script folder (if not exist - create), if you feel like starting from zero again.

# HOW TO: Get Lua Script from Map.
First of all make sure the map you want to extract the script from actually has a script.
## The roughest and pretty much oldest trick in the book...
is to re-open the game, open the map you want to extract the script from, use ![Cheat Engine](http://cheatengine.org) and search for the string "reg_func" and then open the memory window and if the memory region looks like the script try to search for the end and the beginning of the script and then copy the region. (sometimes you need to have a hex to string converter. I would recommend ![this one](http://string-functions.com/hex-string.aspx) ).
## If you want to extract the script out of a map that was inside of the game package (not a downloaded map) and you have The Settlers 4 History Edition
With the new release of The Settlers 4 History Edition Ubi Soft released, besides new improves, **all** configuration files, debug logs and scripts of every map outside of the .map file. Just take a look at <thesettlers4-path>/Script which contains tons of scripts with filenames of their corresponding map.
  
  ## The elegant way (If you already have a settlers with a map editor)
With my new modified S4Editor.exe combined with the Script Editor (source also on another repository) which are both on https://s4.muffinmar.io/ you will be able to open ".map"s and see their lua sources in the Script Editor window.
