Ist momentan noch mit Qt GUI konfiguriert. Wird noch zu reiner shell anwendung angepasst. Muss noch schauen, ob im source Verzeichnis unmittelbar der source code liegen kann.

1. Wenn der Qt Creator installiert ist, einfach auf smithWaterman.pro. Anschliessend links im Fenster auf "Projekte" klicken, oben "Ausfuehrung" auswaehlen und unter Argumente folgende Zeile einfuegen:

../smithWaterman/seq1.txt ../smithWaterman/seq2.txt

Auf Play klicken.

(Hinweis: Das Verzeichnis "smithWaterman-build-desktop-Qt_4_8_3_in_Pfad__System__Release" wird von Qt benötigt. Die txt Dateien befinden sich im smithWaterman Verzeichnis.)

2. Kompilieren per gcc
Per Terminal kompilieren, Beispiel:

	$ /qt_workspace/smithWaterman$ g++ -o smithWaterman \
	-L /opt/AMDAPP/lib/x86_64/ -I /opt/AMDAPP/include/ \
	main.cpp single.cpp filehandler.cpp -lOpenCL

ausführen mit: 

	$ ./smithWaterman seq1.txt seq2.txt

3. Oder per make (sollte die Meldung "make: Für das Ziel »first« ist nichts zu tun." erscheinen, dann gibt es keine Aenderungen im Quellcode seit dem letzten make.) 
Befehle:

	$ make && ./smithWaterman seq1.txt seq2.txt