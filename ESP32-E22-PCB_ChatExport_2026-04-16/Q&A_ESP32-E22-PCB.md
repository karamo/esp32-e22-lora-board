# Q&Q ESP32-E22 PCB  
Beginnend am 10 January 2025 aus Telegram exportierter Chat zur Entwicklung und Information zu ESP32-E22 PCB  

#### wolfgang z  
Alle Beiträge während der Entwicklung der PCB, also vor der endgültigen V2.1.2 wurden in der Telegram Gruppe im Thema #General belassen.  

#### wolfgang z, [13.11.2024 15:47]  
in der PCB V2.1.2 sind viele kleine Änderungen eingeflossen, die auch speziell nach einigen Chats mit DG4NEU Stefan und anderen Erwägungen entstanden sind.  
Aber grundsätzlich hat V2.1.2 die gleichen Grundfunktionen wie die Vorversionen, nur mit einigen wichtigen Erweiterungen:  
• Querformat für Outdoor (alle Ausgänge unten)  
• dementsprechend OLED um 90° gedreht einbaubar  
• erweiterte Stromversorgungsmöglichkeit  
ESP32-E22 Projekt - PCB V2.1.2  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2  
10:15  
#### wolfgang z  
Deep Links für einfacheren Zugriff auf die wichtigsten Unterlagen:  
Datenblätter u.a. der Key-Components  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/datasheet  
Schaltplan V2.1.2  
https://github.com/DK9BT/esp32-e22-lora-board/blob/main/ESP32-E22_V2.1.2/pdf/ESP32-E22_2.1.2_SCH.pdf  
Bestückungspläne und Gehäuseeinbau PCB V2.1.2  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/pdf  
Bestückungshinweise PCB V2.1.2  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/PCB-Assembly#best%C3%BCckungshinweise-pcb-v212  
10:22  
❗️Achtung: Die BOM (Bill Of Material = Stückliste) ist noch von V2.1.0 und daher nicht aktuell für V2.1.2 - bitte beachten! Ggf. in den Schaltplan schauen, was aktuell ist.  

#### ben, [14.11.2024 12:10]  
@wolfgang_zel Kann man da kein bestell.link machen wie bei aisler?  
#### wolfgang z, [14.11.2024 12:12]  
habe ich bei JLBPCB nicht gefunden.  
Aber bei anderen Herstellern ist das möglich.  
Ja, ich habe auch schon daran gedacht und werde das noch evaluieren.  
Aber die Key-Components und Kleinkram kann man ja schon mal bestellen bzw. überprüfen, was man schon hat, denn die haben tw. auch längere Lieferzeiten.  
Es gibt vieles Teile auch bei Reichelt und Amazon wenn man will.  
Einzelne Teile gibt es nur von Aliexpress (günstiger) ... und da ist auch Lieferzeit.  
Den Spannungsregler aber gibt's auch noch anderswo teurer, da ja weit verbreitet.  
Aber man kann auch alternativ einen teuren Recom DC/DC einbauen. z.B. eine Lieferquelle dafür:  
https://at.rs-online.com/web/p/schaltregler/1392959  
10:41  
#### ben, [15.11.2024 13:59]  
Achtung: die normalen E32 Nodemcu boards passen nicht, sind zu schmal...am besten einfach über den Amazon link bestellen...die teile passen dann  
10:42  
Stefan, [15.11.2024 13:28]  
In GitHub sind in der Galerie ein paar Bilder von meinem Node, da kann man den ESP ganz gut erkennen. War auch mal vor Jahren ne Packung von AZ-Delivery im Angebot bei Amazon.  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/gallery/DG4NEU_Stefan  
Inzwischen bevorzuge ich Aliexpress, die Preise sind dort extrem besser und die Herkunft vermutlich die gleiche. Meine Vorliebe für lokale Lieferanten hab ich angesichts dieser Unterschiede mal hintenan gestellt und hab dafür ein bisschen Geduld für die längere Lieferzeit.  
10:43  
Wolfgang Hallmann DF7PN, [15.11.2024 13:41]  
Ich haben noch eine Frage zu der Liste wegen dem OLED:  
Da steht drinn: OLED-Display (VCC-GND-SCL-SDA)  
Ist diese Reihenfolge der Pins genau so einzuhalten, oder ein Tippfehler?  
Ich habe bisher nur solche OLEDs gefunden wo die Reihenfolge: GND-VCC-... verfügbar ist. Also die beiden Pins vertauscht.  
Arg, der amazon link zeigt auf ein teures aber mit Pin-Anordnung wie in der Liste. Die Ali Teile sind viel günstiger aber haben VCC/GND vertauscht.  
Stefan, [15.11.2024 13:43]  
Ja, die OLEDs gibt es in beiden Versionen, auf der Platine ist aber vorgesehen, die Pins zu "tauschen". Ich würde allerdings nach den passenden Displays schauen. Einige Ausführungen erlauben auch ein Tauschen der Belegung durch Brücken auf der OLED-Platine. Dann stimmt aber die Beschriftung nicht mehr.  
Beim Ali muss man sehr genau hinsehen, dass man die Richtigen bestellt/bekommt. Zur Not eben die Platine anpassen.  
https://de.aliexpress.com/item/1005006425021544.html  
Das hatte ich letzt bestellt, die passen und sind günstig, wenn man nicht nur eins bestellt.  
10:44  
#### wolfgang z, [15.11.2024 14:10]  
1️⃣ Ja, die OLED gibt es in grundsätzlich 2 verschiedenen Pin-Anordnungen. Die angegebene (VCC-GND-SCL-SDA) ist bereits auf der PCB verdrahtet.  
Fall man VCC <> GND umdrehen möchte, dann sind auf der Rückseiten 2 Leiterbahnen zu unterbrechen und 2 Drahtbrücken herzustellen.  
Wer will, kann bei JP1 & JP2 Pfostenstecker einbauen (auf der Rückseite) und Jumper verwenden.  
10:48  
Stefan, [15.11.2024 15:28]  
Du musst nur aufpassen, wenn du den E22 anschließt, der zieht zu viel Strom. Bis dahin solltest du auch die 5V-Versorgung bestücken.  
10:48  
Neee, wenn ich ein geeignetes USB-Netzteil verwende, dann funktioniert das. Z.B. von einem RPi.  
10:50  
Wolfgang Hallmann DF7PN  
Danke für die Mühe das hier in diesem Stream zu sammeln!  
10:55  
#### wolfgang z  
Stefan, [15.11.2024 15:30]  
Nicht über den ESP, dann bricht beim Senden die Spannung ein und der macht einen Reboot. Hier getestet.  
Hilft nur, die Sendeleistung runterzunehmen.  
#### wolfgang z, [15.11.2024 15:31]  
Nein, das sollte nicht so sein, denn der 5V-Pfad geht durch an die Steckerleiste und am E22 ist deswegen auch noch der große Elko. Sollte also funktionieren, Aber ich werde es n.W. sehen bzw. auch messen.  
Am ESP32-DevKitC-V4 ist zwischen USB und Stiftleiste nur die eine D3 Schottky-Diode im Pfad. Also meine ich, dass es gehen sollte.  
Denn wie ich schon vor einiger Zeit das Thema der Schutzdioden thematisierte, und auch wie zuvor gezeigt:  
USB-Netzgerät > µ-USB am ESP32 > BAT760-7 > Stiftleiste > E22  
Für Strom-Spikes ist der Elko + 100nF Kerko direkt am E22 vorgesehen.  
Ich sehe da kein Problem.  

11:07  
und wie man sieht, sind am ESP32-DevKit-V4 die +5V links unten gleich neben der USB-Buchse, also keine langen Leiterbahnen, wo ein nennenswerter Spannungsabfall entstehen könnte.  
11:08  
Die beiden bisherigen getesteten Käfer  
11:09  
#### wolfgang z, [15.11.2024 15:49]  
ja, haben offensichtlich gleiches Pinning und gleichen Pin-Abstand.  
11:10  
5 Stk um ≈35€  
https://www.amazon.de/dp/B08BZFW41S  
11:18  
#### ben, [15.11.2024 16:32]  
Also um Klarheit wegen der Spannungsversorgung zu bringen....ein "dummes" ("starkes") 5V Netzteil am ESP32 kann auch den E22 mitversorgen...hab ich getestet....ein intelligentes Netzteil schafft aber evtl. nur 500mA. ...die Peaks aber "könnten" ggf. von Elko (am E22) abgefangen werden...ansonsten haben wir für intelligente Netzteile eine USB-C Buchse vorgesehen die wegen der 5.1k Beschaltung die 5V/2A dann auch liefert.  
#### wolfgang z, [15.11.2024 16:34]  
kleine Korrektur und Klarstellung: 5k1 bedeuten 5V/3A  
(5k1 = 5,1 kΩ Widerstand 2 Stk. bei der USB-C Buchse)  
...  
oder auch einen DC/DC, der 5V/3A liefern kann und mit höherer Eingangsspannung zurecht kommt.  
Wolfgang Hallmann DF7PN, [15.11.2024 16:45]  
wird dann umgekehrt über die USB-C Buchse der ESP32 mit versorgt?  
#### wolfgang z, [15.11.2024 16:47]  
JA, ALLE Varianten sind möglich!  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2#erl%C3%A4uterung-zur-schutzbeschaltung  
11:28  
@dg2rbf hat der externe Button irgendeine Funktion?  
@DG4NEU hast du den Button am ESP32-E22 verwenden können, nachdem du ihn aktiviert hast?  
Stefan, [16.11.2024 11:15]  
Sorry: Korrektur, gerade noch mal probiert, er schaltet zwischen den einzelnen Messages durch.  
11:55  
#### wolfgang z  
#### wolfgang z, [17.11.2024 14:23]  
ESP32-E22-Projekt  
Ich habe die Idee, einen eigenen Power-Switch auf das Board zu platzieren. Den könnte man direkt bestücken oder auch über Drähte ans Gehäuse führen. Dabei stellt sich die Frage: "In welchen Strompfad einbauen?"  
1️⃣❓der DC/DC hat ja einen EN-Eingang, an dem man ihn abschalten kann. Das wäre eine ganz einfache Möglichkeit, einen Power-Switch einzubauen. Das würde aber nur bei Versorgung über die Schraubklemme + DC/DC wirken.  
2️⃣❓ich könnte dann aber auch "nach" dem (+) von C6 einen Schalter einbauen. Das würde zusätzlich für die Versorgung über die USB-C wirken.  
3️⃣❓ABER: wenn man den ESP32 versorgt, dann kann man den nicht irgendwie ausschalten, da es ja über seine eigene USB läuft.  
11:55  
Ok, dann habe ich mich für die einfachste Variante 1️⃣ entschieden und nur einen Jumper mit einer Leiterbahn mit dem EN-Pin des DC/DC verbunden. Offen = EN, geschlossen = OFF (nur mit dem DC/DC-Wandler)  
12:33  
#### wolfgang z  
#### wolfgang z, [19.11.2024 11:08]  
😭 Ein Einzelentwickler, so wie ich, hat gerade gestern ein E22-Modul "irrtümlich" (eben wegen dieses Spieltriebes) zerstört. Daher ist die endgültige Inbetriebnahme meines ESP32-E22-Boards leider verzögert worden.  
Ich "wahnsinniger" od. "ehrgeiziger" wollte das E22 nicht direkt auflöten sondern sockeln. Dabei ist die mechanische Spannung zwischen E22-Modul-Lötstellen, die nur Halblöcher sind, offenbar zu groß gewesen und es gab offensichtlich Leiterbahnunterbrechungen am E22.  
Es kam einfach der Fehlercode -2 bei der Initialisierung von MeshCom.  
Leider war nicht der Sockel das Problem, sondern MeshCom unterstützte den E22-900 nicht. Hätte wahrscheinlich eh noch funktioniert.  
Zur Unterstützung des E22-900 (für 868MHz) kommen wir noch. ...  

Wenn schon defekt, dann gleich mal öffnen. So sieht ein E22-fffMxxS innen aus.  
12:36  
Stefan, [19.11.2024 11:41]  
Der Nachteil der (irgendwie-) Sockellösung ist natürlich die fehlende "Bodenhaftung", da müsste man ein dickeres Wärmeableitpad druntersetzen. Bisher allerdings ist die Temperatur des E22 bei mir noch kein Problem gewesen.  
#### wolfgang z, [19.11.2024 11:42]  
Es ist dann so viel "Bodenabstand", dass man einen kleinen Kühlkörper unten auf das E22-Modul kleben kann, wie man solche auch beim RPi, Motortreibern u.ä. verwendet.  
12:42  
Das Problem mit dem E22-900 ... wird hier abgehandelt  
https://t.me/c/1987218802/1/10025  
und in anderem Thema weiter ausgeführt ...  
#### wolfgang z, [22.11.2024 13:10]  
@oe1kbc bez. ESP32-E22 Projekt:  
Das PCB mit der FW MeshCom  
✅ funktioniert mit einem E22-400M30S Modul  
aber  
❌ NICHT mit einem E22-900M30S Modul  
wo ist da der BUG?  
Der Unterschied ist offenbar, dass  
E22-400... = SX1278  
E22-900... = SX1262  
https://www.cdebyte.com/products/E22-900M30S  
SX1268 !!!  
https://www.cdebyte.com/product_serch/E22-400M33S/1/  
12:50  
Helmi Beh  
Du musst dich mal mit der Adressierung des I2C-Busses beschäftigen. Das LSB ist das R/W-Bit. Wenn man das nicht berücksichtigt (7bit-Adresse) kommt 0x3C heraus. Wenn man das berücksichtigt (Shift left), wird's dann zu 0x78!  
12:55  
#### wolfgang z  
#### wolfgang z, [25.11.2024 21:39]  
Kurze Info zur PCB V2.1.2  
1️⃣ Ich habe mal eine variants.h für Meshtastic erstellt, selbst kompiliert und läuft offenbar problemlos.  
2️⃣ Der Button funktioniert mit MeshCom ordentlich, aber mit Meshtastic nur sporadisch. Ein PullUp kann das Problem nicht lösen, da GPIO12 = strapping Pin  
3️⃣ Es könnte ja sein, dass man eine LED auf dem PCB haben möchte. Dafür würde sich GPIO2 anbieten.  
4️⃣ Es könnte auch sein, dass man einen Buzzer (Signalgeber) auf dem PCB anschließen möchte. Auch dafür muss noch ein geeigneter GPIOxx gefunden werden.  
Stefan, [25.11.2024 21:43]  
Zu 4: Buzzer finde ich gut, hab das beim T-Deck zu schätzen gelernt. (So lange man den auch abschalten kann😀)  
#### wolfgang z, [25.11.2024 21:49]  
leider hatte das bislang niemand zur Sprache gebracht, sonst hätte ich das vorgesehen.  
Ich hatte aber auch nicht genau das DevKitC-V4 Board angesehen. Das hat leider keine OnBoard-LED, wie viele andere Boards sehr wohl.  
Stefan, [25.11.2024 21:55]  
Bisher sehe ich das e22-Board für mich eher als Gateway, daher ist mir das gar nicht so wichtig. In der Firmware vorgesehen, wäre das aber für die anderen Boards sinnvoll. LED oder Buzzer bei eintreffenden DM z.B.  
13:02  
Ein neues ESP32-Board:  
#### ben, [21.11.2024 23:55]  
ESP32-S3 N16R8 2,4G Wifi Modul Entwicklung Board für Microphython ESP IDF 8 MB PSRAM 16 MB FLASH WS2812 LED CH340 Typ-C ESP32 S3 - AliExpress  
https://de.aliexpress.com/item/1005006413972573.html  
DUBEUYEW 3PCS ESP32-S3 ESP32-S3-DevKitC-1 N16R8 WiFi-Modul + 5.0 Bluetooth Internet Development Board 16M Externe Flash-Erweiterung 8M PSRAM mit einem Typ-C-Kabel (gelötet) https://amzn.eu/d/dfaFvCY  
Wir hatten neulich mal die Diskussion das ESP32 mit mehr flash besser wären wegen OTA Update  
#### wolfgang z, [25.11.2024 21:46]  
Das ESP32-S3-WROOM-1-N16R8 Board habe ich jetzt auch und festgestellt, dass  
1️⃣ das Board nochmals um 3 Pins länger ist,  
2️⃣ eine andere Pinbelegung als das derzeit verwendete ESP32-DevKitC-V4 hat.  
ad 1️⃣ es wäre grundsätzlich möglich, den gleichen Formfaktor der Platine beizubehalten, dh. ins gleiche Gehäuse passend.  
ad 2️⃣ ein Redesign (routing) ist damit erforderlich.  
14:58  
#### wolfgang z  
zu GPS nur wenig Text hier und entsprechende Links, zu viele Beiträge.  
Besser: ein solches Board, Antenne und Chip als Einheit mit Kabel an die Platine gesteckt.  
Für die GPS-Antenne ist "rechts oben" neben der SMA-Buchse die Platine ausgespart. Da ist Platz im Gehäuse, die Antenne parallel zur Seitenwand anzubringen.  
https://t.me/c/1987218802/1/10231  
https://t.me/c/1987218802/1/10233  
https://t.me/c/1987218802/1/10259  
https://t.me/c/1987218802/1/10271  
https://t.me/c/1987218802/1/10308  
https://t.me/c/1987218802/1/10558  
15:00  
Zu den in der Anfangsphase erwähnten und verfügbaren 3D-PDFs.  
4) Ja, 3D-PDF gab es. Habe ich aber wieder entfernt, da  
1. veraltet und  
2. nicht wirklich angekommen wurden bei "euch" und  
3. ein nicht unerheblicher aufwand, die zu erstellen. 😉  
15:17  
#### wolfgang z  
Stefan, [23.12.2024 16:36]  
Einbaubuchse für die Versorgung des E22/ESP32-Boards:  
rot/schwarz = VCC/GND  
blau/weiß = D+/D-  
grün/gelb = CC1/CC2  
Ist ein Ersatz der USB-C-Buchse auf dem Board, um bei Indoor-Verwendung die Buchse im Gehäuse einzubauen. Damit ist auch sichergestellt, dass USB-PD funktioniert.  
https://de.aliexpress.com/item/1005006564841844.html  
Man muss halt die richtige "Farbe" auswählen,... 😉  
Die Buchse ist an und für sich wasserdicht, wenn man sie ordentlich einklebt, aber für einen dauerhaften Outdoor-Einsatz nicht wirklich geeignet.  
„Farbe: 6P“  
15:17  
Bilder vom Aufbau von Andre DL4QB  
https://t.me/c/1987218802/1/10751  
https://t.me/c/1987218802/1/10854  
https://t.me/c/1987218802/1/10877  
https://t.me/c/1987218802/1/10882  
15:42  
#### wolfgang z  
Suitbert, DF2PI, [05.01.2025 18:29]  
Einbau GPS-Board und GPS-Antenne in OE3WAS-Meshcom-Trcvr: wer eine mechanische Lösung hierfür sucht, darf sich hier gerne bedienen: https://www.printables.com/model/1135886-montagebrucke-interne-gps-antenne-gps-board-fur-me vy 73, Suitbert, DF2PI 😀  
15:51  
#### ben, [06.01.2025 20:55]  
...übrigens wärmeleitpaste unter den E22 in geringen! Mengen macht sinn...hab irgendwo was von doppelseitigem Klebeband gelesen...lieber Paste  
#### wolfgang z, [06.01.2025 20:56]  
dafür ist auch die größere Bohrung in der Mitte da, um die auch nachträglich noch reindrücken zu können!  
15:52  
Wolfgang Hallmann DF7PN, [06.01.2025 19:21]  
Ich habe heute diese Kabel bekommen USB-C mit D+/- und Cc1/2. Ich messe die mA mit einem USB Adapter und sehe beim Senden mit einem doofen 3A/5V Steckernetzteil beim Senden mit 22 dBm nur max. 0,8 A . Nehme ich eins mit PD Gedöns für CC dann sinds nur 200 mA.  
Da würde ich sagen das mit dem CC Signal tut nichts signalisieren. Noch dazu frage ich mich wenn normal 0,8A gebraucht werden, da 3A Netzteile angeraten werden? Hat jemand Erfahrungen mit der CC Steuerung?  
#### wolfgang z, [06.01.2025 20:18]  
Nein, natürlich nicht!  
Das E22...30 mach ja nur 30dBm und das sind 1W.  
Ich habe folgende max. Ströme genommen von:  
• E22 ... -33 = 2W  
• ESP32  
• OLED  
• GPS !!!  
• und etwas für die Sensoren.  
Das ist die EINE Seite bzw. Sicht der Dinge.  
Damit, dass die nominellen 500mA zu wenig sind, weil der E22 max. 650mA schon alleine benötigen kann und wir daher auf das Maximum der USB-C bei 5V gegangen sind. Das sind eben 3A.  
Auf der anderen Seite ist es so, dass USB-C Netzteile ohne 5k1 nur 500mA nominell liefern dürfen. Aber die 500mA sind definitiv zu wenig. Daher auf den max. Level der USB-C 5V, der "überall" verwendet wird: 5k1 = 3A  
Es ist sinnlos, irgendwelche anderen Widerstände zu berechnen, wenn "alle" die 5k1 nehmen. Diese 3A sind aber auch der max. Strom bei 5V.  
Die "normalen" Netzteile dürfen nur 5V/500mA liefern.  
ABER: Wenn man nur ein Netzteil mit USB-A Buchse hat, dann muss es eines für USB-3.0 (blauer Stecker) sein, wie zB. für den RPi. Diese haben KEIN Power Delivery und in so einem Fall geht auch ohne der 5k1-Widerstände ausreichend Strom rüber.  
Die max. Stufe bei USB-C 5V sind eben die 3A.  
Dass dann u.U. auch ein 2A-Netzteil ausreicht, dass kann schon sein.  
Dass real weniger Strom benötigt wird, das kann auch sein.  
Ben hat das mit den 5k1 damals gefunden und ich habe mich dann sehr lange und ausgiebig mit der USB-C PD Thematik beschäftigt. Es passt alles, so wie es ist.  
Wenn es nicht passen sollte, dann ist es ein unpassendes Netgerät u/o ein inkompatibles USB-C Kabel!  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/PCB-Assembly#22-versorgung-%C3%BCber-usb-c  
#### ben, [06.01.2025 20:57]  
...und wenn man das board extern mit spannung vesorgt dann am einfachsten über pg verschraubung und nem externen Netzteil.....usb-c war eher zum testen aufem Schreibtisch gedacht...wenn der node im Freien hängt macht ja auch 5m USB Leitung keinen Sinn  
15:53  
Um den Strom wirklich real messen zu können, muss man einen Shunt in die Versorgung einfügen und darüber mit einem Oszi die Spannung, woraus sich dann der Strom errechnen lässt. I = U/R  
Alle anderen "Messgeräte" sind da unbrauchbar, da kurzzeitig höhere Ströme fließen können.  
15:56  
❌ Einen BME 5V von der 5V der Stiftleiste des ESP versorgen ...  
#### wolfgang z, [09.01.2025 00:22]  
Das solltest du nicht machen!  
Das könnte tödlich für den ESP32 werden!  
Denn bei 5V-Versorgung sind auch die Datenleitungen dann 5V und das verträgt der ESP32 NICHT !!!  
lies das mal:  
https://t.me/c/1987218802/9026  
20:42  
#### wolfgang z  
Warum wollte ich den E22 sockeln?  
Um eine Adapterplatine an Stelle des E22 aufstecken zu können.  
Darauf sind +5V / +3,3V / GND / I²C / SPI verfügbar, um z.B. Sensoren o.ä. zu testen.  
Und für Messaufgaben mit mehreren Sensoren scheiden MeshCom & Meshtastic sowieso aus. Da ich in diesem Fall aber meistens auch kein LoRa benötige, reicht das WiFi vom ESP32 völlig aus.  

20:48  
Wolfgang Hallmann DF7PN, [30.11.2024 17:37]  
Ich stelle gerade die Kleinteile zusammen für unseren Workshop: Da stellt sich mir eine Frage. Wenn ich innen eine USB-C Buchse habe, sollte auch ein Stecker durch die Gehäusewand gehen. Die empfohlenen Kabelverschraubungen erlauben aber nicht den Durchmesser, den ich bräuchte um einen Stecker durchzubekommen. Wie war das mal gedacht, dass das gehen soll?  
#### ben, [30.11.2024 17:43]  
Du brauchst den usb c stecker net unbedingt  
Geht auch direkt mit 5v  
Wolfgang Hallmann DF7PN, [30.11.2024 17:50]  
Doch ich will 😉 Ne alles gut habe eben einen größere Kabelverschraubung 13,5 gefunden. Da passt der ganze USB-C Stecker durch. Im Durchgang muss man halt das Kabel etwas dicker machen durch Isoband oder Aussenhülle von nem RG58.  
Andere Stecker die ich da reinführen soll, sind auch nicht viel schmaler.  
Bei unserem Bausatz lasse ich die Kabelklemme und den DC/DC Wandler weg.  
Da wäre ich nur mit einem Kabel reingegangen.  
ahja, diesen DC/DC Teil lassen wir weg. Kann sich einbauen wer mag.  
#### wolfgang z, [01.12.2024 10:58]  
❗️Ich habe viele Möglichkeiten vorgesehen. Man kann einiges weglassen, wenn man weiß, was man tut. Aber man sollte auch die Schaltung verstehen.  
Zusätzlich, was noch in der Doku noch nicht so genau beschrieben ist:  
1️⃣ Schraubklemme kann verwendet werden, auch ohne DC/DC, dann Drahtbrücke einbauen.  
2️⃣ Sicherung F1 & Diode D5 müssen nicht verwendet werden, können aber.  
3️⃣ Auf die Stiftleiste J2 kann eine USB-C Einbaubuchse angesteckt werden.  
20:49  
z.B. die 6-polige (VCC GND CC1 CC2 D+ D-), wobei die Belegung offenbar von Stefan gefunden wurde. Siehe zuvor.  
20:50  
es kann auch sein, dass die 5-polige (VCC GND CC D+ D-) funktioniert. Davon habe ich eine Belegung gefunden. Wahrscheinlich gemeinsames CC, also CC1-CC2 verbunden, was aber zu dem bekannten RPi-Problem führt.  
20:50  
#### wolfgang z, [01.12.2024 11:10]  
❌ Die 2-poligen (nur VCC & GND) und die 4-poligen (VCC & GND & D- & D+) funktionieren aber definitiv NICHT, da die CC1 & CC2 Anschlüsse fehlen und daher von dem USB-C Netzteil nur 5V/500mA bereitgestellt werden darf, außer ev. Ausnahmen, wenn man "dumme" Netzteile u/o "dumme" USB-C Anschlusskabel verwendet.  
21:01  
Andre fragte nach "Remote-Steuerung"?  
#### wolfgang z, [19.12.2024 10:58]  
Ja, es gäbe die Möglichkeit, Geräte via LoRa zu steuern.  
Mir ist dabei auch aufgefallen, dass nicht mal RT/TX auf eine Stiftleiste herausgeführt ist, was aber durchaus sinnvoll gewesen wäre.  
Dies und noch andere sinnvolle Ergänzungen wird es in einer ev. Nachfolgeversion geben.  
Kurt Baumann OE1KBC, [19.12.2024 11:25]  
Diese Idee ist sicherlich eine Überlegung wert. Derzeit können mit dem I2C angebundenen MCP23017 16-I/O-Pins gesteuert bzw. abgefragt werden. Diese Platine ist auch im WEBClient im vollem Umfang mit Beschriftung der PINS usw. ab Version 4.33c integriert.  
https://icssw.org/2024/06/16/meshcom-mcp23017-16-pin-i-o/  
Via der MCP23017 kann auch eine Relaisplatine angesteuert werden um größere Ströme zu schalten.  
Ich verwende derzeit die 4-fach SolidState-Relay-Platine von AZ-Delivery.  
Ich würde sagen mit den derzeitigen vorhandenen Möglichkeiten lässt sich eine REMOTE-Gerätesteuerung bzw. Fernabfrage einfach aufbauen. Die Schaltfunktionen sind auch via MeshCom-Meldungen schaltbar. Eine einfach passwort-Kontrolle ist bereits inkludiert.  
21:02  
Kurt Baumann OE1KBC, [19.12.2024 11:33]  
Hier ein Bild des Laboraufbaus.  
Wild aber es funktioniert .. habe es auf der HAMRADIO vorgestellt.  
Auf dem orangefarbenen Board ist ein Pegelkonverter aufgebaut.  
 
20 January 2025  
Stefan  
Das sollte auch ohne eine Anleitung kein Problem sein, mit Platine, den Bauteilen, Bestückungsliste und Schaltplan klappt das gut. Bei Fragen dazu, einfach hier melden. 😊  
15:47  
Ben  
und:  
15:47  
https://md.freifunk-mwu.de/s/7OQwy7e9F  
👍  
15:53  
Stefan  
Könnte André DL4QB vll auf seiner Seite verlinken!  
15:57  
Juergen DF2AP  
Top 👍 Super herzlichen Dank 😊  
17:44  
#### wolfgang z  
Kannst du auch auf GitHub nachlesen. Ich habe alle wichtigen Informationen gegeben. Brauchst nur lesen und etwas Elektronik-Verständnis. 
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/PCB-Assembly  

