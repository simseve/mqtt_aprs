# mqtt-aprs-infl
Connects to the specified APRS-IS server, and posts the APRS output to MQTT and InfluxDB. 
The process parse in particular weather station and pushes the attributes to mqtt and produces the following output

```
skudo/ES3BEC-11/raw ES3BEC-11>APZSKU,WIDE2-1,qAO,HB9HCM-10:/161344z/0Iu2Te1dO!![/A=-00045/C=-06/P=D2/Skudo test
skudo/ES3BEC-11/latitude 59.4364
skudo/ES3BEC-11/longitude 24.7471
skudo/ES3BEC-11/distance 1136.49
skudo/ES3BEC-11/altitude -4.0
skudo/ES3BEC-11/climb_rate -6
skudo/ES3BEC-11/phase D2
skudo/ES3BEC-11/speed 0.0
skudo/ES3BEC-11/course 360
skudo/ES3BEC-11/comment C=-06/P=D2/Skudo test
```

Can parse parameters, or dump the raw JSON from aprslib.  It's currently for receive only from APRS-IS and sending to an MQTT server.

This script uses the aprslib, https://github.com/rossengeorgiev/aprs-python, to do the heavy APRS lifting.

INSTALL
=================
```
sudo pip install -r requirements.txt

cd ~
git clone https://github.com/Skudo-HSM/esa-poc/

With sudo:


cp ~/esa-poc/mission-gui/mqtt-aprs-infl.service /etc/systemd/system
systemctl enable mqtt-aprs-infl.service

```
Edit /etc/mqtt-aprs-infl/mqtt-aprs-infl.cfg to suit.



Forked from https://github.com/mloebl/mqtt-aprs
