# telemetry
Planning and eventually software for model rocket telemetry project

## Specs

915MHz ISM band, will include sensor, RF transmitter, antenna, battery and probably a microcontroller + associated circuitry (bias resistors, filtering / blocking caps)

May need crystal or matching network for RF.

## Parts selection

### Accel / Gyro: LSM6DS3
datasheet: http://www.st.com/web/en/resource/technical/document/datasheet/DM00133076.pdf
Specs:
2-bytes per axis per sensor, 3 axes, 3 sensors (accel, gyro, magnet) = 18 bytes
raw data rate = 18 bytes x sample rate (ie. 1khz) would be 18kbps
not sure about protocol overhead, CRC, etc

### RF TX: 
So far like this one https://www.silabs.com/Support%20Documents/TechnicalDocs/Si4010.pdf
This one cheaper but req more external parts http://www.semtech.com/images/datasheet/sx1243.pdf

### Antenna:
Patch antenna. Looking at OSH park for fabing boards, so epsilon_r = ~4.5, h = 1.6mm (assuming copper width negligible)
Calculator here: https://www.pasternack.com/t-calculator-microstrip-ant.aspx
.. tells me approx 77mm x 100 mm for antenna. Not sure about gain. Most RF tx seem to do somewhere betwen 0dBm and 10dBm. 

Free space path loss @ 915MHz, 100 meters approx 70dB. Thinking of using rtl-sdr, not sure about rx gain yet.