1 February 2025  
10:23  
Juergen DF2AP  
Guten Morgen. Wie habt Ihr bei Euch die Stromversorgung gelöst? Schraubkkemmen, USB-C Breakout-Board oder direkt an den ESP32? Falls jemand USB-C-Breakout nutzt, gibt es einen Link für ein vierpoliges Kabel um die USB-C-Buchse nach außen zu führen?  
10:25  
Stefan  
Schau mal weiter oben, dort ist der Link für das 6-Polige Kabel. Das funktioniert prima. Aktuell habe ich einfach über 5V-Schraubkkemme versorgt.  
10:27  
Juergen DF2AP  
Danke Stefan. Hast Du das HW-613 Modul verbaut oder speist Du einfach 5V fest ein?  
10:29  
Kann man als Sicherung auch so eine selbstrückstellende Sicherung bei F1 einbauen? Die kleinen Glassicherungen scheint es nur im 1.000 er Pack zu geben.  
10:30  
Stefan  
Bei mir hängt die 5V-USV dran, die über USB an nem kleinen Netzteil. Bilder dazu im Github  
10:30  
Sollte auch gehen! Gute Idee. Nur sind 5A etwas heftig, 3A müsste reichen  
10:31  
Juergen DF2AP  
Die Dinger sind etwas größer. Sollten aber neben den Elko gut passen.  
10:32  
Würde so aussehen  
10:33  
Hab die 5 A Variante bestellt.  
10:33  
Stefan  
Sollte die Diode aushalten... 😉  
10:35  
Juergen DF2AP  
Du hast so ein Montagekreuz aus dem 3-D Druck drunter. Korrekt?  
10:35  
Stefan  
Ja, das hält auch das GPS-Antennchen fest.  
10:35  
Juergen DF2AP  
Was ist das für eine USV?  
10:37  
Stefan  
https://de.aliexpress.com/item/1005006860598580.html  
10:38  
Hält mit 2x3400mAh-Akkus recht lange durch und kostet wenig.  
11:05  
Juergen DF2AP  
Was es nicht alles gibt. Das wird ja doch ein Riesen Projekt 😂👍  
11:26  
Stefan  
Hast du einen 3D-Drucker in Reichweite?  
13:55  
Wolfgang Klein  
Stefan die 5V Variante oder die 12V-Variante?  
14:11  
Wolfgang Klein  
Und kann man die STL-Datei bekommen?  
14:38  
Stefan  
Ich hab die 5V-Variante etwas "verbessert", so dass die 5,3V ausspuckt. Wird ein SMD-R getauscht. So kann man die Ohne Sendeleistungsverlust an de E22 anklemmen.  
14:39  
Kannst du gerne ha#### ben, muss die mal suchen. Ich hatte verschiedene Varianten, die Finale war die mit GPS-Antennen-Halterung.  
14:44  
Wolfgang Klein  
Super Danke! Und hast Du noch einen Tip für die 3400mAh Akkus? Bin da etwas vorsichtig wegen Fakeangaben  
14:48  
Stefan  
Da passen alle 18650 FlatTop rein, es reichen auch 3000er aus. Die brauchen auch nicht "geschützt" sein, darum kümmert sich die USV.  
14:59  
Wolfgang Klein  
wenn du einen Bestelllink hättest?  
15:06  
Stefan  
Ich hab meine bei Akkuman bestellt, bin bisher zufrieden:  
https://www.akkuman.de/shop/10x-Tenpower-INR18650-32HE-36V-Li-Ion-3100mAh-10A-Entladestrom  
15:08  
Aber bitte beachten, dass die Zellen kein BMS ha#### ben, sollten also nur für T-Beam, die USV etc. verwendet werden!  
15:10  
Wolfgang Klein  
LED Lampen sollten auch gehen, Danke schaue ich mir mal an  
15:11  
Stefan  
Nur, wenn die ein BMS ha#### ben, sonst ist davon abzuraten. Normale Taschenlampen zum Beispiel haben keinen Schutz gegen Tiefentladung.  
15:28  
Juergen DF2AP  
An den STL-Dateien hätte ich auch Interesse. Hab jemanden in der Nähe, der 3D-Druck machen kann.  
16:38  
#### wolfgang z  
4-polig geht NICHT - siehe GitHub!  
16:40  
Nein, gibt es auch 10 Stk z.B. man muss nur mal suchen.  
16:42  
https://www.amazon.de/dp/B083R44LKT  

#### wolfgang z  
Der Elko C2 lins obere Ecke des ESP32 ist völlig unnötig! Siehe GitHub!  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/PCB-Assembly#98-weitere-hinweise  
19:14  
❓Warum lötet ihr Bauteile ein, die ich nicht beschrieben habe, dass sie eingelötet werden sollen?  
❗️Kaum jemand weiß, was es mit diesem ADC-Eingang für eine Bewandtnis hat.  

19:19  
#### wolfgang z  
Alles, was ich hier nicht beschrieben habe, das sind Spezialfälle und dabei sollte man wissen, was man tut!  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/ESP32-E22_V2.1.2/PCB-Assembly#best%C3%BCckungshinweise-pcb-v212  

#### wolfgang z  
Der Elko link soben schadet grundsätzlich nicht, aber er verlängert in unnötiger Weise den RESET-Vorgang und das könnte in speziellen Versorgungsspannungssituationen zu Fehlfunktionen führen. Ich empfehle, den nicht einzulöten!  
Der war nur für die "alten" ESP32-Board tw. erforderlich bez. des Flash-Vorganges.  

❗️Nochmals bez. der beiden Widerstände R1 & R2:  
Die stellen einen Spannungsteiler dar und sind mit einem ADC-Eingang verbunden, um externe Spannungen messen zu können, z.B. die Batteriespannung, dann muss man noch eine externe Verbindung herstellen zum Akku o.ä.  

Leider habe ich da einfach die Widerstände kopiert und daher sind deren Wert jeweils 5k1. Das ist natürlich für eine Spannungsquelle eine gewisse Belastung. Bei 5V ≈0,5mA  

Spannungsteiler ist so zu dimensionieren, dass aus der Maximalspannung maximal 3.3V werden  .

#### wolfgang z  
Der Spannungsteile ist von mir 2:1 gewählt worden, da ich davon ausgehe, auch ≈5V messen zu können und somit der ADC-Eingang nicht "am Anschlag" steht.  

19:46  
#### Ben  
The ESP32 includes two 12-bit SAR ADCs – ADC1 and ADC2 – and supports measurements on 18 channels (analog-enabled pins). ADC1 is available on eight GPIOs (32 to 39), while ADC2 is available on ten GPIOs (0, 2, 4, 12 to 15 and 25 to 27).  

wir müssten das aber konfigurierbar machen...also den teiler  
der eine will 13.8V messen..der nächste nur 5V...  
oder wir einigen uns auf nen spannungsteiler und stellen das fix ein  
19:52  
Stefan  
Das würde ich vorschlagen, 0-20V, das ist von der Genauigkeit dann noch ausreichend.  
 
#### Ben  
ofiziell haben wir 5.1k/5.1k -> da sind dann maximal 6.6V messbar  

#### wolfgang z  
Ja, das war meine Idee bez. der gleichen Widerstände.  

#### Ben  
aber ich würde gut finden das wir 13.8 mindestens auch noch messen können....wir haben ja den step down wandler jetzt auch drinnen  

#### wolfgang z  
dann ganz einfach einen "Verstärkungsfaktor" und einen "GPIO pin" frei einstellbar lassen.  

#### Ben  
bei 100k/22k könnten wir 18,5V messen  

#### wolfgang z  
Verstärkungsfaktor bzw. Kalibrierungsfaktor.  
Damit kann man die Genauigkeit noch erhöhen wegen der verschiedenen Toleranzen.  
19:58  
Ben  
@DG4NEU : bist du grade am rechner? könnte dir ne testversion schnell machen  
19:58  
Stefan  
Nee, leider gerade nicht, kann nachher noch mal gucken.  
19:59  
#### wolfgang z  
macht mal wer ein Issue [Enhancement] für den ADC-Pin und den Kalibrierungsfaktor.  

#### 2 February 2025  
12:23  
Stefan  
hier noch der Ali-Link für die  
Einbaubuchse für die Versorgung des E22/ESP32-Boards:  
rot/schwarz = VCC/GND  
blau/weiß = D+/D-  
grün/gelb = CC1/CC2  
12:23  
https://de.aliexpress.com/item/1005005605959202.html  
3 February 2025  
11:38  
Ben  
Flex USB Kabel zum flashen  

7 February 2025  

13 February 2025  
13:43  
Juergen DF2AP  
Kurze Frage zum Einbau von U4 HW613. Der muss ja unter das OLED-Display? Ich hab dem Ding eine Stiftleiste verpasst. Passt da noch eine 4er Buchse auf die Leiterplatte oder habt ihr die Stiftleiste direkt eingelötet?  
13:52  
Stefan  
Die Platine ist so designed, dass der auch stehend eingebaut werden kann. Ich würde das nicht mit Stiftleisten oder Buchsenleisten machen, sondern mit starren Drähten fest einlöten. So findet er auch unter dem Display Platz, sonst wird das zu eng. Und unter das Modul eine Isolierung anbringen, damit es nicht direkt aufliegt. Z.B. mit doppelseitigem Klebeband.  

