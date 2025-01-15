# remotely control your micro:bit from smartphone via BLE (Bluetooth Low Energy).

to use, please access URL 
https://secile.github.io/micropad/

You can see screen below.
- Press '🚩' button to connect your micro:bit.
- Press '🛑' button to disconnect.

![image](https://github.com/user-attachments/assets/0cbb2cc2-be83-4312-882f-1917065aac9d)

# Control.
There are three kinds of control.

1. Analog Stick

![AnalogStick](https://github.com/user-attachments/assets/c1fad99e-c844-4899-8265-e20e59c3212c)

2. Button

![image](https://github.com/user-attachments/assets/be318136-3676-4d92-816f-4f03a7052343)

3. Slider

![Slider](https://github.com/user-attachments/assets/3873f6b0-f230-4080-9676-c25ebb8b722d)

# transfer format.
On control updated, micropad send text line to micro:bit via BLE. Text format is csv with 3 params. Format is 'ControlID, Value1, Value2'.  
ControlID is unique ID every control has it own. Value1 and Value2 is up to control kind.

- Analog Stick
    - ControlID: 'a1'(left stick) or 'a2'(right stick)
    - Value1: radian angle clockwise from the X axis. (rounded in 8 directions)
    - Value2: power. distance from origin. range 0.0-1.0. (rounded in 3 levels, 0.0 or 0.5 or 1.0.)
    - e.g. 'a1, 3.14, 0.5'
- Button
    - ControlID: 'b1' or 'b2'
    - Value1: '1'(press) or '0'(release).
    - Value2: '0'(reserved).
    - e.g. 'b2, 1, 0'
- Slider
    - ControlID: 's1'
    - Value1: ratio with 0.0-1.0. (0.1 step)
    - Value2: '0'(reserved).
    - e.g. 's1, 0.7, 0'
