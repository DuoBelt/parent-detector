## Set up the camera preview

1. At the start of your program, import the `Picamera` class from the `picamera` library so that we can use code to control the Camera Module.

    ```python
    from picamera import PiCamera
    ```

1. Add a line of code to create a `PiCamera` object. Make sure this line of code is above the infinite loop.

    ```python
    camera = PiCamera()
    ```

1. Add to your existing code to start the camera preview when the sensor is activated and stop the preview when no motion is detected.


[[[rpi-picamera-take-photo]]]

--- hints ---

--- hint ---
Make sure that the code you add to start the camera preview is __indented__ so that Python knows it is inside the loop.
--- /hint ---

--- hint ---
The code to begin the camera preview is as follows. Can you work out the code to stop the preview?
```python
camera.start_preview()
```
--- /hint ---

--- hint ---
Shown below is the code to tell the sensor to wait for motion to be detected. Can you work out the code telling the sensor to wait for no motion to be detected?
```python
pir.wait_for_motion()
```
--- /hint ---

--- hint ---
Here are the lines of code you will need, but they are not in the right order.
```python
pir.wait_for_motion()
pir.wait_for_no_motion()
camera.start_preview()
camera.stop_preview()
```
--- /hint ---

--- hint ---
Here is the finished code:
```python
while True:
    pir.wait_for_motion()
    print("Motion detected!")
    camera.start_preview()
    pir.wait_for_no_motion()
    camera.stop_preview()
```
--- /hint ---

--- /hints ---

Save your code, and run it by pressing `F5`. Test that the camera preview appears when the motion sensor is activated, and stops when the motion sensor is no longer active.