#### wolfgang z  
einfach so wie du es mit der Stiftleiste bestückt hast von unten durchstecken:  
16:17  
NEIN - ist nur marginal höher als die fette Diode  
17:58  
Juergen DF2AP  
Super Danke. Spannung hab ich auf 5,3V eingestellt. Dann rein damit 👍  
18:01  
So richtig?  
18:31  
#### wolfgang z  
Ja, genau so! Passt  
18:55  
Juergen DF2AP  
Danke Wolfgang 👍  
14 February 2025  
20:12  
Andreas Frank  
Hallo, ich habe eine Frage zur Einstellung der Sendeleistung. Bei meinen beiden Nodes kann ich nur 17 dBm einstellen, obwohl diese mehr könnten. Mache ich da was falsch? Danke für die Antworten. VG Andreas  
20:17  
Stefan  
Du machst nix falsch, die PA im E22 ist noch nicht passend in der Software/FW berücksichtigt. Daher einfach Maximum einstellen, bzw. auch weniger, wenn die volle Leistung nicht benötigt wird.  
20:38  
Rainer OE1KFR  
Sofern du die App meinst ist das ein Bug, den ich gestern behoben habe -> please wait for next Release. Bitte per seriell einstellen. In der App wird in Zukunft nur mehr die Base Power des Chips ausgewählt, die Verstärkung der PA ist dann selbst zu berücksichtigen  
22:07  
Ben  
22db musst du im web-if einstellen dann passt es  
22:07  
In echt kommen dann 33db raus  
22:09  
Andreas Frank  
Hallo, wenn ich das mache und das Web-Interface aktualisiere stehen die 17 dBm wieder dort.  
22:09  
Ben  
Hast du die app benutzt oder nur das web if?  
22:10  
Screenshot (14.02.2025 22:10:29)  
22:10  
So solls aussehen beim e22  
15 February 2025  
08:47  
Stefan  
Hast du den E22/ESP32-Bausatz oder einen anderen Node? Das oben Beschriebene gilt nur für diesen, nicht für T-Beam oder so.  
09:05  
Andreas Frank  
Hallo Stefan, ja, ich habe ein T-Beam. Ich dachte, der kann 100mW.  
09:10  
Stefan  
Bei den "Alten" Versionen des T-Beam ist die Leistung bewusst gedrosselt, sonst tauchen unerwünschte Effekte auf. Nur die neuen laufen mit 21dB problemlos.  
09:23  
Rainer OE1KFR  
Müsste man halt 100% verifizieren, dass das für alle SX127x Boards einwandfrei geht. Mein Infostand war, dass der Boost PA Mode bei den Chips ein verzerrtes Signal zur Folge hat, weil es da einen Designfehler im Chip gibt.  
09:31  
Stefan  
Wie könnte man das feststellen? Hohe Leistung und dann schauen, ob msg ankommen?  
09:33  
Rainer OE1KFR  
Ja und das halt nicht nur am Schreibtisch.  
09:35  
Stefan  
Ich hab leider keinen der Teile mehr da, vll kann ich mir einen besorgen die Tage.  
09:46  
Wolfgang Hallmann DF7PN  
Frage an die Profis: hier ist beim Workshop gerade ein Pin vom Board am E22 weggebrannt. Ist dieser Pin wichtig? Platine damit kaputt?  
09:47  
09:48  
#### wolfgang z  
Wie ist das passiert?  
09:48  
Stefan  
Das sind 3 Masse-Pins nebeneinander, daher ist der Verlust zu verschmerzen... 😉  
09:49  
#### wolfgang z  
Genau , so ist es.  
09:49  
Stefan  
Die 3 Pins sind eh etwas schwierig zu löten, da braucht es ordentlich Hitze, weil die Board/Chip-Masseflächen die Wärme rasch abtransportieren.  
09:51  
Gleiches gilt für die Pins gegenüber, 2x Masse und in der Mitte die Antenne.  
09:54  
Wolfgang Hallmann DF7PN  
Danke, das ist gerettet.  
09:55  
Rainer OE1KFR  
Wir müssten das eh erst in der FW entsprechend möglich machen.  
11:40  
Ben  
Ich kann THD messen relativ genau...wir müssten da halt nen sauberen träger irgendwie rausgeben....müsste man mal in der radiolib schauen....vielleicht im fsk mode  
👍  
12:19  
Jochen DG3FBL  
T-Beam 1 habe ich zwei hier  
13:38  
#### wolfgang z  
Hmm, wie willst du bei den Chirp-Signal von LoRa eine Verzerrung messen. Stelle ich mir nicht einfach vor.  
14:33  
Ben  
Der kann auch andere modi.außer. chirp....  
16 February 2025  
15:46  
Stelio  
Hallo, ich habe für mein ESP32-E22 Projekt ein SMA to N Buchse eingebaut.  
Also SMA Buchse - SMA Stecker - 20cm RG178 - N-Buchse. Als ich die node in Betrieb genommen habe, musste ich feststellen das der Empfänger verglichen mit einem TLORA T3_V1.6.1 ziemlich schlecht ist. Ich habe dann eine zweite node gebaut, aber habe diesmal eine IPEX to N-Buchse genommen. Jetzt war alles perfekt und daher habe ich die erste Platine auch auf IPEX to N-Buchse umgebaut und die Empfangsleistung ist jetzt auch ok.  
Kann es sein das das SMA to N-Buchse Kabel so stark dämpft oder habe ich da was übersehen?  
15:47  
Stefan  
Hast du die Lötbrücke auf der Platine für die SMA-Buchse eingelötet?  
15:48  
Stelio  
ja, habe ich  
15:52  
Stefan  
Das sollte dann prima funktionieren. Du kannst das auch nachmessen, ob evtl. irgendwo was nicht passt: erst mal mit einem Widerstansmessgerät (Multimeter) auf Durchgang und Isolation. Dann evtl. mit SMA-N-Adapter testen.  
15:58  
Stelio  
Ok, Danke Stefan. Das Kabel habe ich schon durchgemessen. Die Verbindung Pin21 und R8 dürfte auch ok sein, BTW den jumper habe ich jetzt wieder entfernt.  
16:00  
Stefan  
R8 ist ja 0Ohm, ich hab dafür einen Draht eingelötet. 😉  
16:03  
Stelio  
ja, ich auch. Aber es gibt 0R zu kaufen ... habe ich nie verstanden.  
16:04  
Stefan  
Macht Sinn für Bestückungsmaschinen. Daher gibt es die.  
16:07  
Ich hab meinen Node mit einem IPX-Kabel angeschlossen, einmal IPX-SMA und einen anderen mit IPX-N, einer mit IPX-BNC ist gerade im Bau. Probleme gab es dabei nicht bisher  
16:25  
Stefan  
Ist meines Erachtens die bessere Variante, als den "Umweg" über die SMA-Buchse zu nehmen.  
16:32  
Stelio  
Ja, ich habe ja meine nodes auch auf IPEX umgestellt bzw. angeschlossen.  
21:54  
Helmi Beh  
Und bitte denkt dran, dass auch hochwertige IPX-Stecker nur für maximal 10 Steckzyklen spezifiziert sind, weil sie gerne ausleiern.  
👍  
21:58  
Stefan  
😊 Daher ja für den Gehäuse-Einbau. Das Kabel macht man nicht dauernd ab.  
Durch die Rumtesterei hab ich die allerdings schon bis an die Verschleißgrenze abgenutzt. Erstaunlich, was die trotzdem aushalten. Ob dann noch die Bandbreite bis 6GHz reicht, hab ich nicht ausprobiert! 😀  
🤣  
22 February 2025  
17:10  
Stefan  
Mal so als Info: Vll kann sich der eine oder andere noch erinnern, ich hatte Probleme mit bestimmten ESP32-Clones aus China. Die sind immer mal unkontrolliert "ausgestiegen" und haben Müll gepostet. Mit der aktuellen Firmware hab ich die nun seit einigen Tagen auf dem E22-Board laufen, keinerlei Probleme mehr. Also kein Unterschied zu den doppelt so teuren ESP32 von EZ-Delivery.  
Die eine Variante hat einen IPEX-Anschluss für eine ext. WLAN/BT-Antenne, das erhöht die Reichweite dafür ordentlich.  
17:12  
#### wolfgang z  
Ahh, gut. Und was meinst du, war das Problem?  
17:16  
Stefan  
Gute Frage, ich hab ein bisschen die Spannungsversorgung in Verdacht gehabt, aber die ist nicht verändert. Daher vermute ich ich irgendwas in der Firmware. Erklären kann ich es nicht.  
23 February 2025  
15:50  
Stefan  
Inzwischen sind die Platinen der 2. Auflage zum Projekt bei mir angekommen, ich fange nun an, die zu verschicken. Sollte noch jemand Interesse ha#### ben, wir haben noch eine geringe Anzahl, die nicht reserviert wurden. 4€ + VVK (2€ DL, 4€ OE). Bitte dann ggf. Mail an dg4neu(at)darc.de  
Bitte auch melden, wenn die mir bekannten "Besteller" heute keine Info von mir bekommen haben.  
25 February 2025  
14:59  
Stefan  
Prima, viel Spaß und Erfolg bei Bau! 🙂  
18:16  
#### wolfgang z  
Bei Startschwierigkeiten am Board dann versuchsweise doch den C1 bestücken. Der verlängert die Reset Zeit.  
18:46  
André  
Platinen sind heute angekommen 😊  
Vielen Dank Stefan.  
👍  
27 February 2025  
16:06  
Juergen DF2AP  
@DG4NEU meine Platinen sind auch eingetroffen. Danke für den Super Service 👍  
16:08  
Stefan  
Gerne, manchmal klappt's auch mit der Post! 😀  
16:12  
Juergen DF2AP  
kurze Nachfrage: das bei mir verbaute USB-C-Adapterboard hat 4 Anschlüsse  
-V  
-CC1  
-CC2  
-G  
Das Kabel hat sechs Anschlüsse?  
Was mache ich mit D+ und D-?  
16:13  
Stefan  
Ja, da gibt es noch ws/bl für D+/D-, aktuell nicht genutzt  
16:17  
Juergen DF2AP  
Super. Dann lass ich die einfach dran und isolier sie.  
16:20  
Stefan  
Mach das, ich hab ne Idee dafür, muss das aber erst noch testen.  
21:32  
Wolfgang Hallmann DF7PN  
Unsere Leute haben da folgendes gemacht. Ein microusb Winkel gekauft und da die Datenleitungen dran gemacht. Somit kann man mit einer externen USB-C Buchse auch die serielle am microusb Anschluss nutzen  
21:37  
Stefan  
Das hab ich heute auch versucht, aber das klappt nicht so, wie ich mir das vorgestellt hab.  
🤔  
22:41  
Stefan  
Der ESP braucht wohl die 5V an der Buchse, hatte aber heute keine Zeit. Morgen vll. dann gibts auch Einzelheiten.  
28 February 2025  
07:57  
Juergen DF2AP  
Klingt gut. Dann warte ich mal auf den Bericht 👍  
12:10  
Carsten  
Vielen Dank!!!!! sind bei mir auch angekommen  
👍  
12:27  
Stefan  
Kannst Du mir mal zeigen, wie das (vom Schaltbild her) gemacht wurde? Hier funktioniert das nicht, wenn nur die Datenleitungen am Micro-USB hängen. Oder haben die Kollegen, das komplett über die Buchse gemacht? Nur die CC1/CC2 am Board angeschlossen? Mit D+/D-/GND/VCC von der Buchse an den ESP klappt das.  
15:07  
Wolfgang Hallmann DF7PN  
Ich habe selber nicht damit experimentiert. Warum es nicht geht bei dir tut mich verwundern. Angeblich soll das USB C Board parallalan der Versorgung zum ESP32 hängen. Ob ich dann die Datenleitungen und Strom getrennt anlege sollte egal sein. Leider habe ich gerade den Schaltplan nicht greifbar. Da müsste es sich zeigen.  
17:35  
Ben  
Gar nicht ...direkt an Antenne  
18:13  
Helmut OE5HWN  
Beim E22 Habe ich weniger Bedenken als bei der 433-iot Pa  
18:51  
Jörg DF3EI (df3ei@db0kk.org)  
Sicher eine aus der selben Quelle wie das PA-Modul... 😁  
1 March 2025  
18:51  
Juergen DF2AP  
3 x ESP32E22 in Thüringen fertig ✅  
👍  
5  
18:52  
Und heute übergeben 😊  
👍  
18:55  
Kurt Baumann OE1KBC  
Großartige leistung, danke für diese Aktivitäten  
19:01  
Tom  
Danke an DF2AP  
19:25  
Rainer OE1KFR  
Hey super toll! Voll schön auch die Fotos. Super, dass ihr euch so engagiert  
4 March 2025  
09:40  
Stefan  
Noch mal zum Thema USB-C-Buchse: Ich hab nun die Kabel etwas anders angelötet, funktioniert. Von den Leitungen der USB-C-Gehäusebuchse sind nur die CC1/CC2 auf dem Board, die VCC/GND/D+/D- direkt am Micro-USB-Stecker angelötet. So ist die Stromversorgung gewährleistet und die Kommunikation über die Buchse mit dem ESP klappt auch.  
Vorteil: Man muss das Gehäuse zum Anschließen des Terminals nicht mehr aufschrauben und auch das Board nicht ausbauen.  
👍  
10:30  
Stefan  
Tststs... warum schreibst du das nicht schon eher! 😀  
11:21  
#### wolfgang z  
Der Grund ist folgender:  
VBUS kommt von der USB-Buchse und ist über die D3 entkoppelt von EXT_5V, welches über die USB-C Buchse kommen würde.  
VBUS ist aber erforderlich, damit der CP2102 (U1) an seinem Pin 8 = VBUS Sense ein Signal bekommt und richtig arbeitet.  
"VBUS Sense Input. This pin should be connected to the VBUS sig-  
nal of a USB network. A 5 V signal on this pin indicates a USB net-  
work connection."  
11:22  
11:30  
In diesem Datenblatt ist genau beschrieben und gezeigt die 22k1/47k5 Beschaltung von VBUS [8] S.8 2.3 USB Figure 2.5  
https://www.silabs.com/documents/public/data-sheets/cp2102n-datasheet.pdf  
11:31  
11:37  
Datenblätter & Application Note AN144 siehe Github  
https://github.com/DK9BT/esp32-e22-lora-board/tree/main/datasheet  
11:49  
Stefan  
Danke für die Info! Demnach ist das aber eine gute Lösung, so liefert USB-C genügend Strom und auch die Kommunikation ist möglich.  
11:50  
#### wolfgang z  
genau so ist es!  
Ich habe noch keine Idee, ob und wie ich das auf der PCB ev. noch einfacher ermöglichen könnte.  
12:13  
Stefan  
Wäre vll etwas aufwändiger, aber ein USB-C-Serial-Wandler als Board auf der Platine (wie der Spannungswandler), versorgt dann den ESP per RX/TX?  
12:29  
#### wolfgang z  
Ja, grundsätzlich möglich. Habe auch schon daran gedacht, als ich erwähnte, dass RX/TX rausgeführt sinnvoll gewesen wäre. ... muss noch etwas gären ...  
12:30  
Stefan  
Vll probiere ich das mal aus, man muss den cp2102 dazu ja nicht deaktivieren, oder?  
12:31  
#### wolfgang z  
Ich würde dann aber gleich auf ein "neueres" Board umsteigen, welches die 2x USB-C on Board und auch größeren Speicher hat. Das würde dann sogar die jetzige USB-C Adapterplatine obsolet werden lassen.  
12:34  
Stefan  
Kann man überlegen. Macht das nicht Sinn, gleich einen neuen ESP (s3...) vorzusehen? Gibt da ja noch Modelle, die USB-C mitbringen.  
12:39  
#### wolfgang z  
genau, den meinte ich auch:  
ESP32-S3-WROOM-1 N16R8  
hab da z.B. µPython schon darauf laufen.  
12:41  
Stefan  
Ich denke nicht, dass es Sinn macht, das jetzige Board zu ändern. Dann lieber was Neues, das auch mehr bietet.  
12:42  
#### wolfgang z  
Ja, ist natürlich EINE Möglichkeit.  
Aber ich habe auch schon angedacht, eine Adapterplatine auf den jetzigen ESP32-Sockel zu machen. Dann könnte man bestehende Boards auch aufrüsten.  
... mit wem hatte ich das schon mal besprochen ? ...  
12:43  
Stefan  
😉😇  
12:44  
#### wolfgang z  
Sticker  
😂  
12:44  
eh mit dir !!!  
war am 30.Jan.2025  
12:47  
vlt. sollte ich den Chat von damals mal zusammenfassen und hier reinstellen ...  
12:48  
Stefan  
Erst müsste man mal klären, ob die Entwickler auch die FW dafür bereitstellen würden. Dann können wir das auch in Angriff nehmen.  
12:52  
#### wolfgang z  
Na ja, sind ja "nur" ein paar andere Definitionen erforderlich. Und wenn man die GPIO grundsätzlich mal variabel als Parameter einstellbar zu machen vorsieht (so wie Button & OneWire), dann reduziert sich das in der FW. Dh. man lagert einige Parameter/Einstellungen in eine externe config aus.  
Ev. mach ich auch einen Fork und teste das mal, was da notwendig wäre zu ändern.  
👍  
12:54  
und wie ich sehe, wird ja ESP32-S3 ja schon unterstützt.  
13:01  
Stefan  
Ben hatte da auch mit experimentiert. Wäre ne schöne Option, wenn das mit einer Adapterplatine funktionieren würde.  
13:05  
#### wolfgang z  
Ja, Ben hat auch so ein Board schon - offenbar.  
13:05  
Adapterplatine wäre ja recht einfach mal.  
17:00  
Ben  
Das wäre top  
17:01  
Sollte kein Problem sein  
👍  
17:02  
Wir haben in der neuen dev version "variants"... Eine header mit pin definition  
17:02  
E290 und helltec v3 sind S3 schon  
17:02  
#### wolfgang z  
ja, das hatte ich eh auch schon in erinnerung.  
17:58  
Rainer OE1KFR  
Wäre schon sehr cool der S3 N18R8. Ich hab in der GPIO Map gesehen, dass einige GPIOs da schon eben wegen dem psram in Verwendung sind.  
18:35  
#### wolfgang z  
Ja, aber es sind auch mehr zur Verfügung. Ich habe schon mal eine Gegenüberstellung gemacht. Muss sie nur noch suchen.  
5 March 2025  
09:55  
#### wolfgang z  
das ist unproblematisch, da das PSRAM über SPI angebunden ist und daher wenig GPIO braucht.  
12:39  
#### wolfgang z  
Am PCB V2.1.2 mit dem ESP32-DevKitC-V4 haben wir folgende GPIOs in Verwendung:  
E22  
GPIO5 E22_NSS  
GPIO13 E22_TXEN  
GPIO14 E22_RXEN  
GPIO18 E22_SCK  
GPIO19 MISO  
GPIO23 MOSI  
GPIO26 E22_BUSY  
GPIO27 E22_NRST  
GPIO33 E22_DIO1  
I²C  
GPIO21 SDA  
GPIO22 SCL  
spezial  
GPIO12 Button (ungünstig, da Strapping-Pin)  
GPIO25 OneWire  
GPIO32 ADC  
GPS  
GPIO16 GPS_TX  
GPIO17 GPS_RX  
12:42  
Zum ESP32-S3-WROOM-1 N16R8 habe ich schon 1 Kollision gefunden. Ist aber behebbar.  
8 March 2025  
09:05  
Wolfgang Hallmann DF7PN  
Gibt es noch Platinen? Hätte noch interesse.  
09:32  
Stefan  
Ja, hab noch was... Mail an dg4neu@darc.de  
18 March 2025  
08:37  
Juergen DF2AP  
Guten Morgen. Falls noch jemand Bedarf hat:  
Das ESP-32 Dev Kit C V4 gibt es heute bei AZ-Delivery als 1er-Set für 6,99€ und als 3er-Set für 13,99€ (Deal of the Day).  
❤  
3 👍  
09:19  
Johann OE6POD  
/Danke für die Info, gleich mal bestellt  
18:20  
Juergen DF2AP  
Gerne 🤗  
19 March 2025  
16:27  
Michael DG1FBP  
Da habe ich mich auch angeschlossen, danke für den Tip  
24 March 2025  
11:32  
Wolfgang Hallmann DF7PN  
11:32  
Ich habe hier was ganz blödes..  
11:33  
nach vielen gleichen Aufbauten ist hier etwas aufgetaucht, was ich mir nicht erklären kann.  
11:34  
das übliche gps modul, was geprüft wurde und auf 9.600 baud Daten liefert bis an den Prozessor, wird von der V Version nicht erkannt.  
11:35  
GPSdebug zeigt wie er drei mal zwei Baudraten probiert und dann gps wieder aussachaltet. Ein frischer esp dafür ausgepackt macht das auch.  
11:36  
Software wurde mehrfach neu aufgespielt. Nix hat geholfen.  
11:37  
Das GPS Modul hat fix und blinkt und am einem ttl/usb Wandler mit u-center ist alles am Laufen.  
11:39  
Da die Pins direkt auf den Prozessor gehen, fällt mir nichts weiter ein  
11:39  
#### wolfgang z  
Ich nehme da mal an, dass das das leidige Problem mit dem Auskreuzen von RX<>TX ist.  
Versuche mal, die umzudrehen.  
Es ist nie sicher, was TX/RX jeweils an den GPS-Modulen bedeutet.  
11:40  
Wolfgang Hallmann DF7PN  
bin skeptisch, aber ich hänge die Leitungen mal um.  
11:41  
#### wolfgang z  
ESP32-GPIO16_GPS_RX <—> TX vom GPS-Modul  
und entsprechen die andere Leitung  
11:41  
Wolfgang Hallmann DF7PN  
ja klar. da habe ich auch den tanzenden Pegel gemessen im Takt der LED  
11:43  
das wäre dann aber der esp der die plötzlich anders will. Gibts sowas? wohl eher nicht, da die gpios 16/17 ja auch andere Aufgaben erfüllen können. Probieren geht über studieren ☺️  
11:45  
#### wolfgang z  
? hat das in einer früheren FW-Version schon funktioniert?  
? Sind es die identischen GPS-Module?  
11:48  
Ein einfacher Test, ob ein Pin ein Eingang ist, falls er keinen PullUp/PullDown hat, mit dem Oszi an diesen Eingang und gleichzeitig diesen Pin mit dem Finger berühren. Damit koppelt man die allgegenwärtigen 50Hz ein und man sieht am Oszi, ob der Pin hochohmig ist.  
11:49  
Wolfgang Hallmann DF7PN  
Das war es auch nicht.  
11:50  
kein Oszi hier  
11:50  
#### wolfgang z  
ältere FW probiert?  
11:50  
???  
11:50  
Wolfgang Hallmann DF7PN  
keine mehr vorhanden hier  
11:50  
#### wolfgang z  
auf Github  
11:50  
Wolfgang Hallmann DF7PN  
stimmt  
11:51  
der ist frisch aufgebaut. ich lade mal was älteres drauf  
11:51  
gibt hier aber viele mit V gleich aufgebaut die laufen  
11:52  
#### wolfgang z  
nimm die "r"  
11:52  
Wolfgang Hallmann DF7PN  
ok  
11:57  
wie zu erwarten, keine gps Erkennung  
11:58  
Helmut OE5HWN  
Hast du noch ein weiteres GPS Modul  
11:58  
#### wolfgang z  
hat sich in der FW nicht geändert:  
#elif defined(BOARD_E22)  
//For heltec these are the pins:  
#define GPS_RX_PIN 16  
#define GPS_TX_PIN 17  
11:59  
Wolfgang Hallmann DF7PN  
Daten liegen an GPIO 16 im Takt an.  
11:59  
Helmut OE5HWN  
Und eine andere Frage GPS ist auf on in der App, bzw. Webserver?  
11:59  
Wolfgang Hallmann DF7PN  
ja klar, war zu erwarten.  
12:00  
ich bin auf der Konsole  
12:00  
12:00  
Helmut OE5HWN  
Welches GPS Modul versendest du?  
12:01  
Wolfgang Hallmann DF7PN  
12:01  
ich mache gerade ein weiteres dran was woanders schon lief  
12:02  
Helmut OE5HWN  
Die sind normalerweise sehr zuverlässig  
12:03  
Wenn's aber im u-center läuft wird es keinen Defekt haben  
12:04  
Bitte die Platine auf Lötfehler prüfen, kann ja mal vorkommen  
12:11  
#### wolfgang z  
war da nicht was, dass man auf nur NMEA einstellen musste oder so?  
12:12  
Helmut OE5HWN  
Das sollte beim Neo-6m als Standard sein, bei dehnen habe ich noch nie was umstellen müssen  
12:13  
Stefan  
Das GPS war schon immer sehr zickig, vll kann man längerfristig eine andere Library dafür hernehmen. Meshtastic z.B. oder die FW von Ricardo ist da wesentlich zuverlässiger, was das GPS angeht. Zumindest ist das mein Eindruck.  
Ich kämpfe da schon lange mit, GPS an den diversen Nodes ans Laufen zu kriegen.  
12:14  
Das war bei den M100, die sind default auf 115200Bd und NMEA/uBlox eingestellt. Die 0815-Ali-Teile in der Regel auf 9600Bd/NMEA only.  
12:20  
Helmut OE5HWN  
So habe mir kurz die Mühe gemacht und mein GPS getauscht von neo-6m auf neo-7m und neo-8m sogar auf ein GT-U7 werden alle erkannt. Jetzt wieder das alte neo-6m alles okay.  
12:25  
Wolfgang Hallmann DF7PN  
erledigt. Alles gut  
12:26  
Helmut OE5HWN  
und was war der Fehler?  
12:26  
Wolfgang Hallmann DF7PN  
Habe ja schon viele nach gleichem Muster gebastelt. Nie Stress gehabt mit dem kram. Zweites GPS Modul wird auch nicht erkannt  
12:27  
anderer esp brachte auch nichts.  
12:27  
so wieder V Version Zurück  
12:28  
nix  
12:28  
zum verrücktwerden  
12:29  
Stefan  
Vll kann Kurt dazu mal was schrei#### ben, ob es tatsächlich die Möglichkeit gibt, die Library (gerne auch mal testweise) zu wechseln. Wir haben hier bei diversen Nodes immer wieder die Probleme, dass das GPS unter Meshtastic z.B. einwandfrei läuft, unter MeshCom aber nicht.  
12:31  
Wolfgang Hallmann DF7PN  
Sachen gibt's  
12:31  
Stefan  
Kann ja auch sein, dass das damit gar nichts zu tun hat, aber irgendeinen Unterschied muss es ja ge#### ben, dass sich die Nodes mit anderer Software so anders verhalten.  
12:31  
#### wolfgang z  
Sticker  
😰  
12:33  
Helmut OE5HWN  
Hast du noch ein zweites E22 zur Hand das funktioniert? dann könntest du da das GPS noch einmal testen.  
12:37  
Wolfgang Hallmann DF7PN  
ja ist in Arbeit  
12:37  
Helmut OE5HWN  
Fertig aufgebaut nicht vorhanden?  
12:39  
Ich würde einmal nur den ESP 32 DevKit alleine mit dem GPS verbinden und dann nachsehen, das würde alles andere ausschließen  
12:42  
Wolfgang Hallmann DF7PN  
😮 das will an einem anderen mesh auch nicht  
12:42  
fuck  
12:43  
Helmut OE5HWN  
Dann zurück zum u-center und da noch einmal testen  
12:45  
Wolfgang Hallmann DF7PN  
das gps aus dem anderen mesh spielt am neuen nun auch. Also Gps boards. Nun wird es lustig.  
Ja UCenter kommt nun dran  
12:45  
nochmal dran  
12:46  
Helmut OE5HWN  
Das wird noch richtig spannend  
12:53  
Wolfgang Hallmann DF7PN  
so an UCenter gehts sofort los mit 9600  
12:53  
12:55  
wir kann man sicherstellen das er später auch nir 9600 benutzt.  
12:57  
Helmut OE5HWN  
Wie ist die Spannungsversorgung am E22 3v3 oder 5v und wie über den PC? Wenn's im U-center mit 9600 läuft dann muss es in der GW auch mit 9600 laufen  
12:58  
Wolfgang Hallmann DF7PN  
ok ist logisch. ttl wandler gibt 3.3 V ab  
12:58  
an der mesh kiste ist es auch 3.3 bzw 3.5  
12:58  
Stefan  
Am E22 sind es 3,3V, mit dem passendenden Adapter kann man das für den PC einstellen. Ich hab das mit 3,3V auch am PC zuverlässig laufen.  
13:00  
Wolfgang Hallmann DF7PN  
eben in U Center andere Baudraten probiert, aber die Platine antworte immer nur bei 9600.  
13:00  
Was mag der esp nicht, das ist hier die Frage  
13:01  
ich habe aber noch paar gps boards zum probieren.  
13:01  
Helmut OE5HWN  
Wie gesagt, ich würde einmal den ESP auf ein Breadboard stecken und nur das GPS anschließen, schauen ob es dann läuft  
13:03  
Dann kann man auch schön RX und TX umstecken  
13:14  
Hast du die Kontakte vom ESP zu den GPS Anschüssen durch gemessen, kann ja sein das da das Problem liegt, falls es über ein Via geht wäre es möglich dass schlecht durchkontaktiert ist  
14:11  
Wolfgang Hallmann DF7PN  
also... uffbasse, hier ist die Lösung:  
Die angeblichen Neo-6M sind keine. Da sind atm chips unter der Haube.  
14:11  
14:12  
Scheinbar sendet die Software (Vermutung) etwas hin und wartet auf Antwort, die diese Chips nicht kennen.  
14:13  
Jetzt wirds spannend ob was in der Software zu sehen ist das dies bestätigt.  
Ich habe jetzt einen frischen Neo-6M ausgepackt und der lief sofort  
14:14  
🇨🇳 Zeugs halt... Fake  
❤  
14:14  
#### wolfgang z  
so wie es mir erscheint, ist da ein LDO drauf, dh. dieses Board benötigt 5V. Damit wäre mit 3,3V dann zu wenig Spannung am Chip  
14:14  
Wolfgang Hallmann DF7PN  
unter dem Aufkleber waren Reste zu sehen vom Vorgänger  
14:14  
14:15  
Halleluja sag ich  
14:16  
#### wolfgang z  
Wenn du aber die VCC auf +5V hängen würdest, dann sind TX/RX wahrscheinlich außerhalb der 3,5V Spezifikation für den ESP32.  
14:31  
Wolfgang Hallmann DF7PN  
eher nicht, da die auf allen Boards drauf sind aber trotzdem als 3,3v Module angepriesen werden.  
14:36  
#### wolfgang z  
hast REcht:  
Support 2.7~3.6V power supply, typical 3.3V power supply.  
19:16  
Helmut OE5HWN  
Direkter Nachbau mit CE Kennzeichen (China Export) bei Ali bestellt?  
19:21  
Wolfgang Hallmann DF7PN  
ja klar. Bei zwei verschiedenen bestellt. Eine Lieferung hat gepasst. Die andere passt halt nicht.  
19:22  
Helmut OE5HWN  
Shit happens, aber Schade um die Zeit die man den Fehler sucht  
19:23  
Wolfgang Hallmann DF7PN  
Die ATM Module funktionieren fast alle. Bei fast allen musste man in der Antenne den Vorverstärker entfernen und brücken.  
19:24  
bei einigen war zuviel Lötzinn in Form von Lötfahnen vorhanden, die einen Kurzschluss produzierten.  
19:25  
Leider werden die ATM Module nicht von der Firmware erkannt, gehen am ttl/USB Wandler aber im U-Center problemlos nach der Antennenkorrektur  
19:31  
Helmut OE5HWN  
habe meine GPS Module bis jetzt immer bei A...n bestellt, da auch eine 3er Packung die nicht Original waren ging zurück, kein Problem. Ersatz bei einem anderen Anbieter etwas teurer bestellt die laufen.  
20:35  
Stefan S.  
Ist mir auch schon vorgekommen, auf dem Sticker ist ein ublox 6M aufgedruckt, beim Start an der Seriellen meldet er sich dann als 5M, also Resteverwertung! Vy73 aus Gmünd.  
27 March 2025  
08:12  
Juergen DF2AP  
Guten Morgen. Heute gibt es bei AZ-Delivery wieder ein Tagesangebot:  
3xBME280 für 11,99€ und  
3x ESP32S Dev Kit C V4 für 19,99€  
https://www.az-delivery.de/products/gy-bme280?variant=19385550536800  
https://www.az-delivery.de/products/esp32-dev-kitc-v4-ai-thinker-soldered?variant=43619467723019&utm_source=90-Days-Engaged&utm_medium=email&utm_campaign=270325_bme280%2BESP32%20Dev%20KitC%20V4%20ESP32_promo_sensors_LVC&utm_id=01JQ9NNVE1NHV5TAZWK4FV8JBB&utm_term=Campaign&utm_content=Hier%20kaufen%20und%20sparen%21&_kx=b2nJXzFUmZF_Rht_n9MewZS-R95z-K-0YgkW6K9F5hdDH8S0JoqPcYl_FPEAP9cG.QVRJMi  
15:51  
Michael DG1FBP  
So, mein e22 läuft auch in grundkonfig  
👍  
15:54  
Franz DG2RBF  
👍  
17:17  
Michael DG1FBP  
mesh klappte noch nicht, 2 kalte Lötstellen an dieser seltsamen Sockelkonstruktion😂😂  
3 April 2025  
10:50  
#### wolfgang z  
Um verschiedene Spannungen mittels des wählbaren Spannungsteilers am Board messen zu können, ist das gelöst worden:  
Da ist jetzt ein Kalibrierungsfaktor !!!  
2025-04-03 v4.34v.04.03 Minor-Release  
NEU #233: Analog GPIO PIN  
PIN setzen --analog gpio 99 (default 32)  
FAKTOR setzen --analog factor 99.9999 (default 1.0)  
Berechnung on/off --analogcheck on/off (default off)  
10:52  
Kurt Baumann OE1KBC  
Schon probiert ob auch gemessen wird. In welchen Rythmus sollen wir messen … sec?  
10:53  
#### wolfgang z  
Nein, noch nicht. Bin noch am TLORA und habe heute Arzt-Termin und schönes Wetter ...  
Ist aber in der Pipeline !!!  
Danke für die Lösung!  
10:53  
Kurt Baumann OE1KBC  
Bin auch gerade beim Hautprüfer HI  
10:54  
#### wolfgang z  
Frage: Ist GATEWAY_NOPOS weggefallen?  
Da dies durch das ANALOG_CHECK ersetzt wurde?  
10:58  
Tja, das ist eine sehr gute Frage.  
Die anderen Umweltdaten sind ja eher träge.  
Der Akku grundsätzlich auch.  
Aber wenn man eine andere Spannung messen will, dann kommt es darauf an.  
• Gemessen wird ja eh in 30" soweit ich es gesehen habe im DEBUG.  
• Übertragen wird es dann seltener.  
• Aber man kann es ja bei Bedarf mit --wx selber öfters abfragen.  
Bitte auch andere Meinungen dazu !!!  
11:37  
Kurt Baumann OE1KBC  
30 sec lasse ich dann  
👍  
11:38  
Welche Werte und wie oft an APRS.fi dynamisiere ich noch  
👍  
7 April 2025  
19:35  
MHX  
Da beim E22-400M33s die reale Leistung höher ist als die in der APP eingestellte, hab ich bei mir mal nachgemessen.  
👍  
19:45  
Michael DG1FBP  
na, das sieht doch gut aus, habe auch den m33s drin  
19:48  
wenn die "No core dump partition found!" kommt.. neu flashen mit komplettlöschen ?  
20:09  
Thomas - DO1TFS  
Kurt meinte deine Spannungsversorgung bricht ein, deshalb der Fehler. Dein -12er Node ist deswegen auf der DENY-Liste weil er gestern nur "Müll" gesendet hat  
20:18  
Michael DG1FBP  
werde das beobachte, mit usb-c an der platine , das sollte reichen  
20:20  
Stefan  
Achte darauf, dass das Netzteil auch die 2A mindestens liefert. Es gibt genug davon, die die Leistung nicht bringen, trotz USB-C  
20:29  
Michael DG1FBP  
werde mal Netzteil vom Raspi4 dran tun..5.2V und 3 A  
20:29  
Thomas - DO1TFS  
dein -11er sendet auch grad "MÜll"  
20:29  
Michael DG1FBP  
dann lassen wir das erst mal  
20:29  
grade weggenommen  
20:29  
Thomas - DO1TFS  
👍  
20:30  
ja das Raspi Netzteil sollte gut gehen  
20:32  
Michael DG1FBP  
taugen die Dinger was ? Angeblich bis 12 A 😂😂  
20:39  
Thomas - DO1TFS  
stell feuerlöscher daneben 🤣😂🤣  
20:54  
Stefan  
Ich hab ne andere Version vom gleichen Hersteller. Hat mich bisher nicht enttäuscht. Nur die Spitzenströme kannst du damit nicht sehen, da ist das zu träge.  
22:07  
#### wolfgang z  
Das ist sehr zu empfehlen!  
Ich habe ja dokumentiert, dass 2A meistens nicht reichen, da die Stromspitzen von den allermeisten Netzgeräten nicht abgefangen werden können.  
Aber wenn du meine ESP32-E22 PCB verwendest, dann solltest du auch die Bestückungsdaten der Kondensatoren einhalten.  
22:08  
Was willst du damit sinnvolles messen?  
8 April 2025  
11:15  
Michael DG1FBP  
war nur interesshalber angeschafft, um zu erkennen, welche Netzteile und Kabel am Mobilphone einen höheren Strom zulassen.  
9 April 2025  
19:00  
Michael DG1FBP  
ist es bekannt, das ab und zu das erste Zeichen oben links verschluckt/nicht dargestellt wird ? beobachte das hier in unregelmäßigen abständen. ist nur beim E22 Board, meine 3 t-beam sind fehlerlos und alle 4 auf version -w  
19:00  
also 4.34w  
19:02  
19:02  
19:56  
#### wolfgang z  
Ja, ja, natürlich bemerke ich das schon sehr lange. Aber ich wollte Kurt damit (noch) nicht nerven, da es wichtigere Dinge gab. 😉  
Übrigens: Am T-LORA Board  
20:17  
#### wolfgang z  
❓Warum hast du den Elko C6 zw. Display und grüner Schraubklemme nicht bestückt?  
20:26  
Ich habe extra da noch darauf hingewiesen❗️  
21:19  
Juergen DF2AP  
Was ist das Jumbo Display?  
21:47  
Franz DG2RBF  
Vermute mal ein 2,4" Display  
10 April 2025  
05:10  
Juergen DF2AP  
Danke 👍  
09:46  
#### wolfgang z  
Nochmals, Michael DG1FBP, und alle anderen, es hat einen Grund, dass in Summe ≈1000µF Elko und einige 100nF Keramik-Kondensatoren auf der PCB verteilt angeordnet sind!  
Jeder erfahrene Elektronik-Entwickler und PCB-Designer wird das sofort verstehen.  
Wer das nicht einhält, der braucht sich dann auch nicht wundern, dass es zeitweise zu einem Fehlverhalten der Elektronik und der FW kommen kann.  
10:10  
Michael DG1FBP  
sorry, Bilder waren schon gemacht, bevor der letzte Elko gelötet wurde, hab nicht mehr an das noch fehlende Bauteil gedacht..😔  
10:11  
Trotzdem vielen Dank für Deine Mühe mit diesem Projekt 👍  
10:29  
#### wolfgang z  
Ok  
15 April 2025  
12:05  
#### wolfgang z  
https://github.com/DK9BT/esp32-e22-lora-board/blob/main/ESP32-E22_V2.1.2/PCB-Assembly/README.md#2-spannungsversorgung  
13:56  
#### wolfgang z  
C3 470µF + C4 100nF sind dafür da, die Stromspitzen vom E22 abzublocken. Und somit den Spannungseinbruch abzumildern. Daher auch ganz nahe am E22 platziert.  
Der andere C6 470µF Elko + C5 100nF sind im Bereich der Stromversorgung, um hier auch zu puffern.  
Die restlichen 100nF sind jeweils sehr nahe bei speziellen Komponenten, um die sehr kurzen Stromspitzen abzublocken.  
(Designregeln der Elektronik, hierbei rechnet man mit Größenordnung ≈100µF/100mA)  
Besser wären 680µF. Die sind zwar auch handelsüblich, aber dann schon wieder mechanisch größer und daher auf der PCB etwas eng und ggf. nicht so leicht verfügbar.  
Aber man könnte auf der Rückseite der PCB noch einen 470µF parallel zum C3 anlöten.  
13:57  
ESP32-E22_2.1.2_SCH.pdf  
60.3 KB  
ich habe den C2 jetzt ausgekreuzt.  
19:48  
#### wolfgang z  
bitte LESEN und beachten !!!  
1 May 2025  
07:27  
#### wolfgang z  
#### wolfgang z 26.04.2025 10:00:17  
❗️übrigens: Ich habe mir gestern ein ESP32-S3-N16R8 Board "zerstört" und das könnte nun auch die Erklärung für jene sein, bei denen das ESP32-Board in einer Boot-Loop hängt, trotz guter Stromversorgung:  
Offensichtlich ist durch einen Kurzschluss des 3V3-Pins auf der Stiftleiste gegen GND der Spannungsregler so gestor#### ben, dass er zwar noch 3,2V liefert, aber den Strom nicht mehr liefern kann.  
Aber ich muss das erst noch genau analysieren.  
07:27  
#### wolfgang z 26.04.2025 17:33:58  
💥Diagnose:  
• Board hängt in einem Boot-Loop  
• An den 3,3V Pin ist im Oszillogramm nichts ersichtlich, aber es triggert bei >1,96V, dh. die 3,3V brechen extrem kurzzeitig ein, sodass der Brown-Out Kreis des ESP32-S3 anspricht und ein Reboot macht.  
Versuch:  
• 100nF KerKo an 3,3V — GND => keine Veränderung  
✅• externe Speisung der 3,3V, wobei ≈70mA fließen, ist erfolgreich! Board läuft wieder problemlos.  
Lösungsversuch:  
• den 3,3V LDO (SMD) zu tauschen versuchen.  
(BT kommen nächste Woche MO)  
👍  
07:27  
#### wolfgang z 27.04.2025 22:18:24  
Den AMS1117-3,3 habe ich nun ausgelötet und mit Netzgerät mit 4,8V versorgt und mit einem Widerstand belastet.  
Bei >100mA bricht die Spannung massiv ein, obwohl es bei Nachrechnung der Verlustleistung und Wärmewiderstand zu keiner thermischen Überlastung kommen sollte.  
Außerdem ist er lt. Datenblatt gegen Kurzschluss und thermische Überlast geschützt.  
Mit Ue=4,8V und Ua=3,3V => ∆U=1,5V  
Bei Ia=200mA => Pv=300mW  
Rth≈90K/W => ∆T≈27K  
Das sollte ergeben Tj = 25°C + 27K = 52°C  
somit ist Tj = 52°C < 125°C = Tjmax  
==> es ist anzunehmen, dass der Spannungsregler trotz angeblichem Kurzschlussschutz durch einen kurzzeitigen Kurschluss am Ausgang defekt wurde!  
Morgen kommen neue AMS1117-3,3 Regler und ich werde den Versuch wiederholen.  
Seid gespannt ...  
07:27  
#### wolfgang z 29.04.2025 20:56:36  
Aber eine "Herz-Transplantation": ASM1117 getauscht und das Board läuft wieder. Zuvor mit dem defekten LDO in einem Boot-Loop gewesen.  
07:27  
ist ja auch die ältere FW, wo ich nur GPIO38 aktiviert habe und kein Neopixel.  
ABER damit ist mir möglicherweise ein Beweis gelungen, dass diese Nodes mit den kryptischen Zeichen, die in einem Boot-Loop hängen, ganz einfach nur einen defekten ASM1117 ha#### ben, da der Anwender "irrtümlicherweise" den durch Unachtsamkeit geschossen hat.  
07:27  
der Test ist denkbar einfach:  
• Die 3V3 mit einem 15Ω Widerstand gegen GND.  
=> dadurch sollten ≈200mA fließen  
• Die Spannung messen: die muss weiterhin ≈3V betragen!  
07:27  
per SW nicht, nur durch externes messen der Spannung bei Belastung  
07:27  
#### wolfgang z  
Kurt Baumann OE1KBC 29.04.2025 21:02:57  
Das wird für manche eine Challenge  
07:27  
#### wolfgang z  
#### wolfgang z 29.04.2025 21:06:05  
Nicht wirklich. Ist zwar ein SMD-Bauteil, aber die Reihenfolge ist folgende:  
•1) mit einem scharfen Seitenschneider die 3 Beinchen abzwicken.  
•2) dann etwas aufbiegen und die breite Lasche ablöten.  
•3) die Reste der Beinchen entfernen und mit Lötsauglitze o.ä. die Lötstellen "säubern".  
•4) den neuen 1117 auflegen, zuerst 1 Beinchen anlöten, dann die anderen beiden. Zuletzt die breite Lasche.  
FERTIG - OPERATION gelungen - PATIENT LEBT wieder.  
07:27  
die Beinchen abzwicken (cyan)  
Die Lasche ablöten (rot)  
7 May 2025  
07:51  
Juergen DF2AP  
Bei AZ-Delivery gibt es heute wieder das ESP32 Board Dev Kit C V4 im Angebot. Drei Module für 13,99€.  
https://www.az-delivery.de/products/esp32-board-dev-kit-c-v4-nodemcu-wlan-wifi-development-board-unverlotet-mit-usb-c-anschluss-kompatibel-mit-arduino?variant=46050529444107&utm_source=90-Days-Engaged&utm_medium=email&utm_campaign=070525_ESP32%20Board%20Dev%20Kit%20C%20V4%2BD1%20Mini_promo_Microcontroller_LVC&utm_id=01JTKHW83ZT22A2CJSRHAKWWST&utm_term=Campaign&utm_content=👉%20Hier%20Angebot%20sichern%20👈&_kx=b2nJXzFUmZF_Rht_n9MewZS-R95z-K-0YgkW6K9F5hdDH8S0JoqPcYl_FPEAP9cG.QVRJMi  
👌  
19 May 2025  
10:14  
#### wolfgang z  
Sticker  
🔥  
10:15  
Ich habe soeben eine Mitteilung bekommen, die meinen Anfangsverdacht bestätigt hat:  
LÖTFEHLER => GESAMTES PCB nachlöten  
10:15  
#### wolfgang z  
Ralf Herold 19.05.2025 08:08:35  
Hallo Wolfgang . Du hattest vor einiger Zeit wegen den Fehl-Aussendungen von DH1IAC-16 hier geschrieben. Er ist ein befreundeter Funkamateur von mir. Hat leider kein Telegramm . Aber er hat den Fehler auf seinem E22 Board behoben indem er alles nochmal nachgelötet hat. Er hat wohl zuvor auch selbst schon gemessen das hier und da nicht genug Spannung vorhanden ist. Seit dem Nachlöten funktioniert es offenbar  
❤  
11:42  
Franz DG2RBF  
👍  
14:37  
Wolfgang Hallmann DF7PN  
Oh brauche Hilfe. Bei der Firmware gibts jetzt neue Aufteilungen. Was ist denn laut der Liste ein DevKitC mit E22400M30S?  
14:49  
Stefan  
Das ist die 1W-Variante des E22 für 433MHz mit dem bisherigen Board mit ESP32 (ohne S3)  
Der mit 2W hat die Bezeichnung E22 400M33S  
15:12  
Wolfgang Hallmann DF7PN  
und welche Version der SW ist das nun? Bisher gabs nur einen bin. jetzt sinds zwei  
👍  
15:13  
15:13  
erster oder zweiter Eintrag? ich weiß nicht was ich nehmen muss  
15:14  
Stefan  
Der erste ist für 868MHz-E22, der Zweite für die 433MHz-Variante.  
15:14  
Wolfgang Hallmann DF7PN  
puh, danke Stefan  
15:17  
Stefan  
Bitteschön!  
15:26  
Wolfgang Hallmann DF7PN  
Wäre sicher gut gewesen diese MHZ in den Namen mit einzubringen wenn man nicht die einfachen Nutzer auflaufen lassen wollte.  
15:27  
Stefan  
Naja, man sollte schon ein bisschen über die Bezeichnungen Bescheid wissen, wenn man das nicht über den Webflasher macht. Die Unterschiede 433/868 sind da nicht ganz unwichtig. 😉  
15:39  
Kurt Baumann OE1KBC  
SX1268 ist 400 Typ SX1262 ist 900 Typ  
15:40  
400 ist 433Mhz … 900 ist 868  
26 May 2025  
09:02  
Juergen DF2AP  
Guten Morgen. Den BME280-Sensor gibt es heute bei AZ-Delivery im 3er-Pack für 11,99€ zzgl. Versand im Angebot.  
https://www.az-delivery.de/products/gy-bme280?variant=19385550536800&utm_source=90-Days-Engaged&utm_medium=email&utm_campaign=260525_GY-BME280-Sensor_promo_sensoren_LVC&utm_id=01JVYRSQH4SAEJ2JJEZ2ZQGEFT&utm_term=Campaign&utm_content=👉%20Hier%20kaufen%20und%20sparen%20👈&_kx=b2nJXzFUmZF_Rht_n9MewZS-R95z-K-0YgkW6K9F5hdDH8S0JoqPcYl_FPEAP9cG.QVRJMi  
29 May 2025  
19:57  
Wolfgang  
jemand ne Ahnung was mit "brownout detector was triggered" gemein ist. hab mir das PCB von DK9BT zusammen gebrutzelt und wenn das teil startet bekomme ich nach der initalisierung diese Meldung im Telnet client angezeigt. meine Versorungs ist ein 5V 3A netzeil, das sollte nach angaben eigentlich reichen  
19:59  
Stefan  
Wenn das Netzteil genau 5V liefert, an der Schotty-Diode noch 0,3V abfallen und beim ersten Senden mit 2W die Spannung noch mal ein wenig zusammenbricht, dann rutschst du unter die "Brownout-Schwelle". Evtl. die Diode mal überbrücken.  
20:00  
Bei anderen waren es unsaubere Lötstellen, an denen durch Übergangswiderstände ein Spannungsabfall aufgetreten ist. Also beim "Zusammenbrutzeln" wundert mich das nicht! 😄  
👍  
20:40  
Helmi Beh  
Hatte gerade das gleiche Problem mit dem Brownout Detector. Bei mir ist das Problem das Display. Ich habe eines mit der Anschlussreihenfolge Gnd-Vcc-SCL-SDA. Und wenn man die Brücken nicht auftrennt, sondern nur die Jumper umsteckt, gibt es einen Kurzschluss zwischen 3V3 und Gnd.  
20:43  
Stefan  
Autsch... aber da ist die Ursache ja eher eindeutig! 😀  
20:43  
Helmi Beh  
Dazu noch ein Hinweis: mein Display kann ich nicht in den J11 stecken, da der Abstand zum ESP32 zu eng ist und sich die beiden PCBs berühren.  
20:44  
#### wolfgang z  
Wer lesen kann, ist entscheidet im Vorteil. 😉  
20:44  
Stefan  
Ist das ein 0,96" oder 1,3"?  
20:44  
Helmi Beh  
In den unbezeichneten Stecker neben den Jumpern geht es aber rein.  
20:46  
0.96", allerdings 128*64 mit SSD1306.  
20:46  
Stefan  
Sollte aber eigentlich passen... 😳  
20:48  
#### wolfgang z  
Der ist nicht unbezeichnet, sondern auf der Rückseite mit J11  
20:49  
Wenn man weiß, was das für Konsequenzen hat, dann kann man das tun.  
20:51  
Helmi Beh  
20:51  
Stefan  
Sicher doch. Die Diode ist schon sinnvoll bei ner Klemme für den Stromanschluss. Für eine Ursachenforschung aber mal verzichtbar. 😉  
👍  
20:51  
Helmi Beh  
Das ist das OLED im J11. Der andere Stecker hat bei mir keine Bezeichnung.  
20:52  
#### wolfgang z  
20:52  
Das ist KEIN DevKitC-V4 !!!  
👌  
20:53  
Helmi Beh  
Ich meine aber den waagerechten! Der hat keine Bezeichnung, bzw. U2. Da ist noch ein halber mm Platz.  
20:54  
Stefan  
Es gibt unterschiedliche Bauformen. Auch welche, die größer sind. Um 90° verdreht müsste das aber passen.  
20:55  
#### wolfgang z  
Ja, richtig. Der ist Teil des OLED und das hat den Bezeichner U2  
20:55  
Helmi Beh  
Hat aber die gleiche Pinbelegung und der Abstand der beiden Pinreihen stimmt auch. Die Breite des ESPs ist 27.8mm. Auch das sollte passen!  
20:56  
Kurt Baumann OE1KBC  
Schaut die WLAN Antenne am Ende etwas raus ca. 5mm  
20:56  
#### wolfgang z  
Ja, aber ist ne NodeMCU und hat u.U. andere Kennwerte.  
20:56  
Kurt Baumann OE1KBC  
Sehe ich auch so  
20:59  
#### wolfgang z  
Ja, natürlich. Ich habe das Design nur möglichst sicher gemacht. Man kann einiges weglassen und einiges überbrücken.  
Auch ohne den Schutzdioden sollte im Normalfall nichts passieren. Aber das kommt auf die Netzgeräte an.  
21:00  
Und wenn man IMMER nur EINE Versorgung angesteckt hat, dann ist das auch OHNE Dioden sicher verwendbar.  
21:00  
Helmi Beh  
Welche anderen Kennwerte meinst du?  
21:01  
#### wolfgang z  
z.B. Stromverbrauch, was sich auswirken könnte.  
21:02  
Aber auch die Sicherheit der WiFi-Verbindung, da anderes Design des Moduls. Es gab ja einen triftigen Grund, dass das neue Design die WiFi-Antenne frei überstehend hat.  
21:04  
Helmi Beh  
Nein; wenn man ein gescheites NT verwendet mit passendem Kabel sollte es kein Problem sein. Ich fahre das Ding eh mit 5.6V wie meine anderen E22. Da kommt etwas mehr Leistung heraus. Wobei ich erstmal eine andere FW verwende, um Satelliten zu empfangen (TinyGS-Projekt).  
30 May 2025  
06:55  
Wolfgang  
ja das mit dem Zusammen Brutzeln war so jetzt nicht gemeint.... löten kann ich schon, aber ich schau mir die Lötstellen nochmal an. wobei ich da auf den 2. blick nichts finde... Das OLED läuft ohne Probleme. Mit JP1 und JP2 habe ich schon beachtet, dass da kein Kurzschluss passiert.  
09:48  
Rainer OE1KFR  
Gebt für den E22 einen größeren oder zusätzlichen Elko rein.  
👍  
09:56  
Kurt Baumann OE1KBC  
Genau ich habe immer 1000uF gleich ins Chip  
09:59  
Klaus Becker  
Brounout: Eingangsspannung am ESP32 zu gering, Prozessor sichern kurz noch wichtige Daten, danach schaltet er ab  
Gegenmaßnahmen: Spannungspegel auf Eingangsspannung gem. Datenblatt erhöhen und stabil halten.  
Die Verwendung von "billigen" USB-Leitungen, zu geringer Aderquerschnitt etc, führen gerne zum geschilderten Problem.  
10:03  
#### wolfgang z  
das wäre ja kein Problem, wenn er dabei nicht irgendwelche Fehlaussendungen macht.  
Ich habe zwar schon alles vorbereitet für so eine Messung, aber muss erst noch die ADC-Filterung fertig machen.  
14:43  
Wolfgang  
danke... das USB kabel ist kein billiges mit knappe 10 € und ich hatte acuh bisher noch keine probleme mit dem Kabeltyp... Das Dev kit 4 läuft ohne die Platiene mit dem E22 stabil... denke ich habe da noch irgen ein bauteil noch nicht eingelötet was rein soll... ich schau mir das nochmal genau an...  
31 May 2025  
10:35  
Wolfgang  
Kurzes Update... es waren keine Lötstellen, und keine problem mit der platiene... es ist das DevKit4 leider ist es defekt, deshalb der Brownout...  
10:53  
Stefan  
Das ist auch meine Erfahrung, manche der Teile sind empfindlich gegen Unterspannung. Vor Allem bei den China-Teilen passiert das eher, die von z.B. AZ-Delivery waren bisher alle ok.  
10:58  
Wolfgang  
der ist tatsächlich von AZ-Delivery  
11:00  
mal ne andere frage gibt es irgend ein kniff um auf die webseite des nodes zu kommen? wlan habe ich eingerichtet, aber laut putty startet er den webserver und die Wlanverbindung nicht selbständig, und wenn ich drauf zugreifen will wenn ich den webserver per app aktiviere ist er nach dem reboot wieder aus  
11:08  
Stefan  
Der Node sollte sich das merken, wenn die WLAN-Info hat. Die Verbindung kommt nur zustande, wenn der Webserver oder GW aktiv ist. Das sollte er sich aber auch merken.  
Wenn du den Webserver einschaltest, dann lasse den Node erst mal in Ruhe, das dauert manchmal ein bisschen, nach dem automatischen Reboot noch einige Zeit, bis er dann doch den Webserver aktiviert.  
11:10  
Wolfgang  
jetzt nach dem ich GW aktiviert habe macht er die Verbindung.... aber auch die Webseite kann ich immer noch nicht drauf. da bringt er mit  
[189708][E][WiFiClient.cpp:429] write(): fail on fd 50, errno: 104, "Connection reset by peer"  
11:12  
Stefan  
Welchen Node hast du genau? Den vom Bild oben? Der Ist nämlich nicht gleich den von der Software unterstützten WROOM DevKits. Evtl. Liegt es daran, die BerryBase NodeMCU sind meines Wissens KEINE WROOM bzw. DevKit V4.  
11:20  
#### wolfgang z  
Hast du die 3,3V nach meinen Angaben getestet?  
Möglicherweise ist nur der 3,3V Regler nicht mehr ok.  
11:22  
Wolfgang  
11:22  
ne habe ich noch nicht gemacht  
11:23  
#### wolfgang z  
siehe hier:  
https://t.me/c/1987218802/11812/21680  
11:24  
das ist ein DevKitC-V4, und sollte somit passen.  
12:32  
Helmi Beh  
Meinst du, AZ-Delivery macht die selbst? Die kommen auch aus China!  
12:34  
Doch, auch die Berrybase sind ESP32-WROOM! Zwar keine V4, aber trotzdem WROOM.  
12:35  
Stefan  
Ja, frelich kommen die daher. 🙂 Allerdings gibt es wohl einige Hersteller, die die produzieren und die sehen auch in der Bestückung unterschiedlich aus.  
13:04  
#### wolfgang z  
bez. der 3,3V:  
Diese Killen des 3,3V-Reglers kann erfolgen:  
• durch irgendwelche Fehlbedienung,  
• z.B. auch OLED mit VCC-GND vertauscht.  
Dann kann der Regler den Strom nicht mehr liefern.  
13:27  
Wolfgang  
das Oled hatte gepasst... aber ist auch kein großer schade... so ein dev kit besorge ich eh immer im 3er pack wenn ich was versuche... hab da noch 2 ganze und glaube in einem ausrangierten Projekt steckt auch noch einer drin  
13:28  
der USB-Serial wandler hat auch einen schlag abbekommen also da muss was ganz arg schief gegangen sein....  
20:09  
#### wolfgang z  
oh, danke, interessante Info  
1 June 2025  
22:37  
#### wolfgang z  
Zum Thema BrownOut Messaufbau  
Leute, ich sag's euch: "Die Elektronik is a Hund!" (Messtechnik)  
So einfach es scheinen mag, so schwierig ist es zu messen.  
=> Schwingungen auf den 5V und dem Shunt.  
Auch die Frage der GND von Osz & NG und USB(PC) ist so eine Sache. Von "Einpunkterdung" keine Spur.  
Ich muss wohl das alles nochmals genau überdenken.  
22:42  
Die Grundidee:  
• USB-Datenleitungen vom PC zum Modul durchschleifen.  
• Die 5V-Versorgung über externes Netzgerät.  
• In die Masseleitung VBUS einen Shunt für Strommessung.  
22:46  
1. Änderung:  
• Den Shunt in die 5V und den Strom differentiell messen. (Oszi hat eh 4 Kanäle).  
• großen Elko+100nF am Ende der Versorgungsleitung vom Netzgerät kommend zur Schwingungsunterdrückung.  
=> Somit wären alle GND auf gleichem Potential: USB-PC, NG & Oszi & Node-GND  
22:47  
aber erst morgen weiter ...  
2 June 2025  
10:29  
Helmi Beh  
Und ein Steckbrett zwischen den Masse- und Stromleitungen ist schon mal für solche Messungen ein No-Go! Und auch diese "modernen" Dupont-Eisendrähte sind Schrott.  
11:54  
#### wolfgang z  
Ja, ja, das stimmt schon. Aber ein erster Versuch war es eben.  
Habe schon nach paar Ideen umgebaut und werde nach dem späten "Frühstück" einen neuen Versuch starten.  
11:56  
Gute Idee, das auch zu ersetzen. Werde das auch noch ändern. Wird aber u.U. kaum was ändern. Aber eine Versuch ist es wert.  
12:10  
Deshalb wäre es interessant, wenn auch "ihr" mal einen Messaufbau machen könntet und dann eure Ergebnisse zeigen könntet. Denn u.U. habt ihr bessere Ideen und damit könnten wir aussagekräftigere Messungen produzieren.  
12:16  
Das ist meine Vorgehensweise jetzt:  
•1) "Einpunkterdung", dh. zumindest alle GND auf gleichem Potential.  
•2) Direkt am Adapterboard Abblockung der Versorgungsspannung mit SuperCap 1,5 F (!) + 330µF Tantal + 100nF Kerko  
•3) MessShunt R100 in der VBUS (+5V), was auch den Ri von einem Akku (Größenordnung 100mΩ) simuliert.  
16:31  
#### wolfgang z  
16:32  
So, Leute, die Ergebnisse sind im Kasten:  
ESP32-E22M400 PCB @ 22 dBm  
16:34  
‼️ In KEINEN der Fälle, wo es zu einem fortlaufenden REBOOT kam, war eine Fehlaussendung festzustellen!  
16:41  
Daher fasse ich mal zusammen:  
1️⃣ Voraussetzung ist, dass mein ESP32-E22 V2.1.2 PCB vollständig nach Angaben bestückt ist und einwandfrei gelötet wurde.  
2️⃣ Die Versorgung erfolgte über ein Labor-Netzgerät mit 1,5 F !!! Super-Cap an der USB-Buchse vor dem Shunt von R100, um einen Akku zu simulieren.  
3️⃣ Es war eine Mindestspannung von 4,4V vor dem R100 erforderlich und es reichte eine 1,0A Strombegrenzung, da der 1,5 F Kondensator die Stromspitzen abfing.  
4️⃣ was kann man daraus schließen? ...  
16:57  
#### wolfgang z  
FAZIT:  
Eine nochmalige Tiefenanalyse der Situation ergab:  
🅰️ Es waren IMMER Nodes mit E22 und als GW.  
🅱️ Die beobachteten Fehlaussendungen konnten logischerweise NICHT auftreten, da sie ein valides UDP-Protokoll erfordern, um am Dashboard des Servers aufzuscheinen. LoRa wäre ev. auch erwägenswert, wenn die Fehlaussendung der sendende Node anschließend über ein GW geleitet wird.  
➡️ Damit die beobachteten Fehlaussendungen abgesetzt werden können und den Server erreichen können, bedarf es einer laufenden, funktionierenden FW:  
💥 Die beobachteten Fehlaussendungen sind somit BEWUSSTE Aussendungen der jeweiligen Betreiber der Node, ev. einer vorgelagerten Node via LoRa.  
💥💥 Zu den "kryptischen Zeichen":  
Das ist überhaupt nicht mysteriös, wenn man annimmt, dass das komprimierter u/o verschlüsselter Text ist/war.  
Da ist mein Ergebnis und Statement.  
Wer hat da wohl bewusst Tests gemacht mit unzulässigen Message-Inhalten?  
Ein gewisser Rest an Fehlfunktionen im Sinne der Fehlaussendungen könnte auftreten, wenn 1️⃣ nicht erfüllt ist. Aber das ist SEHR unwahrscheinlich.  
17:02  
PS: Solange niemand schlüssig nachweisen kann, wie diese vormals beobachteten "Fehlaussendungen" zustande kommen, inkl. detaillierter, genauer Bauteilsituation und Messwerten und Protokollen, kann dieser meiner Aussage NICHT widersprochen werden.  
17:15  
Stefan  
Du glaubst also allen Ernstes, dass die Messages absichtlich von irgendwem geschickt werden? Mit Verlaub, das ist alles andere als wahrscheinlich. Ich konnte diese Aussendungen bei meinen eigenen Nodes schon beoabachten und habe die sicher nicht absichtlich ausgesendet. 🙂  
Die Tatsache, dass du diese Fehlaussendungen nicht nachstellen kannst, ist für mich noch lange kein Hinderungsgrund, dir hier zu widersprechen.  
Ein Nachweis ist nicht ganz so einfach für den betroffenen Funkamateur, dem diese ganzen Messmittel nicht zur Verfügung stehen. Das dann als Absicht zu unterstellen, finde ich schon etwas schräg.  
👍  
17:17  
Ich werde mir nun tatsächlich die Mühe machen und versuchen, die Situation nachzustellen. Nicht, um irgendwem was zu beweisen, sondern um den Fehler zu finden, der nun mal immer wieder auftritt und das sicher nicht mit Absicht.  
👍  
17:24  
Thomas - DO1TFS  
Hat schon mal jemand daran gedacht, dass eine HF Einstrahlung vom E22 den ESP zum Absturz bringt ??  
17:27  
Stefan  
Ich denke, dass es tatsächlich mit der StrV zu tun hat, die Aussendungen sind z.B. immer dann zu beobachten, wenn die Batteriespannung in den Keller geht. Das sieht man u.A. auch in den Graphen der Map. Bei mir war es während einer Autofahrt, bei der der E22 mit Akkus versorgt wurde. Das lässt sich noch mal nachstellen, werde ich demnächst aufbauen.  
17:30  
#### wolfgang z  
Du hast aber nicht verifizieren können - damals - ob die nicht via LoRa empfangen wurden und nur weiter geschickt wurden. Leider gibt es diesbezüglich keinen Log und es hat auch niemand darauf geachtet.  
17:30  
Ja, bitte, mach das.  
17:31  
Diese Situation ist insofern unlogisch, denn warum soll ein abstürzender ESP gerade noch als "letztes Lebenszeichen" einen valide UDP-Message abschicken.  
17:33  
Ja, ok, bitte nachstellen, dies Fehlaussendungen.  
Zeig mir einen Schwachpunkt in meinen Aussagen auf.  
Und beachte auch 1️⃣  
17:33  
Thomas - DO1TFS  
die Situation is sowieso unlogisch... das "Partition not found" kommt doch auch nach dem Reset erst..  
👍  
17:35  
#### wolfgang z  
Genau so ist es! Dieser Klartext KANN NICHT Ausgesendet werde - irrtümlich - und auch noch von einem "sterbenden" ESP32.  
17:35  
Thomas - DO1TFS  
alles sehr seltsam  
17:36  
hab das übrigens rausgepatcht bei mir... einfach eine Dump Core Partition angelegt 🤪  
17:36  
#### wolfgang z  
Das kann auf eine Koinzidenz zurückzuführen sein:  
Die Fehlaussendungen traten auf > der Absender beendet das "Spiel" und du tauschst den ESP32. => Fehlinterpretation  
17:38  
Stefan  
Meiner Beobachtung nach sind das Nodes, die als Gateway laufen, gesendet wird ein Teil der Konsolenausgabe nach dem Reboot oder irgendwas aus dem Buffer. Daher vermute ich, dass diese Aussendungen nur über Internet an den Server gehen, wenn beim erneuten Hochlaufen die Spannung nicht reicht. Aber ich versuche das nachzustellen, das damalige Hardwaresetup ist noch vorhanden.  
👍  
17:38  
#### wolfgang z  
Ich konnte das in vielen Versuchen, mit unterschiedlichen Versorgungsspannungen und Strombegrenzungen NICHT nachvollziehen.  
Der ESP32 war ganz einfach funktionsfähig  
ODER in einer BOOT-Loop  
Aber in KEINEN der Fälle irgendwelche Fehlaussendungen.  
17:39  
Ja, bitte, mach das. Bin gespannt auf die Ergebnisse.  
17:40  
zumal du ja damals gesagt hattest, dass das "fehlerhafte" ESP32-Board nun in einer anderen Anwendung problemlos läuft.  
17:41  
Das hatte wir im Brainstorming auch schon durchgekaut. Aber dieser Ablauf ist durch rein gar nichts nachvollziehbar.  
17:43  
Stefan  
Damals war mir noch einiges nicht so klar, wie heute, ich hab dazugelernt. 🙂 Inzwischen glaube ich nicht, dass es ursächlich an defekten/unsauberen ESP liegt, eher an verschiedenen Toleranzen in Bezug auf die Versorgungsspannung. Auch die vermeinlichen Sorgen-ESPs laufen jetzt einwandfrei, nchdem ich die StrV optimiert habe.  
17:49  
#### wolfgang z  
Manchmal muss man provozieren oder ablenken ...  
1) Dieses  
E (71) esp_core_dump_flash: No core dump partition found!  
kommt vom Bootloader, noch bevor irgendein Teil der FW begonnen hat zu laufen!  
2) warum sollte gerade ein Teil dieses Textes in genau den richtigen Buffer kommen, der dann als valides UDP-Packet ausgesendet wird?  
Wahrscheinlichkeit = 00  
17:51  
Stefan  
Da ich keine Ahnung habe, wie die FW genau arbeitet, kann ich dir die Frage nicht beantworten. Tatsache ist aber, dass es passiert. Und wir finden auch raus, warum und auf welchem Weg das zum Server kommt. 😈  
17:52  
#### wolfgang z  
Photo  
511×29  
hier seht ihr, was passiert, FALLS diese Zeile zuvor in den richtigen Buffer kommt. da die Zeichen VOR dem ":" verworfen werden und die Zeichen inkl. dem ":" grundsätzlich eine Message darstellen kann, die man im Terminal eingeben kann.  
17:55  
Stefan  
Ich versuche das nachzustellen, sobald der Fehler dann auftritt, diskutieren wir weiter. Bis dahin ist das Fischen im Trüben und nicht wirklich hilfreich.  
👍  
17:59  
#### wolfgang z  
Das konstruierte Szenario wäre:  
1) Der Bootloader sendet grundsätzlich als letzte Info die obige Zeile an die Serielle Ausgabe.  
2) Wie aber dieser OUTPUT dann im INPUT der Seriellen Schnittstelle kommen kann, das ist das große, ungelöste Rätsel.  
Wie habe leider nur diesen Klartext, an den wir uns halten können.  
ABER: Der trat nicht immer auf. Aber oft zu Beginn der Fehlübertragungen.  
18:03  
Photo  
604×58  
‼️Hier ist es schon wieder von der bekannten Node um 16:15:26  
Und wie sich zeigt, ist der -16 der Sender und -12 nur das GW  
18:08  
Stefan  
Bisweilen haben meine Nodes das beim Einschalten auch gemacht. Gleich nach dem Hochlaufen eine Meldung, dann war alles ok.  
18:09  
#### wolfgang z  
21:35  
Ralf Herold  
Der OM arbeitet Mobil und beim starten des KFz kommt es zu Unterspannung und in der folge dann zu solchen aussendungen ..  
21:45  
Aber so sicher ist er sich nicht ob es wirklich der Grund ist .  
21:49  
#### wolfgang z  
Unerklärlich, unvorstellbar, unlogisch, ...  
21:49  
Ralf Herold  
Ok er schaltet das Teil erst mal ab wir haben das Dashboard hier nicht immer im Blick  
21:50  
#### wolfgang z  
KFZ-Elektronik ist ein sehr spezielles Gebiet.  
21:51  
Ralf Herold  
Wie wahrscheinlich ist die Theorie das . Die ESP 32 von Aliexpress Probleme machen?  
21:52  
Stefan  
Ich denke, dass es nicht wirklich davon abhängt. Vll sind die Toleranzen anders.  
21:54  
#### wolfgang z  
Glaube ich nicht, dass es deswegen ist.  
Aber, um Elektronik in einem KRF zu betrei#### ben, braucht es schon spezielle Vorkehrungen. Aber die sind ja bekannt unter den Elektronikern.  
21:54  
Ralf Herold  
Ok hmm schwierig..Der OM hat noch einen anderen gebaut . DB0TFM-12 läuft ohne Probleme…  
21:55  
#### wolfgang z  
Unwahrscheinlich m.M.n. Die ESP-Module sind wahrscheinlich alle gleich nur mit anderer Gravur. Und das Board drumherum ist lt. Design von espressif auch sehr gut definiert.  
21:57  
Stefan  
Ich hab den Testaufbau fast fertig, nur lasse ich den nicht heute Nacht auf Akku laufen, das mache ich evtl morgen. Dann schau mer mal.  
21:58  
#### wolfgang z  
Kanns du bitte den Testaufbau, dh. die Verschaltung zeigen?  
21:58  
Speziell, welchen Akku du genau WIE an das Board angeschlossen hast.  
21:59  
Stefan  
Mache ich dann, heute nimmer. Couch ist angesagt. 😉  
22:01  
#### wolfgang z  
Wirst du die Serielle-USB monitoren?  
Das Problem ist ja, dass man sehr wenig sieht, da die USB bei einem Unterspannungs-Reboot getrennt wird.  
Da sollten wir die RX/TX dafür verwenden, da die ja bestehen bleibt, bzw. der Serial-USB-Adapter extern versorgt wird.  
22:02  
Ja, das wäre ein interessantes Szenario: Akkuversorgung und Serielle über RX/TX.  
22:02  
Stefan  
Erst mal muss der Fehler ja wieder auftauchen. 😊  
22:04  
#### wolfgang z  
ev. könnte dir Kurt auch ein Rufzeichen direkt in den TEST-Tab umleiten.  
Mein OE3WAS-99 geht automatisch nach TEST in Dashboard am Server. So irritiere ich niemanden.  
22:04  
Ralf Herold  
Ich habe gerade von Ihm erfahren das er bei dem Board ein E22-400T33S mit 33dBM verbaut hat …🙄  
22:06  
#### wolfgang z  
bist du dir da ganz sicher?  
Wir verwenden einen E22-400M33S od. E22-400M30S !!!  
22:08  
Ralf Herold  
Jep hab gefragt ob er beim zusammenbau was anderst gemacht hat …. Ufff …  
22:10  
Äh sorry da bin ich raus mit meinem Halbwissen  
22:11  
Helmut OE5HWN  
Wolfgang du meintest den "T"  
22:15  
#### wolfgang z  
stimmt, da hatte ich mich vertippt bei Goo.. Aber einen "S" gibt es eh nicht.  
22:17  
Ralf Herold  
Noch mal geschaut E22-400M33S steht da drauf .  
👍  
22:18  
Kurt Baumann OE1KBC  
Ich verwende die E22-400M30S, 1W ist auch genug  
22:20  
Ralf Herold  
Das war wohl eher eine Fehlbestelllung  
22:21  
Kurt Baumann OE1KBC  
Wieso .. ich hab immer die 1Watt, ich halte mehr von Balance  
👍  
22:22  
Ralf Herold  
Ich meinte eine Fehlbestellung s seinerseits .. Er wollte 1Watt und hat den 2Watt bekommen…  
👍  
22:39  
Rainer OE1KFR  
Na dann halt die Leistung runter drehen. Die PA im Modul macht 11dB. 19+11 =30 oder noch weniger  
23:03  
#### wolfgang z  
23:06  
Danke für die Anregung. Habe jetzt die RX/TX-Pins auf den FT232R verbunden (inkl. GND).  
Die Versorgung erfolgt jetzt einfach über USB-C für den 1. Test. ✅ Ja, so ginge es, grundsätzlich. Aber Terminal HUHN verliert trotzdem die Verbindung, wenn die Versorgung "abstirbt". 😢 noch nicht gut.  
23:09  
✅ OK, HTerm 0.8.9 verliert die serielle Verbindung nicht und jetzt sehe ich endlich auch, was bei einem PowerOn Boot passiert.  
23:10  
transmittedFlag<\r><\n>  
transmission finished!<\r><\n>  
OnTXDone<\r><\n>  
<\r><\n>  
Brownout detector was triggered<\r><\n>  
<\r><\n>  
ets Jul 29 2019 12:21:46<\r><\n>  
<\r><\n>  
rst:0xc (SW_CPU_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)<\r><\n>  
configsip: 0, SPIWð<\0><\0>ets Jul 29 2019 12:21:46<\r><\n>  
<\r><\n>  
rst:0x10 (RTCWDT_RTC_RESET),boot:0x32 (SPI_FAST_FLASH_BOOT)<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
invalid header: 0xffffffff<\r><\n>  
ets Jul 29 2019 12:21:46<\r><\n>  
<\r><\n>  
rst:0x10 (RTCWDT_RTC_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)<\r><\n>  
configsip: 0, SPIWP:0xee<\r><\n>  
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00<\r><\n>  
mode:DIO, clock div:2<\r><\n>  
load:0x3fff0030,len:1184<\r><\n>  
load:0x40078000,len:13232<\r><\n>  
load:0x40080400,len:3028<\r><\n>  
entry 0x400805e4<\r><\n>  
E (608) esp_core_dump_flash: No core dum<\0>Ÿ<\0>‚…ÉÑ¥Ñ¥½¹2½Õ¹‘…jRT<5><9>É<19>S§%HY.\5ëKWÖE«µÁ}™±…Í¡é<2>rõ<26>½É•"ÕµÁ‚…ÉÑ¥Ñ¥½¹2½Õ¹‘…jRü<\r><\n>  
<\r><\n>  
============<\r><\n>  
CLIENT SETUP<\r>  
23:13  
Ich habe dabei das USB-C Kabel abgesteckt und wieder angesteckt.  
Die interessante Passage ist:  
1️⃣> Brownout detector was triggered  
2️⃣> rst:0xc (SW_CPU_RESET),boot:0x13  
3️⃣> rst:0x10 (RTCWDT_RTC_RESET),boot:0x32  
4️⃣> rst:0x10 (RTCWDT_RTC_RESET),boot:0x13  
und dann erst Durchstart mit Schrott dazwischen.  
23:15  
Aber trotz dieser wilden 3-fach Starts keine Fehlaussendung.  
23:17  
ad 1️⃣ die Elkos haben die Spannung noch so weit gehalten, dass Brownout gesendet werden konnte !!!  
23:20  
ad 2️⃣ ist offenbar noch mit der Restladung der Elkos  
configsip: 0, SPIWð<\0><\0>ets Jul 29 2019  
erst mit "est Jul ..." beginnt der Power on Zyklus  
23:23  
RICHTIG! Das ist noch nach dem Abstecken gekommen:  
<\r><\n>  
Brownout detector was triggered<\r><\n>  
<\r><\n>  
ets Jul 29 2019 12:21:46<\r><\n>  
<\r><\n>  
rst:0xc (SW_CPU_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)<\r><\n>  
configsip: 0, SPIWP:0xeÿ<\0>  
23:33  
❗️Achtung! Was jetzt kommt, ist nichts für Sensibelchen ...  
😁  
23:34  
Ich sag's ja: "Haben ist besser als brauchen."  
Platine > USB-A > USB-Micro > USB-C > USB-C-Winkel > ESP32-E22 V2.1.2 PCB Versorgung USB-C  
23:38  
Das sieht man normalerweise über die USB im Terminal nicht, da der USB-Serial-Chip schon vorher "verreckt".  
3 June 2025  
10:44  
#### wolfgang z  
jetz auch von einem T-Beam ???  
10:44  
#### wolfgang z  
#### wolfgang z 03.06.2025 10:41:17  
Photo  
685×77  
10:44  
Photo  
778×70  
10:49  
#### wolfgang z  
Sehr eigenartig, dass obiges um 10:31 die einzige Meldung dieser Node seit Mitternacht bisher war. Und es müsste ein ":" zuvor enthalten sein, damit es valide Text-Msg wird.  
10:49  
Stefan  
Der T-Beam hat ja auch einen ESP32 drin, daher kann das gut sein.  
10:50  
#### wolfgang z  
Stimmt, hier ist immer ein ":" zuvor:  
rst:0xc (SW_CPU_RESET),boot:0x13  
10:52  
Ja, schon, aber wir gingen bisher immer davon aus, dass der höhere Strombedarf des E22 mehr Probleme mit der Spannungsversorgung macht.  
Das müssen aber SEHR eigenartige Umstände sein, dass solche irregulären Meldungen auftreten können.  
11:03  
corr: hier ist die richtige Sequenz:  
rst:0xc (SW_CPU_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)<\r><\n>  
11:04  
wobei es aber trotzdem unerklärlich bleibt, warum der 1. Teil nicht auch gesendet wird  
11:17  
All diese Meldungen des BootLoaders kann man unterbinden, wenn beim ESP32 GPIO15 während des Bootens auf GND gehalten wird. (=strapping pin)  
Wir sollten mal bei den verschiedenen Boards nachsehen, was am GPIO15 hängt und ob man den permanent auf GND über einen "strong PullDown" ≈1k (?) legen könnte.  
https://docs.espressif.com/projects/esptool/en/latest/esp32/advanced-topics/boot-mode-selection.html#other-pins  
11:18  
Damit können wir somit wahrscheinlich ALLE Fehlaussendungen, so sie nicht absichtlich erfolgen, unterbinden.  
11:19  
Wäre aber nur ein Workaround, da die wahren Ursachen, warum solche Texte als UDP ausgesendet werden, weiterhin unklar blieben.  
11:57  
Stefan  
Mein Testnode läuft jetzt, genau die Konstellation wie damals, als der Fehler das erste Mal aufgetreten ist. Ich beobachte jetzt, ob das wieder passiert, wenn die Akkus in der USV nachlassen. Wenn ja, geht es ans nachforschen/messen. 😊 Die USV liefert 5,1V aktuell, bricht auch beim Senden nicht ein. Über die ganzen Leitungen und die Diode, kommen am ESP etwa 4,6V an. Es bleibt spannend! 😀  
Der Node ist der DG4NEU-77.  
👍  
12:09  
#### wolfgang z  
Ahh, gute Idee, diese USV zu verwenden. Habe auch so eine - ganz vergessen. (fragt mich, was ich nicht habe ... Hi Hi)  
ABER: Der Elko für den E22 ist nicht bestückt, wie ich sehen kann. UND der Elko am Eingang auch nicht. Oder sind die auf der Rückseite? Was ich nicht glaube, da die PCB so flach aufliegt.  
12:10  
Welche Schottky-Diode hast du genau verwendet? Type?  
12:11  
Hi Hi, ich habe auch einen 50Ω-BNC verwendet, in der Hoffnung, das der die max. 2W verträgt.  
12:13  
Stefan  
Die Elkos sind bestückt, liegen flach unter dem OLED aus Platzgründen. Ist ja noch die alte Testplatine. Die Schottky-Diode ist die aus der Bestückungsliste, 1N5817.  
12:14  
#### wolfgang z  
Ahh, ok. passt also.  
Ja, die 1N5817 hat die geringste Durchlassspannung von 6 verschiedenen getesteten.  
12:15  
ja, richtig. Ist die 1. offizielle Version  
12:17  
Stefan  
Die USV ist modifiziert, wie man auf dem Bild sehen kann. Der eine 30kOhm-R ist durch einen 100k-Trimmer ersetzt, der kann die Ausgangspannung im Bereich von 4,5V bis 6V einstellen. Dreht man da zu weit aus dem Soll von 5V, raucht die Platine ab. Also Vorsicht! 😈  
12:17  
#### wolfgang z  
Lasst uns die Spiele beginnen!  
Ich habe mir 2 Stk. LTO Akkus vorbereitet, die in 2S-Konfiguration 5,6 V max. bis runter auf zulässige 3.0V liefern. Die werde ich jetzt anschalten.  
12:18  
welche Platine? USV oder ESP32-E22?  
12:21  
Stefan  
Die USV kann man damit beschädigen, die ist nicht für größere Toleranzen ausgelegt.  
12:25  
#### wolfgang z  
Aber es gibt doch auch 9V u. 12V Typen.  
Es scheint ein Spannungsteiler zu sein, durch:  
R9=10k||R13=nc und R7=30k||R13=nc  
12:30  
ich habe die SCH catchen können: aber scheint nicht ganz vollständig zu sein, oder?  
12:34  
https://hackaday.com/2024/05/06/upgrading-a-cheap-lx-2bups-ups-board-to-fix-fatal-flaws/  
12:36  
Stefan  
Die Seite kenne ich, da hab ich auch die Infos zum Umbau her. Vll bestelle ich mir mal noch eine und teste das, bei welchen Toleranzen die den Geist aufgibt. 😄  
12:38  
#### wolfgang z  
Das ist nicht gut für die Akkus:  
"Since there is no off-switch or other protections on the board, the XR2981 will happily keep operating until around 2.6V, at a rather astoundingly high idle power consumption."  
"Da es keinen Ausschalter oder andere Schutzvorrichtungen auf der Platine gibt, arbeitet der XR2981 problemlos bis etwa 2,6 V, bei einem erstaunlich hohen Stromverbrauch im Leerlauf."  
12:40  
Hier ist die genaue Erklärung:  
https://hackmd.io/@mrhw/rJYwIQeGC  
12:44  
Der Kommentar ist auch gut:  
Antron Argaiv says:  
May 6, 2024 at 2:23 pm  
Even better, would be if someone were to create a new PCB with the fixes in it and release it to the world. Cheap Chinese manufacturers would steal it (as is customary) and shortly there would be improved cheap UPS products on AliExpress…win!  
12:50  
Stefan  
Für unsere Zwecke taugt das nach dem Umbau recht gut. Man kann auch Protectet-Zellen verwenden, dann gehen die auch nicht kaputt, wenn das Teil mal leerläuft. 🙂  
Die Leerlaufstromaufnahme ist im Vergleich zum Node vernachlässigbar. Es ist ja immer noch eine USV, keine Unterwegsstromversorgung, auch wenn ich das mal so getestet hab.  
13:03  
Da fehlen einige Teile, ich muss auch mal suchen, ob ich einen kompletten Stromlaufplan finde.  
Aber: Das Teil kostet beim Ali bisweilen keine 2€, daher kann man auch nicht zu viel erwarten. Ich hab noch eine andere Lösung mit einer Akkuzelle, die muss ich aber noch aufbauen und testen.  
14:02  
#### wolfgang z  
So, jetzt eine Messung des Stroms möglich.  
• 2x LTO in 2S-Konfiguration => ≈5,4V Anfangsspannung  
• R100 in GND-Leitung  
• ESP32-E22 V2.1.2 PCB Versorgung über V = +BATT und G = -BATT nach R100 an den USB-C Pins  
14:08  
Impulsstrom beim Senden max. 102mV/R100 ≈ 1A❗️  
@ 22 dBm => 2W  
Ruhestrom ≈100mA  
14:12  
OE3WAS-99 BrownOut-Test läuft. UDP-TX alle 60"  
Uin = 5,34V  
14:17  
• links oben FT232R  
•rechts oben 2x LTO (2S)  
• rechts unten, etwas verdeckt: R100  
14:22  
Ich habe die APRS-Konfiguration leider noch nicht geschafft, damit BATT als V und nicht als % übertragen und angezeigt wird.  
14:35  
15:03  
#### wolfgang z  
Uin = 5,20 V  
15:23  
Stefan  
Node pausiert, will den nicht alleine lassen, wenn ich mit dem Hund unterwegs bin... 😉  
16:13  
#### wolfgang z  
Uin = 5,00 V ... 0,35V weniger interne 5V => 4,65 V  
17:29  
#### wolfgang z  
Uin = 4,80 V und intern 4,46 V ... alles läuft perfekt  
Stromspitzen beim Senden dementsprechend auf ≈850 mA gesunken  
19:43  
#### wolfgang z  
Uintern = 4,18 V ... Uin = 4,53 V ... alle läuft ...  
bei ≈4,0 V intern wird es kritisch werden  
wir nähern uns langsam der "Schmerzgrenze"  
20:47  
#### wolfgang z  
Uintern = 4,10 V ... Uin = 4.44 V ... alles läuft  
Stromspitzen beim Senden auf ≈850 mA gesunken  
22:24  
#### wolfgang z  
So, ich beende heute den Versuch bei Uintern = 4,0 V und Uakku = 4,36 V bei voller Funktionsfähigkeit.  
... morgen geht es weiter  
22:27  
oben gelb Akkuspannung. Bricht ≈100mV beim Senden ein.  
unten blau Strom an R100  
4 June 2025  
00:16  
Rainer OE1KFR  
Könntest du bitte deine Brownout Testmeldungen an die Test DM schicken und nicht an All?  
06:18  
#### wolfgang z  
Mein OE3WAS-99 ist doch sowieso direkt auf TEST umgeleitet und ich habe einen 50Ω Abschlusswiderstand als "Antenne". Was meinst du, wie die wo hin gehen? Am Dashbord sehe ich sie nur unter TEST.  
06:23  
Haben wir da irgendeinen Ausbreitungsweg übersehen?  
06:26  
Wer bekommt die sonst noch?  
Außer dass sie am Dashboard auf TEST landen.  
Ich habe jetzt zusätzlich noch den Text geändert auf "Test BrownOut". Oder was sollte ich noch tun?  
06:37  
Start heute mit Uintern = 4,00 V & Uakku = 4,34 V  
... läuft problemlos. Die Versorgung bricht noch nicht ein.  
06:50  
‼️ Aber wie es scheint, wird der Test eh bald zu Ende sein, da jetzt plötzlich permanent REBOOTS auftreten. Muss mal die LOG ansehen.  
06:52  
💥 Ja:  
Brownout detector was triggered  
ets Jul 29 2019 12:21:46  
rst:0xc (SW_CPU_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)  
06:53  
Aber am Oszilloskop sehe ich KEINEN Spannungseinbruch oder er ist so kurz,  
06:55  
So, es wird jetzt nichts mehr aktiv ausgesendet ...  
07:06  
Stresstest läuft ... kann noch keine klaren Anzeichen am Oszi erkennen.  
ABER: auch die 3,3V sind nicht mehr sauber!  
07:12  
Obwohl jetzt sporadische REBOOTs auftreten, sind KEINE irregulären Aussendungen zu beobachten.  
07:17  
07:22  
Magenta: 3V3 bricht signifikant ein unter die Brownout Schwelle von 2,7V (ws Cursor Linie), was einen REBOOT auslöst.  
GELB: Akkuspannung am Eingang, noch vor der Schottky-Diode, im Mittel noch 4,31 V, aber bricht auch ziemlich ein.  
CYAN: der Versorgungsstrom.  
07:22  
Und das ist die REBOOT Sequenz:  
Brownout detector was triggered  
ets Jul 29 2019 12:21:46  
rst:0xc (SW_CPU_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)  
configsip: 0, SPIWP:0xee  
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00  
mode:DIO, clock div:2  
load:0x3fff0030,len:1184  
load:0x40078000,len:13232  
load:0x40080400,len:3028  
entry 0x400805e4  
E (608) esp_core_dump_flash: No core dum  
============  
CLIENT SETUP  
============  
07:23  
Ich kann KEINE irregulären Aussendungen feststellen!  
07:26  
Kurt Baumann OE1KBC  
GM Wolfgang, ich werde in die nächste Version die Textsendungen von der Konsole nicht mit ":" sondern auf "::" Erkennung setzen. damit sind solche Sondersendungen besser abgesichert  
07:27  
#### wolfgang z  
Die Test-Aussendungen gehen grundsätzlich problemlos weiter (alle 60"), wenn auch durch REBOOT dazwischen.  
LOG ist auf Wunsch verfügbar.  
07:27  
Ich kann noch immer keine feststellen. Du etwa?  
07:28  
Kurt Baumann OE1KBC  
Nein aber zusätzlich wäre das der Gürtel zum Hosenträger  
👍  
07:29  
#### wolfgang z  
Und ich werde den GPIO15 über 1k an GND legen, was die BOOTloader Messages unterbindet.  
= "Tarnanzug"  
07:29  
Kurt Baumann OE1KBC  
Gut und dann sollte das Thema gut Hinterleuchtet sein  
07:35  
#### wolfgang z  
Interessant, aber auch logisch ist, dass die BLE-Verbindung nach einem REBOOT nicht mehr immer aufgebaut werden kann, da schon das nächste REBOOT erfolgt. Aber meine APP bleibt noch immer dran und läuft.  
07:38  
Ahh, ich sehe, dass trotz 50Ω "Dummy-Load" manchmal doch was bis zu OE3MHU-16 kommt und der das dann verteilt.  
07:39  
... mittlerweile permanente REBOOTs und daher DEFINITIV ENDE. Ich schalte ab!  
07:41  
FAZIT: Ich konnte KEINE irregulären Aussendungen beobachten!  
07:47  
08:54  
Stefan  
Mein Test ist wieder unterbrochen, da ich nicht die ganze Zeit zuhause bin. Und alleine will ich den vll nervösen Node dann nicht lassen. 😉 Heute Mittag geht es weiter. 🙂  
10:16  
Stefan  
Guck doch bitte mal, welche R bei der 5V-Variante der USV als Spannungsteiler verwendet werden (R9/R7). Ich hab das ja bei mir geändert und den Originalen ersetzt.  
10:24  
#### wolfgang z  
habe ich oben schon mal geschrieben  
10:25  
https://t.me/c/1987218802/11812/23235  
10:25  
Stefan  
10/30k bei der 5V-USV...?  
10:27  
Die 12V hat meine ich 10/26k, ich guck aber später noch mal.  
10:30  
#### wolfgang z  
ja, + » 30k ^FB^ 10k -GND logisch ergibt 1,25V am FB Eingang des XR2981, was der Vref Bandgap entspricht.  
10:31  
parallel zu jedem R sind freie Pads, damit man hier einen anderen R dazu schalten kann, um die Spannung zu variieren. Da muss man nichts rauslöten.  
10:33  
Stefan  
Ich wollte es aber variabel haben! 😎 Daher die Lösung mit dem Spindeltrimmer.  
10:34  
#### wolfgang z  
völlig egal - dann halt an die 3 freien Pads und entsprechenden Trimmer und geht auch. Dann ist ein Teilwiderstand des Trimmers ||zum einen SMD und der andere Teil ||zum anderen SMD.  
10:36  
Du kannst einen fixen Spannungsteile auf diese Art IMMER verstimmen.  
10:37  
Stefan  
Geht freilich auch. Ich such mir immer eine Lösung, die meine Bastelkiste hergibt.  
10:38  
#### wolfgang z  
10:44  
steht für 12V sogar in der Schaltung  
Vout = 1.24 * (1+(91k/10k)=12.52V  
wobei R1=91k wegen schlechter Qualität schwer lesbar.  
10:48  
Bei mir mit R7=3002=30k & R9=1002=10k  
Vout = 1.24 * (1+30/10) = 4.96 V  
❤  
16:09  
Stefan  
Ich hab jetzt mal die beiden Varianten verglichen, 12V und 5V, die ich zuhause habe. Offensichtlich ist es doch ausschließlich der Spannungsteiler, der die Ausgangsspannung festlegt. Bei 12V ist 10K/91K verbaut, bei 5V 10K/30K. Meine Annahme , dass da noch mehr Unterschiede sind, war falsch. Mit einem Trimmer kann man so die Ausgangsspannung vermutlich stufenlos von 5-12V regeln. Probieren werde ich das mit der 12V-Variante, falls die kaputt geht, isses nicht schlimm. 🙂  
Geschrottet habe ich ein solches Teil wohl, als der eingelötete R den Kontakt verloren hat und dadurch sich der Regler wohl selbst gekillt hat.  
Das soll es aber auch gewesen sein zum Thema, geht hier ja erst mal um den E22/ESP32  
17:06  
#### wolfgang z  
Natürlich, sagt ich ja bereits. Und die Schaltung ist auch sehr leicht verständlich und die einzelnen Module gut getrennt:  
Akkulader > Akku > Spannungswandler  
17:06  
Ja, wird sicher funktionieren, da an die freien Pads löten kein großes Problem darstellen sollte.  
17:09  
Genau, das ist ein Thema beim Elektronik-Design, dass man bei kritischen Schaltungen, wo Trimmer/Potentiometer verwendet werden, ein Abheben des Schleifkontaktes auftreten kann und man das entsprechend berücksichtigen muss, den Widerstand zu begrenzen und nicht unendlich lassen werden.  
Daher nur parallel den Trimmer ≈200k oder größer löten.  
17:10  
Induktivität & hohe Schaltfrequenz => hohe Spannungsspitzen => 💀  
18:53  
#### wolfgang z  
schon wieder ... eine Node mit E22 ... dass wir das aber nicht reproduzieren können, das ist eigenartig.  
Aber mit der neuen FW wird das hoffentlich Geschichte sein.  
19:45  
#### wolfgang z  
💥 "I had a Dream"  
• Was passiert, wenn durch einen Lötfehler die RX <-> TX Pins am ESP32 verbunden wurden?  
Beim Einlöten der Stiftleiste oder auf der PCB.  
• Dann besteht tatsächlich eine Chance, dass die Bootloader Message von TX > RX kommen können und somit als Aussendung interpretiert werden.  
? Was meint ihr?  
Ist zwar noch nicht ganz schlüssig, aber u.U. möglich.  
Vlt. probiere ich es über einen 100Ω Widerstand.  
@oe1kbc bitte nochmals überprüfen, ob ALLE Buffer nach dem initialen Ablauf gelöscht werden. Und erst danach Text-Messages akzeptiert werden.  
20:04  
#### wolfgang z  
✅ Tja, das war erfolgreich ‼️  
Schaut am Dashboard auf TEST ...  
es wird wirklich ALLES gesendet, und auch verstümmelt tw.  
Aber der Zusammenhang dass das "nur" mit leer werdenden Akku und REBOOT passiert, der ist noch nicht ganz klar.  
20:08  
ABER: Wenn so eine schlampige Lötung der PCB++ erfolgte, dann ist auch nicht auszuschließen, dass es noch weitere Lötfehler geben könnte.  
Auch die Aussage "nach dem Nachlöten alles Lötstellen funktionierte es", weist darauf hin.  
Daher konnte ich es nicht nachstellen, da meine Lötstellen ordentlich sind. 😉  
20:11  
Ohh ja, das könnte schon sein:  
• Wenn der Akku genug Spannung liefert, dann ist der USB-Serial-Chip (CP2102) viel stärker und überschreibt das alles.  
Wenn aber der Akku schwach wird, dann stellt der CP2102 seine Funktion ein und der Kurzschluss wird voll wirksam.  
Aber ich will mir da keinen Chip grillen, indem ich eine fixe Verbindung mache.  
=> Das würde auch die Aussage stützen: "Der USB-Serial Chip war auch defekt" von jemanden.  
Denn wenn RX-TX verbunden sind, dann arbeiten 2 Ausgänge (TX-TX) gegeneinander und können eine Zerstörung bewirken.  
❤  
20:15  
Photo  
244×63  
so ist das bei manchen Boards mit 0Ω  
bei "besseren" Boards sind da jeweils 1k Widerstände in Serie  
20:21  
seht hier: https://t.me/c/1987218802/11812/23030  
20:40  
#### wolfgang z  
✅ Mit der neuen FW y.06.04 ist auch dieser Fehler nun Geschichte.  
20:43  
Erklärung:  
In vielen Output auf die Konsole (Terminal, USB) sind ":" enthalten.  
Die geniale, einfache Lösung von @oe1kbc Kurt, eine Message über das Terminal nun mit "::" beginnen zu müssen, unterbindet ALLE Texte, wo zu Beginn nur ein ":" steht.  
20:53  
5 June 2025  
07:45  
Wolfgang  
So, kurze Info zu meinem Problem, ich konnte Das DevKit wiederbeleben nach dem ich ein Reset auf werkseinstellungen zurückgesetzt habe... die dinger sind ja fast nicht kaputt zu bekommen. Der Esp war in einem Bootloop gefangen und hat immer wieder ein reset durchgeführ. das Devkit auf Programmiermodus geschalten und im Chrome mit 115200 Baud -> https://espressif.github.io/esptool-js/ Verbunden. Danach den Flashspeicher gelöscht. Arduino IDE auf macht und einfach ein esp32 programm (bei mir ESP32 Info) draufgeladen. Der Chip macht wieder was er soll und kann wieder ganz normal benutz werden  
10:50  
#### wolfgang z  
Fein, dass du das geschafft hast.  
ABER:  
• "ein Reset auf werkseinstellungen" was meinst du damit?  
• "das Devkit auf Programmiermodus geschalten" Hää? Das muss man doch nicht und kann es auch nicht. Das macht esptool sebständig.  
• "den Flashspeicher gelöscht." geht doch auch ganz normal über den Web-Flasher  
• "Arduino IDE ... ein esp32 programm ... draufgeladen." Wozu das? Verstehe die Notwendigkeit nicht.  
Ein FULL Flash inkl. ERASE macht das doch alles, oder?  
11:23  
Wolfgang  
ja aber wenn der USB Serial Wandler immer die Verbindung zum PC trennt, kannst du das schon versuchen... mit Full Flash... deshalb habe ich das in mehreren schritten gemacht. Die Herausforderung daran war die die permanente Verbindung wieder zu bekommen...  
11:27  
#### wolfgang z  
Ahh, ok, das ist interessant!  
Denn ich habe auch schon bemerkt, dass mit HUHN die Verbindung bei einem REBOOT unterbrochen wird, woran ich mich nicht erinnern kann, dass das früher auch so war, denn das wäre mir schon bei der Entwicklung der PCB aufgefallen.  
Ist es dir möglich, die EXAKTEN Schritte zu reproduzieren und mir schicken?  
Heißt das jetzt, dass die serielle Verbindung nun bei einem REBOOT nicht mehr unterbrochen wird?  
PS: mit einem anderen Terminalprogramm passiert das eh auch nicht.  
11:55  
#### wolfgang z  
Nein, das Mysterium bleibt weiter bestehen, dass HUHN die serielle Verbindung bei einem REBOOT verliert (unter GoogleChrome)  
Aber nur beim ESP32-DevKitC-V4  
🤨  
15:36  
#### wolfgang z  
Ich benötige Denkhilfe/Ideen - BITTE ...  
Ich habe schon einiges recherchiert, versucht, ...  
FAKT:  
1) ich kann mich erinnern, dass es früher (ältere FW) keinen Abbruch gab.  
2) Gleiches PCB, gleiches ESP32-DevKitV-V4 Modul:  
=>• µPython: keine Unterbrechung  
=>• Arduino-IDE I²C Testprogramm: keine Unterbrechung  
?• MeshCom FW: Unterbrechung  
?• Meshtasic FW: Unterbrechung  
... es ist extrem lästig !!!  
15:39  
3) HTerm 0.8.9: keine Unterbrechung  
4) TLORA, T-BEAM, ESP32-S3 mit letzter FW: keine Unterbrechung  
15:46  
Helmi Beh  
Als Input für mein Denken: was ist HUHN? Für dich: Beim Booten bringt der ESP seine Bootmeldungen mit 74880 Bd. Vielleicht bringt das dein Hühnchen ausser Tritt? Die anderen Terminalprogramme können das ab.  
15:46  
#### wolfgang z  
https://serial.huhn.me/  
15:47  
eben nicht! Es sind 115200 Bd - deswegen haben wir ja diese Baudrate gewählt.  
UND: der selbe ESP32 mit µPy oder Arduino-IDE-Testprogramm macht keine Unterbrechung  
15:50  
Helmi Beh  
Nachdem ich Firefox verwende, gebrauche ich sowieso ein gescheites Terminalprogramm und nix Browserbasiertes. Ansonsten hab ich für solche Spezialfälle mein "Y-Kabel". Da kann ich mit zwei zusätzlichen USB-seriell-Wandlern direkt sehen, was auf den RX- und TX-Leitungen so vorgeht.  
15:52  
Huch, wo kann man die ESP32-Bootmeldungsbaudrate umstellen? Die ist doch im Bootloader fest vorgegeben!  
15:52  
#### wolfgang z  
Die ist von espressif vorgegeben mit 115200  
ev. im Bootloader  
15:56  
Helmi Beh  
Ach sorry, das war vom ESP8266.  
👍  
16:02  
Gibt's irgendwo die .bin zum herunterladen, da mein Firefox ja keinen Webflasher unterstützt?  
16:04  
Helmut OE5HWN  
Releases · icssw-org/MeshCom-Firmware  
https://github.com/icssw-org/MeshCom-Firmware/releases/  
👍  
17:32  
Stefan  
Hier mit aktueller Software auf dem E22/ESP32 kein Abbruch beim reboot. Mit dem Göker und auch mit der Webflasher-Konsole alles ok. Ist auch bei mir nie anders gewesen.  
17:34  
#### wolfgang z  
eigenartig ... was ist da bei mir anders?  
17:36  
Stefan  
Die Frage kann ich dir nicht beantworten. An der FW scheint es eher nicht zu liegen.  
17:38  
#### wolfgang z  
Dann werde ich es mal auf dem anderen Notebook versuchen.  
17:47  
Photo  
330×57  
es gibt schon einen signifikanten Unterschied:  
COM3 = ESP32 (CP2102)  
COM6 = ESP32-S3 (USB-Enhanced-SERIAL CH343)  
18:03  
#### wolfgang z  
Negativ, gleicher Effekt. Aber es wird zumindest mal CP2102 erkannt.  
OK, dann muss es wohl beim HUHN liegen.  
MS-EDGE & Google Chrome getestet, gleicher Effekt (Win10)  
18:56  
#### wolfgang z  
💥 Problem eingekreist und gefunden:  
E (69) esp_core_dump_flash: <14>æž<26>½É•dump partition found!  
Hier => <14>æž<26>½É•  
kommt es zu einem Framing Error! Dieser wirft die Verbindung offenbar. Andere Terminalprogramme ignorieren den.  
Das ist wahrscheinlich (sicher) im BOOTLOADER.  
Abhilfe-Varianten:  
• anderen BOOTLOADER  
• Mit GPIO15-1k-GND Bootloader Ausgabe unterbinden.  
• Core Dump partition definieren  
19:01  
Stefan  
Aber warum taucht das Problem nur bei dir auf?  
19:29  
#### wolfgang z  
Photo  
664×37  
Nein, ist es NICHT => BREAK => disconnected  
Google Chrome Browser, esptool.oesvsv.at > LOG-Console  
19:29  
Das würde mich auch sehr interessieren.  
19:46  
#### wolfgang z  
habe ich keinen, nur den Windows Defender  
19:47  
außerdem, was soll der bez. Serieller Schnittstelle machen, wenn ein BREAK darauf kommt.  
19:55  
Stefan  
Vielleicht ist Windows das Problem... 😀😎 ich hab ja nur Mac...  
Nee, auch ein Win-Notebook, teste ich nachher mal.  
Update: Getestet, keine Verbindungsabbrüche bei --reboot  
20:02  
#### wolfgang z  
So, GPIO15-GND unterbindet zwar den 1.Teil der Bootloader-Ausgabe, aber die letzten 2 Zeilen sind immer noch da. Und somit auch der FramingError = BREAK  
[KEEP]...KEEP1F28CCECOE3WAS-224.34y  
E (49) esp_core_dump_flash: No core dump<\0><\0>…ÉÑ¥Ñ¥½¹found!  
E (49) esp_core_dump_flash: No core dump partition found!  
============  
CLIENT SETUP  
20:03  
Irgendjemand hat doch geschrie#### ben, dass er eine Core Dump Partition angelegt hat.  
Was muss ich da ändern?  
20:05  
Thomas - DO1TFS  
partitions-4MB-safeboot.csv  
# Name ,Type ,SubType ,Offset ,Size ,Flags  
nvs ,data ,nvs ,36K ,20K ,  
otadata ,data ,ota ,56K ,8K ,  
safeboot ,app ,factory ,64K ,704K ,  
app ,app ,ota_0 ,768K ,3264k ,  
coredump ,data ,coredump, 4032K ,64K ,  
20:06  
partitions-4MB-safeboot.csv  
260 B  
20:08  
#### wolfgang z  
DANKE, was muss ich dann noch beim compile beachten?  
20:11  
Thomas - DO1TFS  
musst safeboot, partitions neu comp. und flashen, also komplett flash nicht nur die firmware.bin flashen  
20:13  
danach kannst wieder die schnelle variante nehmen (firmware.bin via otg o.ä.)  
20:14  
wobei eigentlich müsstest du nur die partition.bin flashen  
👍  
20:14  
#### wolfgang z  
ja, klar. die wird ja eh allgemein erzeugt.  
20:15  
Stefan  
Wäre das nicht ne Idee, das ganz allgemein anzulegen? Auch wenn da etwas Speicherplatz draufgeht?  
20:17  
#### wolfgang z  
Natürlich wäre das ideal. Zusammen mit GPIO15 (über Jumper natürlich) wäre dann endlich Ruhe und nur der Output der FW.  
20:19  
Thomas - DO1TFS  
denke die cordump geht auch kleiner (1kb) hab jetzt nur damit gestestet weil VSC das vorgeschlagen hat  
20:33  
#### wolfgang z  
"The coredump partition subtype is used to store the core dump on the flash. The core dump is used to analyze critical errors like crash and panic. This function must be enabled in the project configuration menu and set the data destination to flash. The recommended size for this partition is 64 kB (0x10000)."  
https://docs.espressif.com/projects/arduino-esp32/en/latest/tutorials/partition_table.html?highlight=partion%20table#partition-table  
20:34  
Thomas - DO1TFS  
ahhh deswegen hat VScode das so vorgeschlagen  
20:38  
#### wolfgang z  
"The minimum size for a core dump partition on an ESP32 is 4 KB (4096 bytes). This is the minimum size for any partition on the ESP32."  
20:40  
Thomas - DO1TFS  
dann die letzten 2 zeilen  
app ,app ,ota_0 ,768K ,3324k ,  
coredump ,data ,coredump, 4092K ,4K ,  
20:44  
#### wolfgang z  
mit 64K noch kein Problem offenbar:  
RAM:   [==        ]  22.7% (used 120688 bytes from 532480 bytes)  
Flash: [====      ]  44.3% (used 1481849 bytes from 3342336 bytes)  
20:49  
Thomas - DO1TFS  
Photo  
620×56  
4kb läuft durch  
20:49  
#### wolfgang z  
✅ endlich RUHE IN DER BUDE ❗️ [KEEP]...KEEP1F28CCECOE3WAS-224.34y  
============  
CLIENT SETUP  
============  
[HEAP]...148312 (free)  
20:49  
Thomas - DO1TFS  
😂👍  
20:52  
is nur die frage was er jetzt sendet statt no core dump....  
20:52  
#### wolfgang z  
Eben NICHTS, da eine Partition vorhanden ist!  
20:53  
Thomas - DO1TFS  
ja dann aber viel. nie nächste zeile nach no core dump  
20:53  
nie=die  
20:54  
#### wolfgang z  
Es gibt keine Ausgabe vor dem "=====..." aus der FW beim Booten.  
20:54  
Thomas - DO1TFS  
ahh ok  
20:55  
#### wolfgang z  
UND: es gibt in der gesamten Ausgabe KEINE Zeile mit "::" beginnend.  
20:55  
Thomas - DO1TFS  
na dann hoffen wir mal...  
20:56  
gibst du das an Kurt weiter als Issue  
👍  
9 June 2025  
13:57  
#### wolfgang z  
erledigt, siehe hier auch mit vollständiger Erklärung:  
https://github.com/icssw-org/MeshCom-Firmware/issues/486  
👍  
14:41  
#### wolfgang z  
❗️✅ Auch dieser Effekt ist nun geklärt:  
• wenn man sich mit https://serial.huhn.me/ zu einer Node verbindet, wobei gerade ein Output auf der Seriellen Schnittstelle erfolgt, kommt es zu folgendem Effekt:  
�y�G�y ��Y���,������)��[WIFI]...SSID: Drei_H288A_24G_yAFG CHAN: 8 RSSI: -43 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...connecting to CHAN: 8 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...power: 8 RSSI:-41  
Diese unerkannten Zeichen entstehen dadurch, dass bei dem Verbindungsparameter 8N1 keine Möglichkeit besteht, den Beginn eines Zeichens richtig zu erkennen.  
Erst nach einer "Pause" kann die Synchronisation erfolgen.  
11 June 2025  
07:43  
Juergen DF2AP  
Guten Morgen. Heute gibt es wieder das ESP32 Dev Kit C V4 bei AZ-Delivery im Angebot. Das 3er-Set für 14,99€.  
https://www.az-delivery.de/products/esp-32-dev-kit-c-v4?variant=30871551869024&utm_source=90-Days-Engaged&utm_medium=email&utm_campaign=110625_AZ-ESP32%20Dev%20kit%2BE-paper%20display_promo_microcontroller_LVC&utm_id=01JXCC4F21C84EC2XQMSC7R0PE&utm_term=Campaign&utm_content=👉%20Jetzt%20zuschlagen%20👈&_kx=b2nJXzFUmZF_Rht_n9MewZS-R95z-K-0YgkW6K9F5hdDH8S0JoqPcYl_FPEAP9cG.QVRJMi  
15 June 2025  
11:22  
Stefan  
Info zu den Platinen: Ich werde zur HamRadio fahren und die letzten Exemplare mitnehmen . Falls wer noch einen E22-Node aufbauen mag, einfach bei mir melden  
👍  
16 June 2025  
07:51  
Wolfgang  
Jetzt muss nur noch das USB C Break Out Bord vom Ali kommen....  
👍  
08:01  
#### wolfgang z  
❗GPIO15 mit 1k Widerstand auf GND ❗️  
10:38  
Wolfgang  
wie meinst du das?  
15:53  
#### wolfgang z  
Genau so wie ich es geschrieben habe.  
Mit anderen Worten:  
Den GPIO15 Pin des ESP32 über einen 1kOhm Widerstand mit GND verbinden  
15:54  
Siehe hier https://t.me/c/1987218802/11776/23410  
17 June 2025  
18:44  
Wolfgang  
danke, hatte das nicht auf dem plan mit den Fehlaussendungen.  
18:48  
btw hab ne "Alternative" zum Ali USB Breakout gefinden, ist zwar breiter, aber schneller ferfügbar. https://www.amazon.de/dp/B0C1YV339S?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1  
23:02  
#### wolfgang z  
Grundsätzlich ja, aber du musst dann die richtigen Anschlüsse verbinden.  
18 June 2025  
07:16  
Wolfgang  
das ist schon klar, aber die bekomme ich ja aus der PCB zeichnung raus... und ich benötige keine 5k1 wiederstände, die sind da schon drauf. um die PowerDeliver zu erhöhen  
👍  
19 June 2025  
12:52  
Wolfgang  
So nach stundenlangem suchen und neu Flaschen des DEV Modul, versuchen die "neue" FW zu Kompilieren, muss ich jetzt das Teil erst mal in die Ecke stellen und mal vergessen... Das Teil lässt keine Bluetooth Verbindung zu, die WLAN Verbindung bricht nach ca 20 Minuten ab und ich muss den Node Neustarten... Ist so für mich nicht wirklich sinnvoll da weiter zu machen...  
20 June 2025  
23:41  
#### wolfgang z  
Ich komme morgen am Samstag aus dem Urlaub zurück. Ab Sonntag dann kommen laufend die Informationen zu den letzten Änderungen und was man beachten muss und einstellen kann. Wird sich aber sicher über die nächste Woche(n) hinziehen.  
22 June 2025  
11:23  
#### wolfgang z  
So, bin zurück und wieder aktiv.  
Was ist eigentlich dein Problem genau?  
• Du verwendest ESP32-E22 V2.1.2 PCB?  
• Welches GPS-Modul?  
• Welche FW?  
...  
23 June 2025  
07:35  
Wolfgang  
Also, Ich hab das ESP32-E22 V2.1.2 PCB, bestückt habe ich fast alles was zu bestücken war, C2 habe ich nicht eingelötet. den 1K Widerstand auf GPIO 15 habe ich auch eingelötet. Das GPS Modul ist ein U-Blox Neo 6M. Als FW habe ich die v4.34z vom Web-Flasher drauf. mein Problem besteht im moment darin, dass die Kiste sich nach ca 3 bis 5 Stunden irgendwo aufhängt und nicht mehr erreichbar ist, weder per Web (was nur übers Smartphone geht, verdacht von mir dass der Adblocker den zugriff am PC verhindert. Hab von einem Laptop aus und Firefox zugriff erhalten) noch über Bluetooth. erst nach entfernen des Netzteiles und Neustarten des Gerätes ist es wieder erreichbar. Der plan war eigentlich das E22 Board als Gateway für meine Region zu nutzen und ne X30 dran zu hängen, oder evtl. auf einer Anhöhe autark mit Solar-Panel und Akku zu betreiben. Wobei das mit den Verbindungsabbrüchen habe ich auch mit einem Heltec V3 was ebenfalls ca 3 bis 5 stunden läuft, danach alle Verbindungen blockiert. der Heltec ist Stock und auch mit der v4.34z geflashed.  
09:04  
Rainer OE1KFR  
Mein E22 hängt sich auch nach einigen Stunden auf.  
09:40  
#### wolfgang z  
Ok, danke mal für die Infos.  
1️⃣ Siehe hier https://t.me/c/1987218802/11777/23650 da hängt der Web-Client definitiv. Da muss Kurt ran.  
09:45  
2️⃣ leider hat Kurt mein Issue bez. des GPS noch nicht eingebaut, denn da ist noch ein signifikanter Tippfehler drinnen. Da kann bewirken, dass das GPS-Modul nicht richtig gelesen werden kann. https://github.com/icssw-org/MeshCom-Firmware/issues/463  
09:47  
3️⃣ Ich werde nun die z.06.18 z.06.23 für das ESP32-E22 selber kompilieren und flashen und dann laufen lassen. Mal sehen, ob sich da was zeigt. ...  
09:47  
Kurt Baumann OE1KBC  
Derzeit habe ich vier neue Hardware-Nodes auf meinem Tisch. zwei bereits inkludiert HELTEC-Stick und HELTEC-TRACKER jetzt kommen die zwei neuen Lilygo - stay tuned  
09:48  
Achtung seit heute früh gibt es 06.23  
10:06  
#### wolfgang z  
Photo  
350×60  
‼️das geht so NICHT, dass du das unter [common] in der allgemeinen platformio.ini setzt!  
Denn der ESP32-S3-DefKitC-1-N16r8 benötigt:  
        "-DARDUINO_USB_MODE=1",  
        "-DARDUINO_USB_CDC_ON_BOOT=0"  
