---
label: CoreELEC für Dune HD Homatics R 4K Plus / Homatics R 4K Plus / Nokia 8010
order: -2
icon: flame
---

# CoreELEC für Dune HD Homatics R 4K Plus / Homatics R 4K Plus / Nokia 8010

<h3>Was muss beachtet werden?</h3>

- Android TV mit `v5310 oder höher` für funktionierendes Dolby Vision.
- Dolby Vision muss in den Android-Einstellungen aktiviert sein.
- USB-Debugging muss in den Entwickleroptionen aktiviert sein.
- USB 3.0 Stick mit mindestens 16GB Speicher.

---

<h3>Downloads:</h3>

!!!info Info  
Die CoreELEC-Imagedatei mit der Endung `Generic.img.gz` ist erforderlich!  
!!!

[!file balenaEtcher](https://github.com/balena-io/etcher/releases/latest)
[!file CoreELEC 21](https://relkai.coreelec.org/?dir=Amlogic-ne/ce-21)
[!file remote](/static/remote.conf)

---

<h3>USB-Stick für CoreELEC vorbereiten:</h3>

1. USB-Stick an den PC anschließen. 
2. Starte das Flashtool `balenaEtcher`. 
3. `Flash from file` drücken und die CoreELEC-Imagedatei auswählen.
4. Drücke `Select target` und wähle den USB-Stick aus.
5. Drücke nun auf `Flash!`.
6. balenaEtcher führt automatisch einen Validierungsprozess mit einem `grünen Balken` durch.
7. Der USB-Stick ist nun geflasht.
8. Öffne die `COREELEC` Partition mit dem Explorer.
9. Kopiere die `remote.conf` in das Hauptverzeichnis.
10. Gehe nun in den Ordner `device_trees`.
11. Kopiere die Datei `sc2_s905x4_sei_smb_280.dtb` in das Hauptverzeichnis.
12. Im Hauptverzeichnis benennen wir die Datei `sc2_s905x4_sei_smb_280.dtb` in `dtb.img` um.
13. [!badge icon="warning" text="Kontrolle:"] Die Dateien `dtb.img` und `remote.conf` sollten sich im Hauptverzeichnis befinden.
14. Jetzt entfernen wir den USB-Stick vom Computer.

---

<h3>CoreELEC starten:</h3>

1. Nun stecken wir den fertigen USB-Stick in den `USB 3.0` Slot in die Dune HD Homatics R 4K Plus / Homatics R 4K Plus oder Nokia 8010
2. Jetzt starten wir CoreELEC, indem wir die `Ein/Aus Taste` der Fernbedienung lange gedrückt halten.
3. Jetzt klicken wir auf `Neustart`.
4. Nun startet `CoreELEC` und beginnt mit der automatischen Installation.
5. Wenn die Installation beendet ist, muss man durch den Einrichtungsprozess gehen.

---

<h3>Hilfestellungen:</h3>

==- Wie ist die Kompatibilität aller Codecs?

<h3>Video-Codecs:</h3>

{.compact}
| Codecs       | Unterstützung |
| ------------ | ------------- |
| H.264 (x264) | ✅            |
| H.265 (x265) | ✅            |
| MPEG-1/2     | ✅            |
| MPEG-4       | ✅            |
| VP8          | ✅            |
| VP9          | ✅            |
| VP9.2        | ✅            |
| AV1          | ✅            |

✅ = Unterstützung  

---

<h3>HDR-Codecs:</h3>

{.compact}
| Codecs          | Unterstützung |
| --------------- | ------------- |
| HDR10           | ✅            |
| HDR10+          | ✅            |
| HLG             | ✅            |
| Dolby Vision P5 | ✅            |
| Dolby Vision P7 | ✅            |
| Dolby Vision P8 | ✅            |

✅ = Unterstützung  

---

<h3>Audio-Codecs:</h3> 

{.compact}
| Codecs                      | Unterstützung |
| --------------------------- | ------------- |
| Dolby Digital (AC3)         | ✅            |
| Dolby Digital Plus (EAC3)   | ✅            |
| Dolby TrueHD & TrueHD Atmos | ✅            |
| Dolby Atmos                 | ✅            |
| Dolby Atmos (DD+ & EAC3)    | ✅            |
| DTS                         | ✅            |
| DTS-X                       | ✅            |
| DTS-HD                      | ✅            |
| Multi-PCM 5.1 & 7.1         | ✅            |

✅ = Passthrough  

===

==- Wie komme ich von CoreELEC zu Android TV?

1. Ihr müsst in das Neustart-Menü gehen.
2. `Reboot from eMMC/NAND` auswählen.
3. Nach ein paar Sekunden startet die Box neu, in das Android TV System.

===

==- Wie komme ich von Android TV zu CoreELEC?

1. Die `Ein/Aus Taste` der Fernbedienung länger gedrückt halten.
2. `Neustart` auswählen.
3. Nach ein paar Sekunden startet die Box neu, in das CoreELEC System.

===

==- Warum wird `Reboot from eMMC/NAND` nicht angezeigt?

Das liegt wahrscheinlich daran, dass man einen anderen Skin verwendet.  
Dies beheben wir, indem wir das `Neustart in Android TV` Addon installieren.  
[!file Addon](/static/reboottoandroidtv.zip)  

Einfach das `Addon` jedesmal ausführen, wenn ihr das Android TV Betriebssystem starten wollt. 

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
- Stereo Upmix: `Aus`
- Audiogerät aktiv halten: `Immer`
- Unhörbares Signal ausgeben: `Ein`
- Passthrough erlauben: `Ein`
- Digitales Ausgabegerät für Passthrough: `ALSA: AML-AUGESOUND, HDMI`
- Dolby-Digital(AC3)-kompatibler Receiver: `Ein`
- Dolby Digital Plus(E-AC3)-fähiger Receiver: `Ein`
- DTS-fähiger Receiver: `Ein`
- Dolby-TrueHD-fähiger Receiver: `Ein`
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
