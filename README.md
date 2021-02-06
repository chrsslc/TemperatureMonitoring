# TemperatureMonitoring
Temperature Monitoring

----index.php----
Website file, hosted with apache

----Crontab----
used to automatically run scripts on a schedule

----doghousetempemailalive.py----
if scheduled in crontab, and not disabled via push button, it will send out the current temperature every hour. This acts a monitor when you can't access teh website on your home LAN, and as an "alive" signal

----Doghousetempemailwarn.py----
if scheduled in crontab, and not idsabled via push button, it will send an SMS alert when it reads a value outside your setpoints

----Doghousetemplog.py----
scheduled by crontab, this records to the database, the temperatures from the dynamic list of temperature probes connected

----email_handler.py----
send emails using smtp, from another author - https://iotbytes.wordpress.com/programmatically-send-e-mail-from-raspberry-pi-using-python-and-gmail/

----Wiring Breakdown----
Blue: (failsafe) Enable/Disable Hourly Update via 3.3v to GPIO20 (pin 38). 2 x 3K ohm Resistor to limit current. Button can be placed in series to allow user enable/disable.
Orange: (failsafe) Enable/Disable Alarm message via 3.3v to GPIO21 (pin 40). 2 x 3K ohm Resistor to limit current. Button can be placed in series to allow user enable/disable.
Green: Ground to pin 6.
Yellow: OneWire Data In to GPIO 4 (pin 7). 5k Ohm resistor from data bus to 3.3v, as per OneWire Standard.
Red: 3.3v supply from pin 1.