10:08  
Kurt Baumann OE1KBC  
ok, wir haben bereits einige Nodes und wenn jeder von uns einige zum testen nimmt können wir diese unterschiede berücksichtigen. Wird gemacht  
❤  
10:09  
#### wolfgang z  
normalerweise ist da in der ...\boards\****.json drinnen.  
10:10  
Kurt Baumann OE1KBC  
in dem fall ist es ein standard ohne eigenes json .. ist auch nicht gut dass wir default boards selbst verändern ...  
10:11  
ich baue das in die variants ein  
👍  
10:18  
Aber wolfgang das passt schon so wenn man  
nur ${esp32.build_flags}  
und nicht auch ${common.usb_flags}  
aufruft  
dann wird das pro board unterschieden.  
Teste das bitte  
10:32  
#### wolfgang z  
hmm, ok, aber es gefällt mir überhaupt nicht, dass es immer noch die Duplikate unter \variants\***\platformio.ini gibt,  
obwohl offenbar ALLE Boards in der allgemeinen platformio.ini enthalten sind.  
Wozu ist das nötig?  
10:32  
Kurt Baumann OE1KBC  
Ist am Plan, geduld bitte  
10:33  
Muss man mit viel Gefühl, was muss an common usw. bleiben und was ist nur mehr in den variants  
11:09  
#### wolfgang z  
➡️ ESP32-E22 PCB läuft ab jetzt als OE3WAS-22 mit z.06.23 als GW ...  
17:37  
#### wolfgang z  
... Zwischenstand: OE3WAS-22 läuft ab 11:07 bis jetzt ohne Probleme als GW  
so, hatte vergessen, die Koordinaten zu setzen. Aber jetzt ist es auf mcmap.oesvs.at sichtbar  
Telemetrie nur BATT, da keine anderen Sensoren dran  
24 June 2025  
00:41  
#### wolfgang z  
... läuft jetz seit über 14 Std. ohne Probleme durch.  
Werde morgen ein GPS-Modul anstecken ...  
00:44  
Wie du sehen kannst, läuft meines problemlos.  
Was hast du anders als ich?  
OE3WAS-22 = GW, aber keine weiteren Sensoren, auch kein GPS, nur Terminal läuft mit.  
01:59  
#### wolfgang z  
So, nun GPS NEO-6M angesteckt und reboot um 01:52:04 ...  
War auf Std. 9600 Baud eingestellt und wurde automatisch auf 38400 Bd umgestellt und läuft.  
FIX wird es im Raum ev. nicht ge#### ben, oder sehr lange dauern, da mir der Akku auf dem Board "abhanden" gekommen ist; aber mal abwarten bis morgen früh ...  
02:09  
aber es tut sich was, da die GPS-Time nach 15' schon vorhanden ist:  
02:08:17 -----------check GPS-----------  
02:08:18 $GPRMC,000819.00,V,,,,,,,240625,,,N*7A  
02:08:18 $GPVTG,,,,,,,,,N*30  
02:08:18 $GPGGA,000819.00,,,,,0,00,99.99,,,,,,*66  
02:08:18 $GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
02:08:18 $GPGSV,2,1,07,08,,,20,09,,,28,12,,,28,17,,,22*7B  
02:08:18 $GPGSV,2,2,07,19,,,29,22,,,17,32,,,30*79  
02:08:18 $GPGLL,,,,,000819.00,V,N*4A  
02:08:18 newData:1 SAT:0 Fix:0 UPD:0 VAL:0 HDOP:9999  
02:06:52 GPS-UTC-Time <local:2.0 2025-06-24 00:06:53  
06:20  
#### wolfgang z  
Auch mit GPS läuft mein ESP32-E22 mit FW z.06.23 auch nach über 5 Std. ohne Probleme.  
10:42  
Michael DG1FBP  
/endlich läuft auch bei mir das gps am e22.. war schon am verzweifeln..mt der 06.23 ging es gleich los :)  
11:09  
#### wolfgang z  
Alles zum Fenster gelegt und schon war des FIX mit 7 Sats da.  
11:18  
Kurt Baumann OE1KBC  
Für den FIX benötigt man immer gute Signale  
11:19  
Sprich: Almanach lesen  
29 June 2025  
10:11  
Stefan  
Reminder: Letzte Möglichkeit, heute auf der Ham Radio noch Platinen für das E22/ESP32 -MeshCom Projekt zu bekommen. Am ICSSW-Stand gibt es noch einige Exemplare. 😊  
8 August 2025  
07:40  
Juergen DF2AP  
Guten Morgen. AZ-Delivery hat heute wieder ESP-32 Dev Kit C V4  
im Angebot. 3 Stück gibt es für 14,99€.  
https://www.az-delivery.de/products/esp-32-dev-kit-c-v4  
17 September 2025  
11:52  
Peter Kaminski  
Hallo, ich wollte einmal fragen, ob es noch Platinen gibt. Würde auch gerne ein Device bauen.  
11:53  
Stefan  
Hatte dir ne PM geschrieben dazu...  
13:36  
Peter Kaminski  
Super, bin Freitag wieder im Büro. Vieleicht habe ich später noch Möglichkeit der Antwort.  
20 September 2025  
18:43  
Elmar DK1ES  
Hallo, im Moment sind die E22 400M33S (SPI) etwas schwierig zu bekommen. Gibt es auch eine FW, die den E22 400T33S (UART) unterstützt?  
18:49  
Helmut OE5HWN  
Werden nicht unterstützt  
19:02  
Helmi Beh  
Die sind nicht in allen Parametern frei programmierbar. Die haben zu viele Einschränkungen.  
19:20  
Klaus  
Gibt's bei AliExpress keine mehr? Habe erst letzte Woche eine bekommen...  
19:25  
Elmar DK1ES  
Hallo Klaus, Du hast Recht, Danke für den Tipp.  
19:55  
Klaus  
Hallo Elmar, ich habe mir das Modul schon zweimal gebaut, mit den Bauteilen vom Ali und bin zufrieden. Dort gibt es auch den ESP32 mit einem zusätzlichen Anschluss fürs WLAN.  
19:57  
Stefan  
Zusätzlich nicht, der hat keine eingebaute WLAN/BT Antenne, also aufpassen... 😉  
20:03  
Klaus  
Hm, da ich meine MeshCom Module nur am Dach oder Outdoor verwende, kommt bei mir immer eine extra WLAN Antenne dran. Habe deswegen den ESP32 nicht ohne Antenne benützt.🤔  
👍  
15 November 2025  
20:24  
Juergen DF2AP  
Hallo Zusammen, ich habe aktuell den Node von DL5WB bei mir auf dem Tisch. Dieser hatte sich durch wirre Aussendungen in die Gruppe *all hervor getan. Bei mir konnte ich mich dann nicht richtig per BLE verbinden. Er hat hier nach dem Datenabruf auch wirre Sachen angezeigt und ich konnte keine Parameter ändern.  
Was hab ich schon probiert:  
- ich habe den ESP32 runter genommen und mittels Erase und neu flashen neu eingerichtet FW war dabei 4.35f  
- GPS und BME280 hab ich nicht aktiviert und die entsprechende Hardware getrennt um diese als Fehlerquelle auszuschließen  
- nach einiger Zeit konnte ich mich nicht mehr per WLAN mit dem Webinterface verbinden, der Node lief jedoch und BLE ging auch  
- das WLAN-Problem hatte ich auf Grund der heutigen neuen FW dort vermutet, ein Update auf 4.35h hat aber nichts geändert  
- ich hab letztlich den ESP32 durch einen anderen ersetzt, der sofort nach dem Einschalten wirres Zeug in die Gruppe *all gesendet hat  
Würde mich freuen, wenn wir gemeinsam versuchen, diesem Kerl den Unsinn auszutreiben und würde mich über Vorschläge zum weiteren Vorgehen freuen.  
20:26  
Ach so, kleiner Hinweis noch. Er läuft bei mir als DF2AP-98. Also wenn da Quatsch kommt, bitte einen Hinweis an mich.  
22:42  
Rainer OE1KFR  
Check mal die Stromversorgung und ob der Elko für den E22 verbaut ist. Das Netzteil muss 3A liefern. Dann mal die Sendeleistung runter drehen wegen HF Einstreuung. Schätze da ist direkt eine Antenne drauf oder exetern?  
23:49  
#### wolfgang z  
und WIE die Stromversorgung erfolgt!?!  
23:50  
somit liegt der Fehler "eindeutig" am PCB, wie ich ja auch schon damals geschrieben hatte: LÖTFEHLER !!!  
23:51  
Oder eben eine ungeeignete Stromversorgung, dh. ein DC-Wandler-Modul, welches massive Störungen verursacht!  
(Das hatte jemand auch schon mal.)  
23:53  
siehe https://t.me/c/1987218802/1/26183  
23:56  
Bitte möglichst detaillierte scharfe Fotos von der bestückten PCB von beiden Seiten.  
16 November 2025  
09:02  
Juergen DF2AP  
Danke für die Rückmeldung. Ich such die Infos zusammen und mach mal Fotos und melde mich dann hier nochmal.  
👍  
11:59  
Juergen DF2AP  
So hier die Fotos der Platine. Die Platine ist eine Nachfertigung eines OMnaus Thüringen aus Fernost. Daher die rote Farbe.  
12:01  
12:01  
Mit OLED  
12:01  
12:01  
Ohne OLED  
12:02  
OLED-Modul  
❤  
12:02  
Die Stromversorgung erfolgt bei mir über eine Power Bank mit 3A Ausgang.  
12:03  
R3 und R4 sind korrekt und mit den richtigen Werten verbaut. Ich schließe an der USB-C Buchse auf der Platine an, also nicht direkt am ESP.  
12:04  
C3, C4 und C5 sind korrekt und wenn notwendig auch polungsrichtig verbaut.  
12:05  
C6 hat statt 470 220 ist aber polungsrichtig verbaut.  
12:06  
D1 ist korrekt und richtig rum drin.  
12:08  
Es sind noch Bauelemente rund um den HW-613 bestückt. Der Regler ist aber gar nicht verbaut.  
12:08  
D3 ist auch richtig rum bestückt.  
12:09  
OLED ist drauf und hat scheinbar verdrehte Anschlüsse (siehe Foto). Zusätzlich ist auf der Platine eine Brücke JP1 JP2 eingelötet, allerdings nicht über Kreuz?  
12:10  
Das Display leuchtet aber.  
12:12  
Was noch auffällt ist, dass das Webinterface nach ein paar Minuten Laufzeit nicht mehr erreichbar ist. Mein Router zeigt es aber weiterhin als verbunden an…. Das kann natürlich ein ganz anderes Problem sein. Ist aber auch seltsam.  
12:18  
Ach so: Antenne ist extern und ich hab die Ansteuerung für den E22 auch schon auf 10dB runter gedreht.  
12:19  
C2 ist wie beschrieben auf der Platine nicht bestückt.  
13:02  
#### wolfgang z  
Ok, danke für die ausführlichen Infos.  
Auf den 1. Blick kann ich keinen Fehler sehen.  
Aber verstärke C6 durch einen zusätzlichen 220µF Elko parallel.  
Falls du einen Oszi hast, könntest du mal die Versorgungsspannung am E22-Modul ansehen, ob da irgendwelche Spikes auftreten. Ebenso direkt am ESP32-Modul auf der Stiftleiste oben.  
13:07  
Bitte davon noch genaues Fotos!  
1) JP1 & JP2 sind par default als Leiterbahn vorhanden!  
2) Über Kreuz auf der Leiterbahn ist NICHT vorgesehen:  
=> wenn default, dann so:  
13:08  
hier sind die Leiterbahnen eh schon vorhanden!  
13:08  
13:11  
Wenn aber das OLED GND-VCC-SCL-SDA hat, dann muss man diese beiden Leiterbahnen unterbrechen und mit Jumper HORIZONTAL verbinden, ohne die OLED auskreuzen zu müssen. Das ist der Sinn dieser beiden JP1 & JP2.  
13:12  
Rainer OE1KFR  
Der Elko ist zu klein. Ich hab 2000uF drinnen. Hab damals Leistung gemessen und darunter bricht sie ein.  
13:13  
#### wolfgang z  
ergänze bitte diesen 1K Widerstand noch!  
13:14  
Helmi Beh  
Ich kann es zwar nicht so ganz richtig beurteilen, da die Auflösung nicht so gut ist, aber manche Lötstellen sehen eher nach Klebestellen aus. Schon mal alles nachgelötet?  
13:15  
#### wolfgang z  
ja, wäre auf jeden Fall gut.  
Aber diese Flecken könnten auch nur Reflexionen von Lötrückständen sein.  
13:17  
Welchen meinst du?  
Es kommt aber auch auf die Qualität des Elkos an!  
Ich habe z.B. C3 = 330µF Tantal-Elko drinnen und das funktioniert problemlos!  
13:18  
Rainer OE1KFR  
Der Puffer für den E22  
13:18  
#### wolfgang z  
C3 = 330µF Tantal-Elko  
13:19  
Helmi Beh  
Man sieht es vor allem auf der Bestückungsseite. Da ist teilweise kein Lot sauber durchs Loch geflossen. Wahrscheinlich zu niedrige Temperatur oder zu kurz gelötet.  
13:19  
Rainer OE1KFR  
Das ist meiner Meinung nach zu wenig. 1000uF min  
13:20  
#### wolfgang z  
Das ist nicht notwendig, da es ja Durchkontaktierungen sind.  
13:26  
1x 1000µF ist kontraproduktiv mit einem normalen Wickel-Elko. Da ist es besser, 2x 470µF zu bestücken.  
Daher reicht mein 330µF Tantal auch!  
13:27  
Noch besser wäre eine Stufung von 470µF + 220µF + 47µF.  
13:30  
Juergen DF2AP  
Danke erstmal für die Infos. Lotungen sehen qualitativ gut aus, hab mit der Lupe drüber geschaut. Die Platinen sind sehr gut durchkkntsktiert, da muss das Lot nicht auf der anderen Seite raus kommen. Aber ich kann natürlich nochmal nachlösen. Schaden tut das ja nicht.  
13:31  
Ist der im Schaltplan drin? Wenn nicht, hat den keins meiner Boards. Was macht der Widerstand?  
13:32  
So hatte ich das auch verstanden. Heiß dann aber, dass die Brücken auf der Platine weder nutzen noch stören.  
13:33  
Die ohnehin vorhandene Leiterbahn ist dann quasi zusätzlich durch zusätzliche Brücken verstärkt.  
👍  
13:35  
#### wolfgang z  
Das ist die Erweiterung, die ich auch beschrieben habe und das Ergebnis der Analyse der vormaligen Fehlaussendungen.  
GPIO15 - 1KΩ - GND verhindert die Boot-Loader-Meldungen.  
Siehe auch hier in der Gruppe ...  
siehe hier: https://t.me/c/1987218802/11776/23410  
👍  
13:37  
Juergen DF2AP  
Das verbaute OLED-Modul.  
13:38  
Die Kreuzung hat Bernd schon hier gelöst.  
13:39  
#### wolfgang z  
genau - das hat die VCC-GND verdreht.  
Daher so wie gezeigt die Beinchen auskreuzen, oder wie beschrieben die JP1 & JP2 ändern.  
13:40  
Juergen DF2AP  
Ich hab noch die Info bekommen, dass Bernd wegen seines OLED-Moduls hier horizontal gebrückt hatte, ohne die Leiterbahnen zu durchtrennen.  
13:41  
Da gab’s kurz Funkverkehr 🤪  
13:42  
Und anschließend war wohl der ESP32 hinüber. Hoffe, dass da nicht noch mehr Schaden entstanden ist.  
13:45  
Ich werde jetzt erstmal folgendes machen:  
- nachlöten  
- Elko C6 anpassen (muss schauen, was ich habe) entweder 470 rein oder 220 parallel  
- 1K Widerstand ergänzen  
Melde mich anschließend.  
13:47  
#### wolfgang z  
🔥💥Das macht einen KURZSCHLUSS zw. VCC = GND ‼️  
13:49  
Juergen DF2AP  
Ja genau. Wenn ein intelligentes Netzteil dran war, sollte eigentlich nichts kritisches passieren.  
13:49  
#### wolfgang z  
Bevor man als ungelernter Elektroniker etwas eigenmächtig tut, ohne zu wissen, was man tut, dann wäre es besser gewesen, bei mir nachzufragen!  
Oder den Schaltplan richtig lesen und auch verstehen, was man tut.  
13:49  
13:50  
Juergen DF2AP  
Deswegen bin ich mit dem Problem ja jetzt hier bei den Profis 😊  
13:50  
#### wolfgang z  
Sticker  
⚡️  
13:51  
Nicht unbedingt. Da ein so massiver Kurzschluss auch ev. ungewollte Effekte im Netzgerät ausgelöst hat. Und wenn man das dann wieder verwendet, dann ...  
13:53  
Juergen DF2AP  
Bin erstmal unterwegs. Melde mich später nach den Hausaufgaben wieder. Kann ein bisschen dauern. Erstmal Harmonische besuchen.  
13:53  
Schon mal herzlichen Dank 👍  
14:01  
#### wolfgang z  
‼️ Was mir gerade noch einfällt:  
Wenn eine Diode überlastet wird, dann kann es unerwartete Effekte geben:  
• Diode = Kurzschluss, dh. keine Diode mehr  
• Diode = hochohmiger, dh. mehr Spannungsabfall  
das kann aber nicht mehr so einfach mit einem einfachen Messgerät festgestellt werden, da abhängig vom Strom!  
• Diode = Unterbrechung  
➡️ daher ALLE Schottky-Dioden, die seriell im Spannungspfad liegen, vorsorglich mal AUSTAUSCHEN/ERNEUERN ❗️  
14:05  
Wenn über USB-C versorgt wurde, dann D1  
Wenn über Schraubklemme J3 versorgt wurde, dann D2 und zusätzlich F1 überprüfen!  
14:07  
klar, es wurden ja die 3V3 kurz geschlossen.  
Und daher ist der 3,3V LDO am ESP32 hinüber !!!  
Den Austausch habe ich hier beschrieben:  
https://t.me/c/1987218802/11812/21679  
und nachfolgende Beiträge  
19 November 2025  
13:52  
Juergen DF2AP  
Node von DL5WB - aktueller Sachstand:  
- alles nochmal nachgelötet  
- 220 Elko parallel zum 220 auf der Platine ist drauf  
- 1 K Widerstand ist auch ergänzt  
- Z-Diode ist mangels Ersatz aktuell noch drin  
Mal schauen, wie er sich verhält.  
13:53  
So sieht’s jetzt aus.  
14:10  
#### wolfgang z  
Aber die Schottky-Diode(n) sind wahrscheinlich ja eh noch ok, da ja nur die 3V3 kurz geschlossen wurde und somit der 3,3V-LDO am ESP32 Board defekt wurde, wie ich ja beschrieben hatte.  
14:10  
Ja, schaut gut aus. Bin gespannt ...  
14:12  
ev. noch einen parallel zum E22-Elko C3 !  
21:12  
Juergen DF2AP  
C3 war korrekt mit 470µF bestückt. Nur C6 war mit 220µF bestückt. Da hab ich noch einen 220µF parallel dazu.  
21:13  
Node scheint aktuell "noch" unauffällig zu laufen. Ich hab im Moment GPS und WX-Sensor noch nicht dran. Lass ihn mal einen Tag laufen. Wenn das soweit klappt, steck ich die Hardware wieder an.  
21:20  
Die Sache mit dem Webinterface bleibt mysteriös. Ich habe aktuell zwei Nodes im Parallelbetrieb. DF2AP-98 und DF2AP-99. Beide Nodes ziehen sich unterschiedliche IPs: AP-98 XXX.XXX.X.178 und AP-99 XXX.XXX.X.114.  
Einer der beiden ist nach kurzer Zeit jeweils extrem langsam oder gar nicht mehr per Webinterface zu erreichen. Im Moment habe ich das Gefühl (müsste ich nochmal verifizieren), dass der später ins WLAN eingebuchte jeweils die Probleme macht. Auf alle Fälle wechselt der Effekt zwischen den Nodes. Ist also vermutlich kein Defekt am Node.  
21:27  
Helmi Beh  
Wieviele Nodes sind denn in deinem Router eingebucht (Fritzbox???)? .178 ist schon ein ziemlich hoher Wert für die Tabelle.  
22:12  
Juergen DF2AP  
Ich habe kein WLAN über die Fritzbox. Ich nutze Ubiquiti APs. Die IP XXX.XXX.X.1 bis XXX.XXX.X.99 sind bei mir für statische IP reserviert.  
22:17  
Helmi Beh  
Schau doch mal, wie lang dort die Routingtabelle sein darf. Könnte sein, dass die voll ist und deswegen der letzte Teilnehmer schlechter geht.  
22:19  
Juergen DF2AP  
Ich hab IP-Adressen, die über XXX.XXX.X.200 gehen und funktionieren.  
22:19  
Helmi Beh  
Dann vergib doch mal feste IPs und probiere das dann aus.  
22:20  
Juergen DF2AP  
Gute Idee. Probier ich morgen mal aus und melde mich wieder.  
22:20  
Dankeschön 👍  
20 November 2025  
00:17  
#### wolfgang z  
Gut, und was würdest du meinen, was jetzt die volle Funktion gebracht hat?  
Doch Lötfehler gewesen? Oder Elko? Oder ...?  
09:31  
Juergen DF2AP  
So richtig kann ich es nicht sagen. Das Teil lief vorher teilweise recht lange problemfrei und hat dann angefangen Unsinn zu machen.  
Nachdem ich jetzt drei Sachen gemacht habe, wird es schwierig da eine qualifizierte Aussage zu treffen. Außerdem steht der Langzeittest noch aus.  
Ich hab aktuell auch noch einen von meinen ESP32 drauf. Ich steck heute mal den Ursprungs ESP32 drauf. Mal schauen, ob der auch problemfrei läuft.  
Wir bleiben mal dran und machen Schritt für Schritt weiter.  
👍  
10:50  
Klaus  
Das Problem mit dem WLAN ist bei einem meiner beiden ESP32 Nodes auch schon aufgetreten. Aus heiterem Himmel, wollte im Browser von den Nachrichten auf Mheard wechseln oder umgekehrt. Passiert selten, aber hier beim lesen sehe ich Parallelen. Ich tippe aber auch auf Probleme in meinem Netz, dass da was durcheinander kommt.🤔  
10:52  
Juergen DF2AP  
Ja das könnte auch bei mir an meiner WLAN-Konfiguration liegen.  
10:58  
Klaus  
Davon abgesehen laufen die ESP32 Recht gut. Haben auf Anhieb funktioniert, interessant war, das beide die ersten 10min sehr heiß wurden und wenn die SV etwas schwach ist, beide im Minuten Takt booten.  
12:41  
#### wolfgang z  
Bitte teste den zuvor die richtige Funktion des 3,3V-LDOs, wie ich beschrieben habe! Ich vermute, dass der defekt ist.  
12:43  
Wir ha#### ben, auf Grund ähnlicher Probleme, damals einen Befehl in die FW eingebaut, mit dem man die WiFi TX-Power einstellen kann.  
Es schien nämlich so, dass im Nahbereich des WLAN-Routers bei zu hoher TX-Power des ESP32-Moduls, es wahrscheinlich zu Übersteuerungen im WLAN-Router kam und die Verbindung nicht bis sehr schlecht möglich war.  
12:45  
PS: Während des Bootens kann man im Terminal sehen, wie stark der WLAN-Router am Modul empfangen wird. Das kann als Anhaltspunkt dienen, die TX-Power passend einstellen zu können.  
12:46  
Franz DG2RBF  
👍  
12:50  
#### wolfgang z  
Beim Booten:  
==============  
CLIENT STARTED  
==============  
[WIFI]...SSID: Drei_H288A_24G_yAFG CHAN: 2 RSSI: -55 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...connecting to CHAN: 2 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...power: 78 RSSI:-54  
[WIFI]...Wait connect .  
...  
[WIFI]...connect OK  
[WIFI]...now listening at IP 192.168.1.107, UDP port 1990  
[WIFI]...Internet UDP-DEST meshcom.oevsv.at  
[WIFI]...Internet NTP-DEST pool.ntp.org  
00:00:06[Web]...mDNS responder started  
TimeClient now (UTC): 11:47:36  
12:53  
siehe hier: https://t.me/c/1987218802/1/23899  
12:57  
#### wolfgang z  
#### wolfgang z 27.05.2025 10:45:00  
Wir haben einen neuen Parameter  
--wifiTXpower [2..20]  
[...] ist die mathematische Schreibweise. Die Einheit ist dBm;  
eingebaut, da zu hohe WiFi-Leistung bei manchen Boards den Verbindungsaufbau verhindert hat. Default ist der auf 8,2 dBm.  
Also du kannst versuchen, mit --wifitxpower 20 die Leistung zu erhöhen.  
Siehe auch hier:  
https://github.com/icssw-org/MeshCom-Firmware/issues/432  
13:07  
#### wolfgang z  
Das deutet stark auf Lötfehler hin, da diese(r) durch Erwärmung erst später auftreten kann.  
13:15  
Juergen DF2AP  
Hallo Wolfgang, der ESP32 ist nicht der vom Kurzschluss. Der war tatsächlich defekt und wurde ersetzt. Trotzdem tauchten die Probleme nach einer Weile immer mal auf.  
13:17  
#### wolfgang z  
Ok, das ist eigenartig. Das würde eine genauere Untersuchung erfordern.  
Aber ich vermute, dass die ESP32-Boards auch gewisse Toleranzen oder auch selber Lötfehler/Haarrisse aufweisen können.  
Hier ist es wirklich einfacher, das Modul zu ersetzen.  
13:24  
auch hier dokumentiert:  
https://github.com/karamo/MeshAll42_MIT-AI2/blob/main/MeshCOM_Interna/MeshCom-Commands_info.md#-wifitxpower  
23 November 2025  
13:12  
Juergen DF2AP  
Update zum Test:  
Bisher konnte ich keine unerwünschten TX-Aussendungen mehr feststellen. Ich habe gestern das WX-Modul angesteckt, auch damit scheint es soweit zu laufen.  
Heute habe ich das GPS-Modul angesteckt. Allerdings habe ich vermutlich ein Konfigurationsproblem mit dem GPS-Modul. Die rote LED auf dem Neo6M blinkt. Das Modul scheint also GPS-fix zu haben. Ich hab GPS in der App auch aktiviert. In der Info-Abfrage sowohl in der App, als auch im Webinterface wir jedoch kein GPS-fix angezeigt.  
Muss das GPS-Modul anders konfiguriert werden und wenn ja, wie macht man das?  
13:57  
#### wolfgang z  
Das GPS-Modul wird automatisch durch die FW richtig eingestellt. Habe ich damals implementiert und getestet. Aber es muss natürlich ein kompatibles Modul sein, welches auch mit der FW kommunizieren kann.  
➡️ 1) Wie ich sehe, hast du ein Neo-6M Modul = kompatibel  
2)❗️stelle bitte --gpsdebug on  
3) und poste das Ergebnis, welches der Befehl --gps liefert  
4) und was beim Booten gemeldet wird.  
14:35  
Ritter Freiherribert von Matschkenffark =^..^=  
Meiner sagt:  
-----------check GPS-----------  
$GPRMC,,V,,,,,,,,,,N*53  
$GPVTG,,,,,,,,,N*30  
$GPGGA,,,,,,0,00,99.99,,,,,,*48  
$GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
$GPGLL,,,,,,V,N*64  
newData:1 SAT:0 Fix:0 UPD:0 VAL:0 HDOP:9999 TIMEVAL:1  
14:36  
Was bedeutet das? Dass ich kein Fix habe mitten im Zimmer ist klar - Frage, ob das Mosul "Gesund" ist?  
14:37  
Kurt Baumann OE1KBC  
Es hat gsnz einfach kein Signal von gps  
14:37  
Franz DG2RBF  
Geh mal ins Freie mit deinem Meschcom Teil  
👍  
14:38  
Ritter Freiherribert von Matschkenffark =^..^=  
nach Reboot sagt er  
GPS: trying 38400 baud <1>  
GPS: connected at 38400 baud  
GPS serial connected, saved config  
14:39  
Kann leider nicht, bin nach OP leider noch im Bett...  
14:39  
Franz DG2RBF  
Das ist schlecht  
14:39  
Ritter Freiherribert von Matschkenffark =^..^=  
Und wie :)  
14:40  
Aber ansonsten scheint es gesund zu sein, oder?  
14:40  
Franz DG2RBF  
Ja  
14:40  
Ritter Freiherribert von Matschkenffark =^..^=  
Ich habe das originale GPS Modul vom Lilygo T-Beam ausgetauscht gegen einer aus Amazon  
14:41  
Franz DG2RBF  
Das passt schon  
14:42  
Die original GPS Module der T-Beams sind Müll  
14:43  
Ritter Freiherribert von Matschkenffark =^..^=  
Dachte ich, deshalb habe ich dieses montiert:  
https://www.amazon.de/dp/B07MHGPT8L  
14:44  
Franz DG2RBF  
Diese GPS Teile montiere ich auch bei den T-Beams  
👍  
14:44  
Ritter Freiherribert von Matschkenffark =^..^=  
Aber vorerst kann ich nicht unter freen Himmel mit dem Ding  
14:44  
Attila Kocis (DL1NUX)  
Kann ich nicht bestätigen. habe 3 Stück und alle laufen tadellos und bekommen schnell einen Fix.  
14:45  
Franz DG2RBF  
Die Streuungen bei diesen kleinen GPS Modulen ist sehr gross, hab schon defekte Teile bekommen  
14:46  
Helmi Beh  
Das ist aber kein GPS-Modul, sondern nur die GPS-Antenne!  
14:46  
Franz DG2RBF  
Schon klaar  
14:47  
Ritter Freiherribert von Matschkenffark =^..^=  
SRI für unklare Formulierung... natürlich Antenne  
18:04  
#### wolfgang z  
Nein, du hast nicht das GPS-Modul ausgetauscht, du hast lediglich die aktive GPS-Antenne ausgetauscht.  
18:05  
Ritter Freiherribert von Matschkenffark =^..^=  
Ja, das haben wir ja besprochen...  
18:07  
#### wolfgang z  
ok, aber  
1. habe ich die Antwort von Helmi noch nicht gesehen gehabt, und  
2. sollten sich alle um einer möglichst exakte Ausdrucksweise bemühen, da es sonst zu groben Missverständnissen kommen kann.  
18:08  
Ritter Freiherribert von Matschkenffark =^..^=  
Hast Recht, deshalb habe ich mich ja wegen der inkorrekten Formulierung entschuldigt gehabt.  
👍  
19:50  
Juergen DF2AP  
esp-web-tools-logs.txt  
5.8 KB  
Ich hab mal beim booten per Konsole mitgeschrieben. Es scheint so, als ob zum GPS-Modul keine Verbindung zu Stande kommt.  
19:51  
Diese Ausgabe läuft quasi permanent, so bald ich das GPS im Setup anschalte:  
[19:43:37]GPS: trying 38400 baud <1>  
[19:43:40]GPS: trying 9600 baud <1>  
[19:43:40]GPS: trying 38400 baud <1>  
[19:43:44]GPS: trying 57600 baud <1>  
[19:43:47]GPS: trying 115200 baud <1>  
[19:43:51]GPS: trying 38400 baud <2>  
[19:43:54]GPS: trying 9600 baud <2>  
[19:43:54]GPS: trying 38400 baud <2>  
[19:43:58]GPS: trying 57600 baud <2>  
[19:44:01]GPS: trying 115200 baud <2>  
[19:44:05]GPS: trying 38400 baud <3>  
[19:44:08]GPS: trying 9600 baud <3>  
[19:44:08]GPS: trying 38400 baud <3>  
[19:44:12]GPS: trying 57600 baud <3>  
[19:44:15]GPS: trying 115200 baud <3>  
[19:44:19]GPS: trying 38400 baud <4>  
[19:44:22]GPS: trying 9600 baud <4>  
[19:44:22]GPS: trying 38400 baud <4>  
[19:44:26]GPS: trying 57600 baud <4>  
[19:44:29]GPS: trying 115200 baud <4>  
[19:44:33]GPS: trying 38400 baud <5>  
[19:44:36]GPS: trying 9600 baud <5>  
[19:44:36]GPS: trying 38400 baud <5>  
[19:44:40]GPS: trying 57600 baud <5>  
[19:44:43]GPS: trying 115200 baud <5>  
[19:44:47]GPS: trying 38400 baud <6>  
[19:44:50]GPS: trying 9600 baud <6>  
[19:44:50]GPS: trying 38400 baud <6>  
[19:44:54]GPS: trying 57600 baud <6>  
[19:44:57]GPS: trying 115200 baud <6>  
[19:45:01]GPS: trying 38400 baud <7>  
[19:45:04]GPS: trying 9600 baud <7>  
[19:45:04]GPS: trying 38400 baud <7>  
[19:45:08]GPS: trying 57600 baud <7>  
[19:45:11]GPS: trying 115200 baud <7>  
[19:45:15]GPS: trying 38400 baud <8>  
[19:45:18]GPS: trying 9600 baud <8>  
[19:45:18]GPS: trying 38400 baud <8>  
[19:45:22]GPS: trying 57600 baud <8>  
19:58  
Helmut OE5HWN  
Welches GPS hast da angeschlossen, es wird auf jeden Fall nicht erkannt  
19:59  
Dieses Problem ist bereits mehrfach aufgetreten bei GPS Modulen von Ali, da es sich dabei um Fälschungen handelt.  
20:15  
Juergen DF2AP  
Hallo Helmut,  
Danke für die schnelle Antwort. Laut Aufdruck soll es ein Neo-6M Modul sein.  
20:15  
Kann den OM nach der Bezugsquelle fragen. Wie gesagt die rote Leuchtdiode blinkt, aber irgendwie klappt die Verbindung nicht.  
21:38  
#### wolfgang z  
es könnte ganz einfach sein, dass du RX <-> TX vertauscht hast. Nach welcher Anleitung hast du das GPS-Modul mit dem PCB (Board) verbunden?  
21:43  
Juergen DF2AP  
Danke Wolfgang für die Rückmeldung. Der Node inkl. GPS-Modul sind ja nicht mir. Ich prüfe das Morgen mal. Heute ist bei mir schon Feierabend im Shack.  
24 November 2025  
08:39  
Juergen DF2AP  
Hab nachgeschaut, RX/TX sind korrekt verdrahtet. Ich werde mal mit einen USB/TTL Wandler direkt die Daten vom GPS-Modul anschauen, ob da was läuft.  
09:30  
Kurt Baumann OE1KBC  
Dreh trotzdem RX/TX einmal um  
10:09  
Juergen DF2AP  
Ok Kurt. Mach ich heute Nachmittag mal.  
10:09  
Bin erstmal unterwegs.  
11:01  
#### wolfgang z  
Das ist keine valide Aussage!  
Meine Frage war: "Nach welcher Anleitung/Überlegung ...  
meinst du, dass es korrekt sei?"  
12:36  
#### wolfgang z  
schau mal, hier habe ich die korrekte Verdrahtung beschrieben:  
https://github.com/DK9BT/esp32-e22-lora-board/blob/main/ESP32-E22_V2.1.2/PCB-Assembly/README.md#41-gps  
12:37  
Für das ESP32-E22 PCB gilt speziell folgende Zuordnung/Verdrahtung:  
In der configuration.h  
#define GPS_RX_PIN 16 <= TX am GPS-Modul  
#define GPS_TX_PIN 17 => RX am GPS-Modul  
12:59  
#### wolfgang z  
und mit --gpsdebug on solltest du dann beispielsweise folgende Ausgabe am Terminal sehen. Bei mir im Zimmer natürlich keine SATs und auch kein Fix möglich.  
-----------check GPS-----------  
$GPRMC,,V,,,,,,,,,,N*53  
$GPVTG,,,,,,,,,N*30  
$GPGGA,,,,,,0,00,99.99,,,,,,*48  
$GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
$GPGLL,,,,,,V,N*64  
newData:1 SAT:0 Fix:0 UPD:0 VAL:0 HDOP:9999 TIMEVAL:1  
19:55  
Christoph OE3BCB  
Hat jemand die E22 bezüglich Empfang schonmal mit Heltec oder so verglichen ?? Bei mir hat das E22 um -20dbm weniger als die Heltec V3 oder Wireless Tracker mit Selber Antenne und genau selbe Position. Kann es sein dass die die SF und anderen Werte eventuell nicht passen ??  
20:05  
#### wolfgang z  
Habe diesbezüglich heute mein E22-PCB mit gleicher Antenne aktiviert. Ja, der Empfang ist schlechter als der TLORA+PA mit +10dB RX.  
Aber auf Grund der herrschenden Jahreszeit habe ich nicht die Möglichkeit, eine "Referenz"Node für solche Tests in einiger Entfernung aufzustellen, die ich auch unter meiner Kontrolle habe.  
Die einzige nächste Node, die ich erreiche ist OE3MHU-16 bzw. OE1KBC-12. Aber von denen bekomme ich kein RX, im Gegensatz zuvor mit der TLORA+PA  
20:07  
Christoph OE3BCB  
👍  
20:09  
Die Frage, wird es nur schwächer angezeigt als es vielleicht wirklich ist, quasi Kalibration falsch oder so, oder ist es wirklich um so viel schwächer, das geht nur auf einem Messplatz das genau herauszufinden  
20:11  
#### wolfgang z  
oder auf möglichst Freifeld >10m Abstand ev.  
20:13  
Die Frage ist dann halt nur, wie ich die entfernte (Referenz)Node dazu bringen kann, Aussendungen zu machen.  
Ohne externe HW scheint mir das nicht zu gehen.  
Oder ich baue mir eine Ping-Pong-Funktion in die FW ein.  
20:14  
dh. ich schicke ein PING auf {9} und die Node schickt mir ein PONG zurück  
22:20  
Helmi Beh  
Also ich betreibe den ESP32-E22 nicht mit Meshcom, sondern benutze die Platine für Lora-Satelliten-Empfang (TinyGS). Man merkt den LNA im Gegensatz zu den TTGO und Heltecs, die ich auch noch habe, schon sehr. Die Sendeleistung kann ich natürlich nicht beurteilen, da das ein reines Empfangsprojekt ist (in Ermangelung passender Satelliten, die auch empfangen und wieder aussenden können)  
25 November 2025  
10:43  
Juergen DF2AP  
Hallo Wolfgang. Bin nicht eher zum antworten gekommen.  
Ich habe das E22 auf der fertigen Platine, also keine Lochraster Verdrahtung.  
Dort gibt es einen 4-poligen Anschluss für das GPS-Modul.  
GND  
V+  
RX  
TX  
Dort hab ich nochmal geprüft, ob die Spannung korrekt verdrahtet ist und die 3,3V am GPS-Modul ankommen. Dann bleiben noch RX/TX.  
Die hatte ich verdrahtet:  
PCB: TX auf GPS RX  
PCB: RX auf GPS TX  
So sollte es korrekt sein. Ich habe trotzdem noch mal RX/TX getauscht. Wie erwartet hat das jedoch auch nicht funktioniert.  
10:49  
Stefan  
Hast du ein Bild von dem GPS-Modul?  
10:55  
Juergen DF2AP  
Bin gerade unterwegs. Kann ich aber nachliefern.  
10:56  
Ich will das Teil mal mit USB/TTL Wandler starten. Vielleicht ist es gar kein Neo 6M (Fake).  
12:02  
#### wolfgang z  
ja, das sollte passen, wie ich ja zuvor auch und in der Doku auf GitHub geschrieben habe.  
12:03  
Ja, ev., das ist ja auch die Vermutung von Stefan. 😉  
12:04  
Helmut OE5HWN  
Diese Vermutung hatte ich auch schon vor Tagen geäußert  
👍  
12:05  
Stefan  
Das blaue Modul ist ein Fake und funktioniert am E22-Board nicht. Das schwarze ist ok und bei mir auch im Einsatz.  
12:05  
12:07  
Über ein USB-Interface geht das, lässt sich aber nicht passend konfigurieren. Ich hab die Meisten der Fakes in die Tonne befördert, gekauft nur, weil der Preis mit Antenne günstiger war als ne Antenne einzeln. 😄  
12:08  
#### wolfgang z  
Das ist eine gute Idee.  
Da es ja anfangs notwendig war, das GPS-Modul händisch mit einem speziellen Programm passend einzustellen, habe ich recherchiert und alle notwendigen Schritte für die richtige Einstellung der Parameter eruiert, die dann auch in die FW eingebaut wurden. Dadurch war es nur mehr notwendig, ein GPS-Modul zu verwenden, welches die richtige "Sprache" spricht.  
12:09  
Stefan  
Das ist ja das Blöde, die Fakes lassen sich nicht so einstellen... 😉 "Markenmodule" funktionieren dagegen.  
12:11  
#### wolfgang z  
Das hier funktioniert(e), findet aber im Haus keinen FIX.  
Leider habe ich mir blöderweise den kleinen Puffer-Akku abgerissen.  
Auf der Rückseite: "NEO-6M GPS"  
vorne: "HW-595 0228"  
12:49  
#### wolfgang z  
Photo  
564×75  
so, jetzt empfange ich OE3MHU-16 auch direkt via HF mit meinem E22+≈35cmAntenne, im Zimmer.  
OE3MHU-16 hatte gestern einfach einen Crash gehabt, ist jetzt aber wieder als GW aktiv.  
12:53  
da schau, das habe ich jetzt das 1.x gesehen.  
Was bedeutet das, bzw. was kann ich damit erkennen?  
13:03  
⁉️die Verbindung zu aprs.fi scheint wieder problematisch zu sein, da auf der mcmap alles ok, aber auf aprs.fi sehr veraltete Infos tw.  
❤  
🔥  
21:39  
Juergen DF2AP  
Ich habe mal einen USB/TTL-Wandler angeschlossen und versucht den Boottext mitzuschreiben. Das scheint kein ublox-Chip zu sein:  
$GPTXT,01,01,02,HW=ATGM332D,0001211360338*14  
$GPTXT,01,01,02,IC=AT6558-5N-31-0C510800,BM08CKJ-F2-022601*50  
$GPTXT,01,01,02,SW=URANUS5,V5.3.0.0*1D  
Siehe erste Zeile. Sehe ich das richtig?  
21:40  
Ach so, es ging um diese Nachricht.  
28 November 2025  
17:52  
Juergen DF2AP  
Ich bekomme den Node nicht richtig in den Griff. Aktuell macht er ein paar seltsame Aussendungen direkt nach dem Start, dann läuft er erstmal.  
17:53  
Elko und 1k Widerstand haben das Problem offensichtlich nicht komplett behoben.  
17:54  
Zusätzlich hab ich als zweite Problem das GPS-Modul.  
17:55  
Wie hier bereits geschrie#### ben, scheint da offensichtlich kein ublox Chip verbaut zu sein.  
18:25  
Stefan  
Hast du mal ein Foto von dem Modul? Ist das eins, wie oben gezeigt?  

  
ESP32-E22 PCB  
Previous messages  
28 November 2025  
19:28  
#### wolfgang z  
Ahh, das bist du! Hatte nicht wahrgenommen.  
Ok, scheint immer noch die Spannungsversorgung zu sein.  
Bitte mal mit Oszi daran schauen!  
Aber da es Teile aus der Kommandozeile sind, scheint mir doch noch ein Kurzschluss zw. RX <-> TX am ESP32 vorzuliegen.  
19:35  
Juergen DF2AP  
Wurde auf Meshcom zu Telegram gerufen 😅. Hier bin ich.  
19:35  
#### wolfgang z  
Was meine ich damit:  
Wenn RX <=> TX (von der USB) verbunden sind, dann kommt die Ausgabe der Konsole (TX) => RX und dann ist klar, dass "... wrong command..." kommt.  
19:36  
JAAAA, sorry, hatte ich anfangs nicht so wahrgenommen.  
19:36  
Juergen DF2AP  
Das hat prima funktioniert. 👍  
19:37  
#### wolfgang z  
Aber, was mir zwar noch nie vorgekommen ist, dass es ev. auch die Terminal Software verursachen könnte, dass die (Teile) vom RX gleich wieder an TX schickt.  
Welche verwendest du?  
19:41  
❓Du sagtest, dass das nur beim RESTART/BOOT auftritt?  
19:41  
Juergen DF2AP  
Putty für Windows. Der PC war aber gar nicht dran, als die Aussendungen liefen.  
19:42  
#### wolfgang z  
1) Bitte nimm einen Chrome Browser und  
https://terminal.spacehuhn.com/  
19:43  
Franz DG2RBF  
Mein Tip, ich nehme für Mac und Windows Coolterm her, das läuft besser als putty, und braucht keinen Browser.  
👍  
19:43  
Juergen DF2AP  
Also ich hab den ESP32 abgezogen und alleine per Webflasher und vorherigem Erase neu geflasht. Ich wollte nochmal sauber starten.  
19:43  
#### wolfgang z  
Dann schau dir beim Booten die Terminal-Ausgabe an.  
19:44  
Juergen DF2AP  
Den neu geflashten ESP32 hab ich auf das Board gesteckt und dann hat er den Unfug gesendet.  
19:45  
Da bei der Neueinrichtung mehrmals Reboot erfolgt, kammdas ein paar mal hintereinander.  
19:45  
Franz DG2RBF  
Das kommt bei manchen ESP32 vor, beim Erststart die boot Taste am ESP32 drücken.  
19:45  
#### wolfgang z  
Du brauchst das ESP32-Modul nicht vom Board nehmen:  
Micro-USB am ESP32-Modul anstecken und da das Terminal.  
+ zusätzlich an der USB-C zur Verstärkung der Versorgung.  
19:45  
Juergen DF2AP  
Allerdings hatte ich auch einen Fehler meinerseits. Ich war an der Powerbank nicht am 3A Ausgang.  
19:46  
Kann sein, dass der Anode zu wenig Strom bekommen hat.  
19:46  
Anode = Node  
19:46  
#### wolfgang z  
Ja, das kann sein. Daher µUSB am ESP32 & USB-C  
19:47  
Franz DG2RBF  
Nein, das ist ein Bug von manchen ESP32 Device  
19:47  
Das hat mit der Stromstärke nichts zu tun  
19:47  
#### wolfgang z  
Dann ist sehr anzuraten, mal den 3.3V LDO am ESP32-Board lt. meiner Anleitung zu testen.  
19:48  
Franz DG2RBF  
ok..  
19:49  
#### wolfgang z  
Warum ist das so?  
Weil die 3,3V NUR am ESP32-Board vom LDO erzeugt wird.  
Wenn der defekt ist, dann bricht die Spannung bei schon geringen Stromstärken zusammen.  
19:49  
Juergen DF2AP  
Wo finde ich die Anleitung Wolfgang?  
19:50  
#### wolfgang z  
Hier ... moment  
19:51  
https://t.me/c/1987218802/11812/26592  
19:51  
Juergen DF2AP  
Danke, ich lese mich ein und melde mich wieder.  
19:51  
#### wolfgang z  
exakt hier: https://t.me/c/1987218802/11812/21680  
20:13  
#### wolfgang z  
❗️Es wäre noch zu überprüfen, ob die Fehlaussendungen beim BOOTEN auch dann kommen, wenn ein Terminal angesteckt ist?  
20:16  
Franz DG2RBF  
Diese Fehlaussendungen kommen immer zustande, egal ob etwas angesteckt ist, oder nichts drann steckt  
20:24  
#### wolfgang z  
20:26  
Hier am ESP32-Board sind am Ende bei der WLAN-Antenne die 3V3 & GND.  
Löte hier 100nF + 10µF parallel dran.  
Für die Messung der 3,3V bei Belastung kann man dann gleich auf die Beinchen der Kondensatoren anklemmen.  
20:27  
Franz DG2RBF  
Ist dieser 100nf ein Keramik C?  
👍  
20:42  
#### wolfgang z  
Ja, und da kann man auch gleich mit dem Oszi messen.  
20:44  
Franz DG2RBF  
Das ist ein sehr guter Tip  
29 November 2025  
09:50  
Juergen DF2AP  
Guten Morgen Wolfgang. Hängt der 100nF zwischen 5V und GND oder zwischen 3,3V und GND.  
Auf dem Foto sieht es eher so aus, als ob er an 5V hängt.  
Und parallel dazu dann noch ein 10µF?  
09:53  
@Stefan: hier noch ein Foto vom GPS-Modul.  
09:54  
#### wolfgang z  
Guten Morgen,  
1) ja, zw. 3V3 —||— GND  
2) Das am Foto ist das ESP32-S3 Board, das hat die letzten 2 Pins jeweils dupliziert. Darum die andere Ansicht.  
3) Ja, 10µF oder 47µF, aber nicht >100µF, da diese dann auch zu große Induktivität wegen des Wickels haben. Tantal-Elko wäre natürlich viel besser.  
09:55  
Stefan meinte mal, man solle unter das Pickerl schauen ... 😉  
09:55  
Juergen DF2AP  
Okay 👍. Mach ich mal im Laufe des Tages. Muss erstmal den lokalen Adventsmarkt unserer Gemeinde mit vorbereiten.  
09:57  
#### wolfgang z  
Alles normal oder mit "Schutzpanzer" 😉  
09:58  
Juergen DF2AP  
Normal. Wir sind ein Dorf mit gut 1.000 Einwohnern.  
🥰  
09:59  
Ich hatte auf YouTube ein Video zu den GPS-Modulen angeschaut. Laut Boot-Meldung ist das ein chinesischer Chipsatz. Also nicht ublox.  
👍  
10:00  
Hab jetzt einen neuen geordert. Werde berichten.  
10:00  
Außerdem hab ich mal noch ein ordentliches USB C Kabel geordert.  
👏  
10:00  
Wenn alles klappt kommt das heute noch.  
10:23  
#### wolfgang z  
Findest du auch Datenblätter dazu?  
👍  
11:14  
Kurt Baumann OE1KBC  
Ja bitte dann könnten wir einbauen  
11:16  
#### wolfgang z  
Genau, das meinte ich auch. Ev. muss man diese Module mal händisch in ein kompatibles Format bringen.  
Ich hatte mich ja damals nur mit dem ublox Format beschäftigt, um die Parameter passend einzustellen.  
11:46  
Juergen DF2AP  
1911211831_ZHONGKEWEI-ATGM332D_C458416.pdf  
1.7 MB  
11:46  
Sowas hier?  
11:52  
#### wolfgang z  
Ja, schaut ganz gut aus:  
"ATGM332D-5N series of module through the UART as the main output channel output in accordance with the NMEA0183 protocol format"  
11:53  
"Zhongke micro provide the"GNSSToolKit" Lite version of the software package (Windows version, Android version), used to locate output parsing and work mode  
configuration."  
11:55  
Da müsste man weiter suchen:  
Reference  
1. "ZKMicro AGNSS solutions"  
2. "CASIC multi mode satellite navigation receiver protocol specification"  
3. "ATGM module online upgrade protocol "  
4. "AT6558 datasheet （EN）"  
5. "GNSSToolKit tool instructions"  
6. "UBF serial port upgrade tool instructions"  
13:33  
Juergen DF2AP  
at6558.pdf  
2.5 MB  
1 December 2025  
17:59  
#### wolfgang z  
Ich habe gestern 2 Stk. dieser Module mit der Bezeichnung GY-NEO6MV2 bei A..Z bestellt und sollten Mi kommen. Dann kann ich mir das mal ansehen.  
schaut genauso aus wie deines & Stefan seines, nur andere Bezeichnung am PCB.  
"u-center Software: Dies ist die offizielle u-blox Software zur Evaluierung.  
Verbinden Sie das Modul mit Ihrem PC und öffnen Sie u-center.  
Führen Sie den Befehl UBX-MON-HW aus. Ein echtes Modul sollte korrekt antworten. Fälschungen antworten entweder nicht, mit fehlerhaften Daten oder sie melden einen anderen Chip (z. B. NEO-7M oder AT6558)."  
https://github.com/mikalhart/TinyGPSPlus/issues/95  
https://portal.u-blox.com/s/question/0D52p00008HKEEECA5/psa-fake-ublox-modules-and-potential-ways-to-identify-them  

