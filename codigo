
import sys
import os, subprocess
from subprocess import Popen
FILE = ['hidraw0','hidraw1','hidraw2','hidraw3','hidraw4','hidraw5','hidraw6','hidraw7','hidraw8']

usbport= subprocess.Popen(('ls /dev/hidraw*'), shell =True,
                     stdout=subprocess.PIPE, stderr=subprocess.PIPE)
inet = usbport.stdout.read().decode('utf-8')
xnet = inet.split()

b = int(len(xnet))

for usb in range(b):
    a = xnet[usb]
    print (a)
    usbport2= subprocess.Popen(('sudo cat /sys/class/hidraw/'+FILE[usb]+'/device/uevent | grep HID_NAME | cut -d "=" -f2'), shell =True,
                     stdout=subprocess.PIPE, stderr=subprocess.PIPE)
    inet2 = usbport2.stdout.read().decode('utf-8')
    xnet2 = inet2.split()
    print (inet2)
    os.system('sudo chmod a+rwx '+a)
