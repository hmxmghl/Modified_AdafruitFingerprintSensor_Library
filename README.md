
# Modified_AdafruitFingerprintSensor_Library

This library is a modified version of Adafruit Fingerprint Sensor Library. Modifications include getting full 688 bytes
template with headers from FPS module. It also include fingerprint matching functionality so one can again download template
to FPS slot and match with current fingerprint.

This library is a work of Don Jeronimo. However, the library had few bugs that caused incorrect buffer size and hence new
enrollment on FPS was never successful. I modified Don's version of library to eliminate those bugs.

You can find original library at following URL:

https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library

After installing original library, you need to replace ".cpp" and ".h" files with the ones in this repository. After that you
can follow Don's instructions at Adafruit Support page to get full 688 bytes template:

https://forums.adafruit.com/viewtopic.php?f=22&t=33229&hilit=template&start=60&sid=6a422af6548edcd7540e1f30fb26519b#p359231

In this library, template for matching is hard coded so you will still need to modify it to download template from your specific
database.

IMPORTANT NOTE:

After following Don's instructions, you need to change following lines in Adafruit library examples in order to make them work:

Serial.begin(9600)   ==>  Serial.begin(57600)
finger.begin(57600)  ==>  finger.begin(9600)
