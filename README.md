# cold-end
Firmware for ColdEND controller supporting SSD1306 and SH1106 OLED displays

Installation of SSD1306 or SH1106 OLED display:

1) Import Adafruit-GFX-Library and either Adafruit_SSD1306 or Adafruit_SH1106
   depending on which OLED display you plan to use.

2) Uncomment (define) the appropriate OLED display in config.h. Note that only one display
   at one time is allowed so dont' forget to comment the other one.

3) Flash your ColdEND, vent the system, make sure that the mist knob is fully turned clockwise
   for maximum lubrication and turn the spit knob fully counterclockwise to deactivate spit mode.
   Meter your lubrication output over 15 minutes and multiply the value by 4 to get the maximum
   quantity in milliliter per hour. Do the same with mist knob fully turned counterclockwise
   to get the minimum quantity in milliliter per hour.

4) Edit "min_ml_per_hour" and "max_ml_per_hour" in config.h to the correct values and reflash your ColdEND.


ATTENTION: Refreshing the screen takes some milliseconds and freezes the loop for this time.
In rare cases it may happen that the coolant or spit value jumps between numbers.
To avoid jumping values to interrupt the loop, turn the potentiometer slightly into one direction.

NOTE: If your stepper speed is too high and you have already set your microsteps to maximum,
decrease "mist_min_flow_rate" and "mist_max_flow_rate" since they define the stepper timing.
After changing any of these values, you will need to repeat steps 3 and 4 to calibrate the displayed quantity.

NOTE: If spit mode at times does not start, it is most likely that your mist switch is bouncing.
In this case, increase "switch_debounce" slightly.