Hier werden Module mit exakt der gleichen "Seriennummer" angege#### ben, wie deines auch hat.  
https://cool-web.de/arduino/fake-gps-neo-6m-module-aus-china-aliexpress.htm  

Jürgen, hier siehst du ein weiteres Detail beim Blick auf die PCB: Bei der Antenne sollten lt. Schaltung ein 22Ω Widerstand in Serie mit einer 27µH Spule sein.  
Auf deinem Bild sieht das nicht danach aus.  

so sollte die Schaltung sein:  
http://wiki.sunfounder.cc/index.php?title=Ublox_NEO-6M_GPS_Module  

Da generell aktive GPS-Antennen verwendet werden, müssen die ja auch versorgt werden, was eben über die Serienschaltung L1+R4 erfolgt, wodurch auch die HF abgeblockt wird.  
Wenn aber in deinem Fall ein SMD-Bauteil mit der Beschriftung von "110" an Stelle der Spule verbaut ist, dann kann das nicht funktionieren.  
Es wäre nun interessant, was du an diesem Bauteil mit dem Ohmmeter messen kannst.  

SMD-Induktivitäten sehen grundsätzlich nicht so aus wie Widerstände und sind auch nicht so beschriftet.  

#### Juergen DF2AP  
Heute sind zwei neue GPS-Module angekommen. Diesmal nicht direkt aus Fernost. Werde die Teile in den nächsten Tagen mal testen und hier berichten.  

