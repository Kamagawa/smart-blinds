# smart-blinds
Blinds-opening robot that makes it easier to get up early



## bluetooth pairing process:
- look for bt adapter
  - if no adapter, quit app
- enable bt adapter
- look for a paired smart blinds
  - if none, take user to bluetooth pairing screen, then return to app
- paired and ready to communicate

# Ideas
mechanical design:
- make the stepper motor's position adjustable
  - attach the motor to a flexible tube-like arm
- reduce blinds cord slippage
  - by using a vertical holder
  - by cutting out a "circle" of holes, allowing the l-bracket to be mounted at a variey of angles

mobile app:
- automatically determine opening and closing times based on location

# Electric Circuit Design
powering arduino - options:
- barrel jack 7-12V regulated
- vin 7-12V regulated
- usb 5V unregulated

## scenario 1 - ideal, assuming motor is strong enough:
- my current 7.5v adapter with 1A
- motor controller and motor get power from arduino vin
- parts to order: motor, motor bracket, screws

## scenario 2 - 12V motor:
- will need a 12 V adapter with terminal block connector
- cannot use arduino jack and vin to transfer 12V power since too much current
- motor and motor controller will get power directly from source
- parts to order: motor, motor bracket, screws, 12V adapter, protoboard

# App function
- main
  - on/off switch for timed blinds opening
  - timed opening - two modes: 
    - custom time: set custom times at which to set blinds to open and close positions from calibration
    - [automatic: automatically open and close blinds based on your location's sunrise and sundown times]
  - manual blinds control
- sync
  - 
- calibrate
  - manually set open and closed positions
  
--------------------------------------------------------------------------------------------------------------------

## activities: main, sync, calibrate
- SharedPreferences for current mode and open/closing times and positions
- could use PreferenceFragment for calibration screen settings
- use onSharedPreferenceChangeListener to update UI after preference changes
  - in onSharedPreferenceChangeListener of activity to be updated:
    - implement on onSharedPreferenceChanged
    - registerOnSharedPreferenceChangeListener
    - unregisterOnSharedPreferenceChangeListener
- alarmmanager for scheduled blinds adjustments

- main activity: two options
  - preferences activity with custom preference for blinds position adjustment, and custom preference for switch/time select
  - regular activity:
    - with linearlayout
    - fragments for time and position controls, or a "compound component": https://developer.android.com/guide/topics/ui/custom-components.html
    - and sharedpreferences.editor to update settings
  
--------------------------------------------------------------------------------------------------------------------

# Components List (Cost)
- arduino uno: ~$15
- [sensor shield]: $13
- bluetooth module: $10
- motor controller: $14
- motor: $19
- motor bracket: $10
- 12V adapter: $14
- protoboard: $0.30

- acrylic board
- screws, standoffs, etc.
- motor attachments
