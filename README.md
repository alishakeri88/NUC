# NUC
We run two JAVA packages on the NUC to receive the data from Beaglebone Black and plot them in real-time.
##SerialBuffer
This package lets us have access to the serial ports on the NUC. In linux the serial ports are listed in the /dev folder and they are usually called /dev/ttyS* so when we run the program it goes to read these devices.
Since we are connecting our sensors to the NUC via USB interface we can read their data on the /dev/rfcomm* ports which are not known by this package as a serial port! 
Here we need to make a little change to introduce these ports to our program. Fllowing commands can link the rfcomm ports to the serial ports (ttyS):

      ln -s rfcomm0 ttyS50
      ln -s rfcomm1 ttyS51

We need to make sure that these serial ports don't really exist! You can usually use the number more than 50 like what we did.