#### wolfgang z  
❗️Nach längerer Recherche muss ich folgendes feststellen:  
1) Dass die GPS-Module mit dem AT6558 fake seien; ja, aber nur, wenn man NEO-6M erwartet.  
2) Dass diese GPS-Module für die Tonne seien, dass ist völlig überzogen und falsch.  
➡️ Die GPS-Module mit einem AT6558 sollten grundsätzlich ein kompatibles Protokoll ha#### ben, was den Empfang betrifft.  
💥Dass das automatische Einstellen der passenden Parameter mit der aktuellen MC-FW und TinyGPS zur Auswertung nicht funktioniert, das ist logisch, da die einen proprietären CASIC Befehlssatz haben.  
09:05  
#### Juergen DF2AP  
Das deckt sich mit meinen Erfahrungen. Die Module bei mir sind Fake, da sie als Neo6M-V2 verkauft wurden. Allerdings bekommen sie einen GPS-Fix und ich hatte sie mal an der ublox-Software. Dort wird der fix und die serielle Datenausgabe per 9600 Bd auch angezeigt. In der Software gibt es sehr viele Einstellmöglichkeiten welche Datensätze da über die serielle ausgegeben werden soll.  
Welchen Datensatz erwartet denn unser ESP32 auf dem E22?  
Vielleicht kann man das mit der korrekten Einstellung lösen oder wird vom ESP32 geprüft, ob da tatsächlich ein ublox-Chip dranhängt?  
11:09  
#### wolfgang z  
Es gibt  
1) Infos über die CASIC-Befehle, wie man diese AT6558 einstellen kann.  
2) natürlich kann man die nicht mit dem u-blox-center v25.x einstellen, da eben andere Befehle notwendig sind.  
11:10  
3) es gibt ein spezielles Programm dafür, aber das ist tw. in Chinesisch. Habe es schon runtergeladen und auch mehrere Infos dazu.  
11:12  
Grundsätzlich NMEA, aber es muss auch TinyGPS das auch "verstehen", um es auswerten zu können. Da müsste ich mich näher damit befassen.  
Aber wie gesagt, meine Module kommen erst morgen Mi.  
11:13  
Ja, das werde ich mir ansehen und könnte es ev. lösen; und auch die automatische Umstellung wäre grundsätzlich möglich, da es "nur" über die Serielle Schnittstelle geht.  

