# Micropython på Nodemcu


# Flash prosedyre
1.	installer usb driver: CH342SER.EXE
2.	last ned nyeste stable micropython versjon http://micropython.org/download#esp8266 og kopier til C:\python27\scripts
3.	last ned og installer python 2.7 https://www.python.org/downloads/
4.	sett enviromental properties. I kontrollpanel -> Control Panel\System and Security\System      ->   advanced system settings   -> system variables->
legg til c:\python27 under Path

5.	installer esptool.py: c:\python27\scritps>pip install esptool  
6.	plugg i nodemcu brikken med usb kabel.
7.	Fjern eksisterende flash -> 
8.	c:\python27\scripts\esptool.py --port COM7 erase_flash
9.	flash micropython på nodemcu -> 
10.	esptool.py --port COM7 --baud 9600 write_flash --flash_size=detect 0 esp8266-20171101-v1.9.3.bin




# Web REPL oppsett
1.	Koble nodemcu til usb. 
2.	i putty innstillinger under serial, sett flow control til «none»
3.	koble til nodemcu med baud rate 115200
4.	trykk inn RST knapp på nodemcu kortet.
5.	skriv kommando: import webrepl_setup
6.	skriv kommando: webrepl.start()
7.	restart nodemcu

du kan nå koble til wifi nettverket MicroPython-****** med passord: micropythoN
her er en web repl som du kan bruke til å koble til node mcu https://micropython.org/webrepl/  ip adressen til nodemcu er ws://192.168.4.1:8266/
i web repl kan en laste opp og ned filer til nodemcu.



# Set opp Wlan tilkobling 

1.	import network
2.	wlan = network.WLAN(network.STA_IF)
3.	wlan.active(True)
4.	wlan.active()	for å sjekke om wlan er på
5.	wlan.connect(¨ssid¨, ¨passord¨)
6.	wlan.isconnected() 	for å sjekke om nodemcu er koblet til wifi nettverk
7.	wlan.ifconfig() 	for å få IP adresse til nodemcu

restart chip. Nettverk blir husket. Eksisterende AP er også aktivt.
Kan nå bruke web repl med ny ip adresse. Bruk samme port nr.: 8266
Ingen statisk ip adresse.


# IDE og filoverføring
https://www.gitbook.com/book/dfrobot/upycraft/details

direct download link : https://dfrobot.gitbooks.io/upycraft/content/

# GPIO setup

pin4= machine.Pin(4,machine.Pin.IN)  
pin5= machine.Pin(5,machine.Pin.OUT)

# Moduler
https://pypi.python.org/pypi?%3Aaction=search&term=micropython&submit=search
threading modul : https://docs.micropython.org/en/latest/pyboard/library/_thread.html#module-_thread

# esp8266 funksjoner
https://docs.micropython.org/en/latest/pyboard/library/esp.html



# Referanse
 web repl https://www.youtube.com/watch?v=TNvDhM7sGxs&t=300s
web repl https://learn.adafruit.com/micropython-basics-esp8266-webrepl
Flash https://docs.micropython.org/en/latest/esp8266/esp8266/tutorial/intro.html
Micropython basic https://learn.adafruit.com/micropython-basics-what-is-micropython/
