---
label: CoreELEC für die Dune HD Homatics R 4K Plus
order: -2
icon: flame
---

# CoreELEC für die Dune HD Homatics R 4K Plus

<h3>Was wird benötigt</h3>

- Android TV v5310 oder höher für funktionierendes Dolby Vision
- Dolby Vision muss in den Android-Einstellungen aktiviert sein.
- PC (Windows)
- USB 3.0 Stick (min. 16GB)
- [balenaEtcher - Portable](https://etcher.balena.io/#download-etcher) - (Download)
- [CoreELEC 21.0 - Generic Build](https://relkai.coreelec.org/?dir=Amlogic-ne/ce-21) - (Download)
- [remote.conf](https://raw.githubusercontent.com/U3knOwn/sb-wiki/main/dune/remote.conf) - (Download)

<h3>USB-Stick für CoreELEC vorbereiten</h3>

1. USB-Stick an den PC anschließen. 
2. Starte das Flashtool `balenaEtcher`. 
3. `Flash from file` drücken und die CoreELEC-Imagedatei auswählen.  
(z.B: CoreELEC-Amlogic-ne.aarch64-21.0-Omega_nightly_20231031-Generic.img.gz).
4. Drücke `Select target` und wähle den USB-Stick aus.
5. Drücke nun auf `Flash!`.
6. balenaEtcher führt automatisch einen Validierungsprozess mit einem `grünen Balken` durch.
7. Der USB-Stick ist nun geflasht.
8. Öffne die `COREELEC` Partition mit dem Windows Explorer.
9. Kopiere die `remote.conf` in das Hauptverzeichnis.
10. Gehe nun in den Ordner `device_trees`.
11. Kopiere die Datei `sc2_s905x4_sei_smb_280.dtb` in das Hauptverzeichnis.
12. Im Hauptverzeichnis benennen wir die Datei `sc2_s905x4_sei_smb_280.dtb` in `dtb.img` um.
13. Kontrolle: Die Dateien `dtb.img` und `remote.conf` sollten sich im Hauptverzeichnis befinden.
15. Jetzt entfernen wir den USB-Stick vom Computer.

<h3>CoreELEC starten</h3>

1. Nun stecken wir den fertigen USB-Stick in den `USB 3.0` Slot der Dune HD Homatics R 4K Plus.
2. Jetzt starten wir CoreELEC, indem wir die `Ein/Aus Taste` der Fernbedienung lange gedrückt halten.
3. Jetzt klicken wir auf `Neustart`.
4. Nun startet `CoreELEC` und beginnt mit der automatischen Installation.
5. Wenn die Installation beendet ist, muss man durch den Einrichtungsprozess gehen.

<h3>Hilfestellungen</h3>

==- Wie komme ich von CoreELEC zu Android TV?

1. Ihr müsst in das Neustart-Menü gehen.
2. Nun drückt auf `Reboot to EMMC`.
3. Nach ein paar Sekunden startet die Box in das Android TV System.

===

==- Wie komme ich von Android TV zu CoreELEC?

1. Die `Ein/Aus Taste` der Fernbedienung länger gedrückt halten.
2. Jetzt klicken wir auf `Neustart`.
3. Nach ein paar Sekunden startet die Box in das CoreELEC System.

===

==- Warum wird `Reboot to EMMC` nicht angezeigt?

Das liegt wahrscheinlich daran, dass man einen anderen Skin verwendet.  
Dies beheben wir, indem wir das [Reboot to Android TV](https://github.com/U3knOwn/sb-wiki/raw/main/dune/script.reboottoandroidtv.zip) Addon installieren.

Einfach das `Addon` jedesmal ausführen wenn ihr das Android TV Betriebssystem starten wollt. 

===

==- Warum funktioniert Dolby Vision nicht?

**Android TV muss v5310 oder höher sein für ein funktionierendes Dolby Vision.**  

**Dolby Vision muss in den Android Einstellungen aktiviert sein.**

1. In CoreELEC gehen wir auf Einstellungen -> System -> Display
2. Wir ändern nun folgendes:
- Display Farbtiefe erzwingen: `12 bits`
- Farbunterabtastung erzwingen: `4:2:2`

---

1. Wir gehen in CoreELEC auf Einstellungen -> System -> CoreELEC
2. Nun ändern wir folgendes:
- Use Player Led: `Ein`

===

==- Was muss ich tun, um alle Audio Codecs in Passthough abspielen zu können?

1. In CoreELEC gehen wir auf Settings -> System -> Audio Codecs
2. Wir ändern nun folgendes:
- Audio-Ausgabegerät: `ALSA: AML-AUGESOUND, HDMI Multi Ch PCM`
- Anzahl der Audiokanäle: `7.1`
- Ausgabekonfiguration: `Beste Übereinstimmung`
- Originallautstärke beim Downmix beibehalten: `Aus`
- Stereo Upmix: `Aus
- Audiogerät aktiv halten: `1 Minute`
- Durchschleifen erlauben: `Ein`
- Digitales Ausgabegerät für Durchschleifen: `ALSA: AML-AUGESOUND, HDMI`
- Dolby-Digital(AC3)-kompatibler Receiver: `Ein`
- Dolby Digital Plus(E-AC3)-fähiger Receiver: `Ein`
- DTS-fähiger Receiver: `Ein
- Dolby-TrueHD-fähiger Receiver: `Ein
- DTS-HD fähiger Receiver: `Ein`

===

==- Welches Plex Addon soll ich am besten nutzen?

Das Addon heißt `PlexMod`.  
Der Vorteil dieses Addons ist, dass es regelmäßig aktualisiert wird.  
Das offizielle `Plex` Addon wird nicht mehr aktualisiert und startet nicht mehr.

Hier findet ihr `PlexMod`:  
[PlexMod](https://forums.plex.tv/t/plexmod-for-kodi-18-19-20-21)

Hier wird beschrieben, wie man `PlexMod` perfekt einrichtet:  
[Kodi / CoreELEC Einstellungen](https://u3known.github.io/sb-wiki/appbox/plex-app-settings/)

===

---
