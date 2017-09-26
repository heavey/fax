# fax
FÄXËN
## Setup printer
I have somewhat followed the guide at [smittytone](https://smittytone.wordpress.com/2013/09/23/hacking-a-thermal-till-printer-to-work-with-the-raspberry-pi/), but several steps seem to be outdated. Therefore, this is what i have done:
1. run ``sudo raspi-config``. Select ``Interfacing Options`` > ``Serial`` then specify if you want a Serial console (probably no) then if you want the Serial Port hardware enabled (probably yes). Then use ``/dev/serial0`` in any code which accesses the Serial Port.
2. run ``sudo apt-get install python-serial``
3. run ``sudo apt-get install python-imaging-tk``, but this doesnt work. Fuk.
4. get the [github.com/luopio/py-thermal-printer](github.com/luopio/py-thermal-printer) stuff
5. Change ``SERIALPORT = '/dev/ttyAMA0'`` to ``SERIALPORT = '/dev/serial0`` in ``printer.py``
6. run ``chmod 777 printer.py``

Now ./printer.py

## Setup sms
I followed [this](http://www.mattiasnorell.com/send-sms-from-a-raspberry-pi/) and [this tutorial](http://www.mattiasnorell.com/receive-sms-on-a-raspberry-pi/). 