Ich habe mal alle relevanten Infos auf mein GitHub hochgeladen.  
Sollte laufend ergänzt werden und falls jemand von euch diesbezüglich auch Infos u/o Daten hat, dann bitte einfach als Issue hochladen.  
https://github.com/karamo/MeshAll42_MIT-AI2/tree/main/Doku/GPS  

3 December 2025  
19:31  
#### wolfgang z  
Photo  
368×79  
❗️Meine GX-GPS6MV2 sind eingetroffen.  
Und das liefern sie @ 9600 Baud.  
Wie zu sehen ist, ...  

damit verglichen, sind es exakt die gleichen Datensätze, die ein "originales" NEO-6M" liefert:  
$GPRMC,,V,,,,,,,,,,N*53  
$GPVTG,,,,,,,,,N*30  
$GPGGA,,,,,,0,00,99.99,,,,,,*48  
$GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
$GPGLL,,,,,,V,N*64  
 
Das sind offenbar tatsächlich originale U-blox NEO-6M  
 
1) nur mit einem Terminal vorerst.  
jetzt werde ich das u-center anwerfen.  

Das habe ich jetzt herausbekommen in der Message View  

#### Stefan  
Kannst du die Bootmessage im Textfenster mitschreiben?  

#### wolfgang z  
$GPTXT,01,01,02,Resetting GPS*68  
??:??:?? $GPTXT,01,01,02,ANTSTATUS=INIT*25  
20:39  
cold start:  
$GPTXT,01,01,02,ANTSTATUS=INIT*25  
$GPTXT,01,01,02,ANTSTATUS=OK*3B  
20:42  
Ach, du meinst an eine Node anstecken?  
20:44  
schön langsam füllen sich die Daten und es sind schon ein paar wenige SATs in View:  
??:??:??  $GPRMC,,V,,,,,,,,,,N*53  
??:??:??  $GPVTG,,,,,,,,,N*30  
??:??:??  $GPGGA,,,,,,0,00,99.99,,,,,,*48  
??:??:??  $GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
??:??:??  $GPGSV,2,1,06,01,,,18,04,,,23,05,,,18,18,,,17*72  
??:??:??  $GPGSV,2,2,06,22,,,15,24,,,19*75  
??:??:??  $GPGLL,,,,,,V,N*64  
20:45  
siehe: $GPGSV ...  
20:48  
Photo  
391×57  
und es werden mehr  
20:49  
Stefan  
Bin leider gerade nicht zuhause, gerade OV-Abend. 😳 Geht aber über u-Center oder ein Terminal-Programm.  
20:51  
#### wolfgang z  
Ich lasse das u-center über einen FTDI-Adapter an dem GPS-Modul über Nacht laufen. Position direkt innen vor der Fensterscheibe auf der O-Seite meines Hauses.  
20:52  
#### Stefan  
U-Center hat immer problemlos funktioniert, am Node dann ging's nicht...  
21:21  
#### wolfgang z  
so schaut es mit den SATs derzeit aus. Aber sehr wechselhaft, daher noch keine Zeit und kein Fix  
G18 & G23 stehen stabil in der Höhe aber noch zu wenig.  

#### Juergen DF2AP  
Das war der Boottext gleich nachdem einschalten vom Neo6M mit dem „Fake“ Chipsatz.  
22:04  
#### wolfgang z  
Ja, das liefert ein AT6558, aber ein original ublox NEO-6M eben nicht.  
Mein Problem ist momentan, dass ich kein brauchbares Gehäuse für mein ESP32-E22-PCB habe.  
Werde aber morgen das PCB + Powerbank + GPS in eine Schuhschachtel packen und vors Haus ins Freie stellen.  
Jetzt über Nacht soll mal der kleine Akku aufgeladen werden und sich der Almanach etwas aufbauen.  
22:05  
Du kannst das Programm GnssToolKit3, welches ich auf mein GitHub geladen habe, dazu verwenden, deinen AT6558 zu konfigurieren.  
Lässt sich von chinesisch auf englisch umstellen. Muss dann aber neu gestartet werden.  
22:06  
Photo  
930×88  
22:07  
22:12  
So, Zeit habe ich bereits ..  
22:51  
#### wolfgang z  
die BLAUE LED hat soeben zu blinken begonnen und ich habe Koordinaten.  
22:52  
habe dafür extra nochmals den PC eingeschaltet.  
Aber heute früher GN8.  
23:55  
Thomas - DO1TFS  
kurze Nachfrage.... wenn ich das Board über externe Stromvers. an den Terminalpins anschließe, kann ich dann trotzdem an die USB Schnittstelle mit dem PC gehen oder schrotte ich den PC-USB?  
4 December 2025  
04:48  
Franz DG2RBF  
Sowas ist heikel, würde ich nicht machen.  
04:50  
Nur über einen USB Hub würde ich zur Sicherheit sowas machen.  
10:22  
#### wolfgang z  
unklar, was du damit meinst. Bitte genauere detailliertere Angaben, was du wie machen willst!  
10:24  
Ach so, du meinst beim ESP32-E22, du verwendest die Schraubklemmen.  
JA, geht absolut problemlos, wenn du alle Schottky-Dioden richtig verbaut hast.  

#### wolfgang z  
so, nun an die Node ESP32-E22 angesteckt und das kommt, wie es sein soll:  
--gps on  
START CHECK:  
ONE:--gps on  
GPS: trying 38400 baud <1>  
GPS: trying 9600 baud <1>  
GPS: connected at 9600 baud  
GPS serial connected, saved config  
11:51  
dann, natürlich noch keinen FIX:  
-----------check GPS-----------  
$GPRMC,104829.00,V,,,,,,,041225,,,N*7B  
$GPVTG,,,,,,,,,N*30  
$GPGGA,104829.00,,,,,0,00,99.99,,,,,,*60  
$GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
$GPGSV,4,1,13,02,01,027,,05,07,205,,10,06,336,,12,07,220,*78  
$GPGSV,4,2,13,13,65,151,,14,46,059,,15,67,248,,17,34,110,*78  
$GPGSV,4,3,13,19,25,133,,22,62,068,,23,26,301,,24,37,283,*74  
$GPGSV,4,4,13,30,15,090,*45  
$GPGLL,,,,,104829.00,V,N*4C  
newData:1 SAT:0 Fix:0 UPD:0 VAL:0 HDOP:9999 TIMEVAL:1  
GPS-UTC-Time <local:1.0 2025-12-04 10:48:29  

#### wolfgang z  
Mit LoRa E22 TX = 10 dBm kein Problem und auch kein Fehler.  
Mit LoRa E22 TX = 22 dBm => CRASH  
12:45  
#### Franz DG2RBF  
Da ist eine Einstreung vorhanden  
👍  
12:45  
Oder schlechte Schirmung  
12:46  
#### wolfgang z  
Ist bisher noch nie aufgetreten. Muss mal überprüfen, was anders ist als zuvor.  
12:46  
Franz DG2RBF  
Metallgehäuse oder Kunststoffgehäuse ?  
12:47  
#### wolfgang z  
Sticker  
😂  
12:47  
schick gleich Foto  
12:48  
12:48  
Franz DG2RBF  
Was gibts da zum Lachen? Das war eine ernst gemeinte Frage  
12:50  
Tja, bei solchen Aufbauten wundert mich nix  
12:50  
#### wolfgang z  
Deswegen, das ist mein Gehäuse  
😭  
12:51  
Franz DG2RBF  
Das ist für mich Müll  
12:51  
#### wolfgang z  
Nee, das ist gut. Schmeckt mir.  
12:52  
Franz DG2RBF  
Ich meinte das Gehäuse, sowas gehört ins Recycling  
12:52  
#### wolfgang z  
Und außerdem passt die PCB perfekt hinein und ist gut nach unten isoliert.  
UND: ich will ja auch mal "eure" Fehler erkennen.  
Offenbar konnte ich mit diesem Aufbau so einen Fehler provozieren.  
12:54  
Franz DG2RBF  
hier gibts diesen „Käse“ nicht..  
13:14  
#### wolfgang z  
So, nun Aufbau geändert, dh. das GPS-Modul auf die andere Seite geführt, also nicht am E22 vorbei mit den Leitungen.  
Ergebnis: kein Crash mehr, auch nicht bei RF=22dBm & GPS ON  
13:14  
Sticker  
👍  
13:15  
ihr konnte hier live miterle#### ben, wie man durch ungünstigen Aufbau massive Probleme bekommen kann.  
13:16  
ABER: Ein CRASH sollte hierbei trotzdem nicht erfolgen, oder?  
14:19  
Franz DG2RBF  
Es vermischt sich halt HF Technik und Digital Technik  
14:19  
Das kann gravierende Probleme erzeugen  
15:21  
#### wolfgang z  
ja, und so eben den Fehler bez. des Buttons gefunden!  
siehe in Firmware Issues  
17:27  
Rainer OE1KFR  
Wenn du die Antenne direkt am Modul hast und mit voller Leistung sendest, kann das natürlich durch HF Einkopplung zu solchen Verhalten führen. Hatte bei solchem Setup auch schon ESP Reboots usw.  

18:17  
Thomas - DO1TFS  
super... ja alle Dioden sind verbaut. Danke  
5 December 2025  
05:26  
Christoph OE3BCB  
Hast du eine andere Hardware auch ? zb. Heltec oder so, mich würde interessieren ob es beim RX Probleme gibt ? Meine selbstgebaute E22 Platine ist um mindestens 10dbm schlechter als andere fertig gekaufte Hardware  
07:53  
Rainer OE1KFR  
Pigtail direkt am E22 Chip oder SMA Buchse? Ich hab Ersteres.  
11:26  
#### wolfgang z  
Ja, habe ich schon: 2x T-LORA 433  
Aber es war mir bislang noch nicht möglich, Vergleiche der einzelnen Module zu machen.  
11:28  
schon RX Booster eingeschaltet?  
12:54  
Juergen DF2AP  
Ich hab inzwischen die beiden beim großen A bestellten Neo6MV2 Module erhalten. Offensichtlich wird man jetzt kreativer, wenn gar kein ublox Chip verbaut wurde.  
12:55  
Einfach mit schwarzen Edding durchgestrichen. Ich schick sie gleich wieder zurück. Schade ☹️  
13:01  
Stefan  
Funktionieren tun die ja, nur eben nicht als ublox. 😉  
13:05  
Juergen DF2AP  
Was muss ich denn einstellen, dass sie am ESP32E22 laufen? Bisher hab ich das nicht hinbekommen?  
13:07  
Stefan  
Das klappt bei mir auch (noch) nicht. Ich werde mich mal mit der Software zum Einstellen beschäftigen, hab aber momentan keine Zeit dafür. Deswegen hab ich beim Ali andere bestellt (Bild weiter oben), die auf Anhieb funktionieren.  
13:12  
Juergen DF2AP  
Danke, dann suche ich die mal.  
14:04  
#### wolfgang z  
Mit der Software auf Github kannst du sie konfigurieren.  
Aber, wie gesagt, habe ich keine solche und kann es daher auch nicht selber testen.  
14:05  
siehe hier: https://t.me/c/1987218802/11812/27099  
14:10  
das ist der Schlüssel für die Erkennung in src\esp32\esp32_gps.cpp  
aber ich habe k.A. wie man tinyGPSPlus ggf. umstellen kann und was erwartet wird.  
                if (tinyGPSPlus.encode(c))  
                    newData = true;  
14:13  
1) du musst auf BaudRate 38400 stellen. Das ist das Wichtigste.  
2) dann sollten alle Pakete reinkommen und an tinyGPSPlus zeichenweise geleitet werden.  
3) das "verwurschtet" dann alle ankommenden Zeichen und erkennt einen FIX  
14:15  
4) es sollte dir gelingen, das Modul so umzustellen, dass es die "gleichen" Zeilen liefert, wie die ublox. Das sollte gehen.  
14:17  
• Stell zuerst auf English um.  
> Programm schließen und neu starten  
> Dann öffnest du das View > NMEA Fenster  
Hier solltest du sehen, was reinkommt.  
14:19  
Ja, natürlich zuerst das richtige COM-Port auswählen und 9600 Baud wählen  
14:20  
in der Configuration View stellst du die BaudRate um  
14:21  
Photo  
92×76  
Configuration View  
14:22  
rechts unten [Save] nicht vergessen !!!  
14:24  
Im Prinzip sind es CASIC Befehle, die in einer der PDFs auch genau beschrieben sind.  
z.B. AT6558-protocol-en.pdf  
14:56  
Christoph OE3BCB  
Ja bringt leider nichts  
15:01  
Stefan  
Ist der absolute Signallevel schlecht oder das SNR?  
15:02  
Christoph OE3BCB  
Beides eigentlich, gefühlt wie mit Dummyload ggg, tx ist aber ok  
15:04  
Stefan  
SNR ist schlechter beim E22, der LNA verstärkt halt auch die Störungen. Aber die Empfindlichkeit ist hier grundsätzlich ok.  
15:06  
Einer meiner E22 hat mal einen Schlag durch Gewitter bekommen, sah dann so aus, wie bei dir. Da hat es wohl die Eingangsstufe zerbröselt. Starke Signale hört der noch, schwache nicht mehr.  
15:08  
Juergen DF2AP  
Hallo Wolfgang, welche Baudrate muss ich auf 38400 stellen?  
15:09  
Franz DG2RBF  
38400 ist die einzustellende Baudrate..  
15:09  
Stefan  
Die Baudrate der SSt GPS-Modul zum Node  
15:09  
Juergen DF2AP  
Das Programm hab ich von Github geholt und das "Fake" Modul angeschlossen. Standardmässig steht es auf 9600 Baud. Hab es jetzt auf 38400 Bd gestellt und Save gedrückt.  
15:10  
Franz DG2RBF  
Das macht der Node automatisch  
15:10  
#### wolfgang z  
Da das Modul grundsätzlich, ursprünglich auf 9600 eingestellt ist. Kanns du dich mit dem Programm zuerst nur mit 9600 Baud verbinden.  
Erst dann kannst du die Baudrate vie oben beschrieben vom Modul umstellen.  
15:10  
Juergen DF2AP  
es laufen auch Daten ein im Terminal  
15:11  
#### wolfgang z  
Ja, gut einmal. Aber das sind keine reinen MNEA Sätze  
15:11  
Juergen DF2AP  
Antenne ist aktuell indoor...  
15:12  
Franz DG2RBF  
Das gibt Probleme  
15:14  
#### wolfgang z  
könnte sein, dass man hier was um-/einstellen muss.  
15:14  
Franz DG2RBF  
Da sieht die GPS Antenne zu wenige Satelitten..  
15:15  
Juergen DF2AP  
ich versuche mal einen Fix zu bekommen. Kann etwas dauern.  
15:16  
Franz DG2RBF  
Wie weit bist du mit der GPS Antenne vom Fenster oder Balkontüre entfernt ?  
15:17  
#### wolfgang z  
so was sollt rauskommen:  
??:??:??  $GPRMC,,V,,,,,,,,,,N*53  
??:??:??  $GPVTG,,,,,,,,,N*30  
??:??:??  $GPGGA,,,,,,0,00,99.99,,,,,,*48  
??:??:??  $GPGSA,A,1,,,,,,,,,,,,,99.99,99.99,99.99*30  
??:??:??  $GPGSV,2,1,06,01,,,18,04,,,23,05,,,18,18,,,17*72  
??:??:??  $GPGSV,2,2,06,22,,,15,24,,,19*75  
??:??:??  $GPGLL,,,,,,V,N*64  
15:19  
es schaut so aus, als dass man hier das Output interval für jede einzelne ID einstellen kann.  
15:20  
was ist da eingestellt?  
15:20  
Franz DG2RBF  
Könnte mir jemand den Link zu dieser Software nochmal posten?  
15:20  
#### wolfgang z  
mein GitHub 😉 hier in diesem Thema  
15:20  
https://t.me/c/1987218802/11812/27052  
15:21  
Franz DG2RBF  
Diese Info ist aber spärlich :-)  
15:21  
na also geht doch :-)  
15:22  
#### wolfgang z  
... so was von ungeduldig ... 😇  
15:22  
Franz DG2RBF  
nix für unguad..  
15:24  
tut mir leid dieser Link zu Git endet nur bei PDF Files, nicht zum ausführbaren Program  
15:25  
bin auf Github nicht so fitt  
15:26  
benötige da etwas Hilfe  
15:31  
Stefan  
Du hast Post... 😉  
15:32  
#### wolfgang z  
GnssToolKit3.zip  
❤  
15:33  
https://github.com/karamo/MeshAll42_MIT-AI2/blob/main/Doku/GPS/AT6558/GnssToolKit3.zip  
15:34  
Franz DG2RBF  
Leider ist diese Software in CN nicht in English, wo stellt man da die Sprache um ?  
15:38  
#### wolfgang z  
bitte lies hier im Thema! Ich habe alles bbeschrieben  
15:38  
hier beginnend: https://t.me/c/1987218802/11812/27099  
15:44  
Juergen DF2AP  
So fix ist da. So sieht die Ausgabe jetzt aus:  
15:46  
Photo  
1280×138  
Welche Datensätze braucht es denn?  
15:47  
Es scheinen aber Positionsdaten zu kommen.  
$GNRMC,144702.000,A,5058.72601,N,01047.28418,E,0.00,242.22,051225,,,A*7E  
16:11  
#### wolfgang z  
dann hänge das Modul mal an die Node an.  
16:20  
Rainer OE1KFR  
Das Format muss NMEA sein. Weiß aber nicht mehr genau welches. Glaub im uBlox kann man unterschiedliche auswählen.  
16:28  
16:52  
Juergen DF2AP  
gleiches Ergebnis. Der Node probiert alle Baudraten durch. Sie finden aber nicht zueinander. Vielleicht falsches Format auf dem "Fake" Teil eingestellt.  
17:10  
#### wolfgang z  
So, da bin ich wieder.  
Das was Rainer im Bild zeigt, das sind die Einstellungen, die ich mache, um das u-blox passend einzustellen.  
Ja, da kann es sich spießen.  
Ich schau mal, auf welchen Satz ich schaue beim Test der Baudrate ...  
17:14  
Juergen DF2AP  
diese Datensätze liefert das Modul unter anderem jetzt:  
[17:08:33] ( 72B) $GNRMC,160833.000,A,5058.77603,N,01047.24774,E,0.96,0.00,051225,,,A*7C  
[17:08:34] ( 74B) $GNGGA,160834.000,5058.77687,N,01047.24494,E,1,06,6.4,190.9,M,0.0,M,,*73  
17:16  
#### wolfgang z  
Diese habe ich zuletzt gekauft, und obwohl nicht im Bild ersichtlich, waren es originale u-blox  
https://www.amazon.de/dp/B0DX1V4WS1  
17:17  
Juergen DF2AP  
Bleibt dabei: GPS-Modul und ESP32 reden nicht miteinander 😅  
17:18  
#### wolfgang z  
ja, und wenn die sich nicht finden, dann können zwar die Datensätze passend sein, aber trotzdem kein Erfolg.  
17:19  
Juergen DF2AP  
Okay, aber dann brauche ich da erstmal nicht weiter machen.  
17:20  
Vielleicht teste ich nochmal die beiden neuen Amazon Module.  
17:20  
#### wolfgang z  
genau darauf schaut es auch:  
#define _RMCterm "RMC"  
#define _GGAterm "GGA"  
17:23  
Juergen DF2AP  
Kurze Frage noch. Auf dem Foto vom großen A steht bei den von Dir bestellten Modulen auch kein ublox drauf? Hast Du welche mit ublox-Aufkleber geliefert bekommen oder so, wie die auf dem Foto?  
17:24  
#### wolfgang z  
Genau, siehe meine Beiträge OOPS ...  
17:24  
https://t.me/c/1987218802/11812/27074  
17:25  
wenn dem nicht so gewesen wäre, hätte ich die Option der einfachen Rücksendung wahrgenommen.  
17:27  
"TinyGPSPlus is a compact, resilient library that parses the most common NMEA 'sentences' used: GGA and RMC. "  
17:36  
das ist einfach nur ein öffnen der SoftwareSerial, aber im ´Zusammenspiel mit der  
#include <SparkFun_u-blox_GNSS_Arduino_Library.h>  
und da hakt es eben.  
13 December 2025  
13:48  
Juergen DF2AP  
Ich möchte noch eine Rückmeldung zum störrischen Node mit den ungewollten Aussendungen und dem GPS-Problem geben.  
Aktuell scheint er (vorerst) keine ungewollten Aussendungen zu machen. Was wurde alles gemacht:  
- C6 hatte nur 220µF statt 470µF -> nochmal 220µF parallel  
- den 1K Widerstandwie von Wolfgang beschrieben auf der Platine nachgerüstet  
- am ESP32 zwischen 3V3 und GND noch 100nF und 10µF ergänzt  
Weiterhin schien es mir, dass der WX-Sensor beim Start ein paar ungewollte Zeichenaussendungen provoziert hat. Ich habe einen anderen BME280 dran gesteckt und das Problem ist weg.  

14 December 2025  
14:07  
#### wolfgang z  
Leider noch nicht. Soeben Schrott gesendet !!!  
DL5WB-99>all : �����n�m ��. `������goa��@���.�n��p�.���ld:����o�� .����o��� �:���:.���������.�m����@ �������`�o������w��� 57600 baud <12>  
14:08  
MeshCom, [14.12.2025 13:58]  
DL5WB-99>all : [E];568;(f`e  
MeshCom, [14.12.2025 14:01]  
DL5WB-99>all : ; AP\;160;(fe  
14:18  
14:19  
Das kann doch nicht sein, dass DL5WB die bei DF2AP funktionierende Node wieder geschrottet hat oder den Fehler wieder produziert!  
14:21  
Es sind ≈300+ E22 PCBs aufgebaut worden und davon laufen ≈99% ohne Probleme.  
14:24  
Juergen DF2AP  
Oh je. Tut mir leid.  
14:27  
Hatte heute bei der Übergabe ein kurzes Gespräch. Er hat den Node mit 2W nur mit einer Aufsteckantenne betrieben. Hab ihn drauf hingewiesen, dass das zu Problemen beim ESP32 führen kann. Er soll lieber eine externe Antenne in gebührenden Abstand nutzen oder die TX-Leistung erheblich reduzieren.  
14:30  
Stefan  
Vor Allem eine stabile StrV, die auch 3A schafft ohne Spannungseinbruch!  
👍  
14:31  
Juergen DF2AP  
Das könnte aber erklären, warum er bei mir tagelang ohne Probleme lief. Ich hatte ihn immer an einer Außenantenne in Betrieb. Fehlerhafte Aussendungen hatte er bei mir nur beim Starten gemacht.  
14:32  
Vielleicht macht der Node durch die HF ständig Reset gemacht?  
14:32  
Guter Hinweis. Gebe ich nochmal weiter.  
14:33  
Ach ich hab noch eine Idee. Ich hatte mein GPS dran. Das ist jetzt nicht mehr dran und den Knopf hab ich vergessen auszuschalten.  
14:38  
#### wolfgang z  
genau, siehe hier:  
https://t.me/c/1987218802/11777/27164  
https://t.me/c/1987218802/11812/27160  
14:39  
aber bei mir nur REBOOT-CRASH, aber keinen Schrott gesendet.  
14:40  
Da passiert so etwas nicht.  
Mit GPS ON und kein GPS angesteckt, läuft nur die Suche der BaudRate mehrmals durch und dann wird GPS OFF automatisch durchgeführt.  
14:41  
Juergen DF2AP  
Ah ok.  
14:42  
Also er baut jetzt mal externe Antenne ran, steckt mal GPS (das Richtige ublox) an und nimmt den WX-Sensor nochmal runter.  
15 December 2025  
02:13  
#### wolfgang z  
Leider noch immer Fehlaussendungen, gerade eben.  
02:17  
Franz DG2RBF  
Würde den ESP32 mal neu flashen, mit Komplet erase, wenn das nichts hilft, hat die HF-Einstreuung den ESP32 gekillt, eine HF-Einstreuung ist sehr kritisch.  
 
09:41  
Juergen DF2AP  
Hatte ich schon gemacht. Ich hatte auch den ESP32 ausgetauscht. Das Problem war, dass der Fehler bei mir in dieser Form gar nicht reproduzierbar war.  
11:29  
#### wolfgang z  
Ok, gut. Dann gehen wir wieder die Fehlersuche an:  
❗️Die 1. wichtigste Frage ist:  
"Was ist unterschiedlich (Aufbau, Geräte, ...), wie es bei dir war und was gegenüber dem von DL5WB?❓  
Es geht um Fehlereingrenzung ...  
11:34  
Juergen DF2AP  
Sind schon dabei. Viel kann es nicht sein. Stromversorgung, Antenne, andere HF unmittelbar daneben.  
11:40  
#### wolfgang z  
was ich immer noch nicht verstehe ist, dass hier definitiv Teile von der Konsolen-Ausgabe ausgesendet werden. Das ist von der FW her eigentlich überhaupt nicht möglich.  
MeshCom, [15.12.2025 10:53]  
DL5WB-99>all : 00:00;[0;[HEAP];1506pporteorted  
DL5WB-99>all : ;[  
DL5WB-99>all : 5Ln�:...onwr�ng coin ::  
DL5WB-99>all : 5Ln�:..437722", frmwar":".35,"f_sub:"h} En:4  
DL5WB-99>all : 5Ln�:.47722", frmwar:5,"_su:"h l:4  
11:42  
Eine wichtige Änderung in der FW war, die Message mit "::" einleiten zu müssen. Von daher sollte nichts mehr von dieser Seite ausgesendet werden, das KEIN "::" in der Konsolenausgabe auftritt.  
•❓• was wird an der USB ausgegeben?  
•❓• welches Terminalprogram?  
•❓• Wie schaut die 5V & 3,3V aus? Darüber kam noch keine Rückmeldung (Oszilloskop!)  
17:35  
Rainer OE1KFR  
Das f_sub in dem Log oben deutet darauf hin, dass das extUDP Interface eingeschaltet ist. Dort kann man auch Nachrichten absetzen. Ist der Node Wifi verbunden? War er das bei den Tests auch? Ferrit auf das Kabel zum Netzteil geben?  
18:18  
Juergen DF2AP  
Bei mir war UDP nicht aktiviert. DL5WB hat es glaube wegen MeshDash aktiviert. Ich frag noch mal nach.  
18:20  
@Wolfgang: mangels Oszi und weil er bei mir das Problem so nicht hatte, gab’s keine Rückmeldung.  
👍  
16 December 2025  
00:56  
#### wolfgang z  
ohh, bedeutet das, dass die Störungen u.U. über WiFi gekommen sind? Das wäre ein ganz neuer Ansatz für die Fehlersuche.  
Man sieht auch im erwähnten "Log", dass einzelne u/o mehrere Zeichen verfälscht u/o ausgelassen werden.  
01:03  
Dieses wr�ng z.B. hat sicher wrong geheißen, wo das "o" korrumpiert wurde (Bitfehler). Ich kenne die native UDP-Übertragung zu wenig. Aber da bei dieser Übertragung keine Sicherheit des Inhaltes gewährleistet ist, kann so ein Zeichenfehler nicht erkannt werden. Die fehlenden Zeichen könnten so stark gestörte Zeichen sein, dass sie einfach nicht erkannt werden.  
??? was wäre, wenn auf dem Funkweg vom Node zum WLAN-Router die Störung erfolgen würde ???  
Dann wäre auf der Node nichts erkennbar, was auf eine Störung hindeuten würde, aber der WLAN-Router bekommt den "Schrott" dann und schickt ihn einfach nur weiter.  
01:18  
#### wolfgang z  
andererseits ist das "00:00;[0;[HEAP];1506" definitiv ein Fragment aus dem Terminal Output, welches bei mir gleich nach dem Reboot z.B. so aussieht "01:10:28;[HEAP];73588;(free)"  
Hierbei ist aber erkennbar, dass bei mir bereits beim 1.Mal die richtige Zeit erscheint.  
Aber bei dem gestörten ist die Zeit offenbar noch 00:00:00, was darauf hindeutet, dass die WiFi-Verbindung noch nicht erfolgreich war und der NTP-Server (noch) nicht erreichbar, obwohl sie zu diesem Zeitpunkt schon verfügbar sein sollte, wie hier zu sehen ist:  
[WIFI]...SSID: Drei_H288A_24G_yAFG CHAN: 2 RSSI: -40 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...connecting to CHAN: 2 BSSID: 90:FD:73:AC:F1:83  
[WIFI]...power: 78 RSSI:-40  
[WIFI]...Wait connect ...  
[WIFI]...connect OK  
[WIFI]...now listening at IP 192.168.1.187, UDP port 1990  
[WIFI]...Internet UDP-DEST meshcom.oevsv.at  
[WIFI]...Internet NTP-DEST pool.ntp.org  
00:00:02[Web]...mDNS responder started  
TimeClient now (UTC): 00:17:14  
01:17:20;[HEAP];73612;(free)  
01:20  
➡️❗️daher bitte mal die vollständige Ausgabe am Terminal nach einem RESET.  
01:30  
‼️ oha, jetzt habe ich plötzlich 2x hintereinander, nach einiger Zeit nach dem RESET einen Verlust des COM-Ports gehabt im terminal.spacehuhn.com  
Möglicherweise habe ich diese Störung nun provozieren können, indem ich NUR die USB am ESP32-Board (=schwache Stromversorgung) angesteckt hatte und keine weitere Stromversorgung über USB-C oder Schraubklemme.  
02:21  
#### wolfgang z  
wenn ich dieses Fragment weiter analysiere, dann fallen mir folgende Dinge auf:  
•1) Wenn das Board ein ESP32-E22-PCB ist, dann muss der Heap bei der 4.35h bei ≈73588 Bytes nach dem Start liegen, wie bei mir ersichtlich.  
•2) was sollen die "1506" bedeuten?  
a) Zeichenfehler, dann keine weitere Erkenntnis.  
b) da aber nur eine "0" zu einem "[" wurde, könnte ich nun annehmen, dass die Zahl 1506 offenbar unvollständig ist.  
=> aber 1506xx Bytes sind zu viel Heap bei der geg. Konfiguration. Diese Wert von ≈150kB ist nur gleich nach dem RESET, ohne WiFi u.a. Da aber dieser Teilstring via WiFi gesendet wurde, passt es nicht zusammen.  
c) 1506x wären ≈15kB, was aber schon so hart an der Grenze ist, dass ein Crash bevorsteht, was aber nicht passiert ist, da die Übertragung weiter ging, und zwar als mehrere Messages wohlgemerkt.  
d) Wenn in den "1506" vor, nach zwischen Zeichen fehlen, dann auch keine weitere Erkenntnis.  
02:23  
‼️kann ich nur wiederholen ‼️  
02:25  
➡️💥🧩 wieder geschehen!  
COM-Port Verbindungsabbrüche bei schwacher Stromversorgung sind in gewissem Maße reproduzierbar.  
Ich muss mir da aber noch eine spezielle Versuchsanordnung überlegen ...  

23 February 2026  

Detlef DG5NBF  
Läuft das Neo 6M GPS mit Werkseinstellung oder muss das vorher mit der Ublox Software eingestellt werden ? Meines wird am Board nicht erkannt. Es sucht immer die Baudraten durch. An der Ublox Software und USB Adapter wird's aber sofort erkannt....  

#### wolfgang z  
1) Es werden ALLE originalen Ublox GPS erkannt und automatisch richtig eingestellt von der FW.  
2) falls es den Effekt wie du beschrieben zeigt, dann ist es kein originales Ublox  
das sagt überhaupt nichts aus, außer, dass die Ublox Software auch nicht Originale erkennen kann.  

#### wolfgang z  
ja, aber wir könnten auch die L76K Erkennung auch für solche aktivieren und diese dann umstellen, da die ja den CASIS Befehlssatz unterstützen  

24 February 2026  
07:54  
Detlef DG5NBF  
Gibt's irgendwo eine Info oder Anleitung zu den notwendigen Einstelldaten ?  

11 March 2026  
07:27  
#### wolfgang z  
hier folgende in meinem Repository und bei LilyGo findest du alle Datenblätter bez. CASIS Befehlen.  
https://t.me/c/1987218802/1/29723  
https://t.me/c/1987218802/1/29717  

#### wolfgang z  
Das Problem damals war ja, dass ich kein solches "angeblich fake" GPS-Modul hatte. Aber im Zuge meiner Implementation des T-Beam-1W kam ich drauf, dass der ja ein L76K Modul eingebaut hat. Die nächsten Schritte ergaben sich daraus in logischer Folge.  

### Ab der FW 4.35p.04.xx sollten L76K und UBLOX GPS-Module (fast immer) einwandfrei erkannt und verwendet werden.
