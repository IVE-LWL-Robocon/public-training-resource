# VESC tutorial

# Index
1. [What is VESC?](#vesc)
2. How to control the motor by VESC?
    1. [Without coding: VESC Tool](#vesctool)
        1. [Connection](#vesctool_conn)
        2. [Calibration](#vesctool_calib)
        3. [Controlling](#vesctool_control)
    2. [With coding: MUCs](#withcoding)

## What is VESC? <a name="vesc"></a>
VESC is an open source project. Some BLDC motor drivers developed from the project. Visit the [VESC Project Website](https://vesc-project.com/Hardware), get more information.

## How to control the motor by VESC?
### Without coding: VESC Tool <a name="vesctool"></a>
We can use VESC Tool to control the motor without coding. First, you need to download VESC Tool from [VESC Project Website](https://vesc-project.com/vesc_tool) (You need to create an account). Or you can find the app in private repositories, path: [Useful-resource](https://github.com/IVE-LWL-Robocon/Useful-resource) -> [vesc](https://github.com/IVE-LWL-Robocon/Useful-resource/tree/main/vesc). We recommend to use version 3.00, not the latest one (ver. 3.01). The latest version is not stable, use it as your risk. You try, you die, don't ask why.

#### Connection <a name="vesctool_conn"></a>
Below picture is an example. It shows how to connect the power part.<br>
<img src="photo/vesc_power_conn.jpeg" width="800"><br><br>

Connect the encoder with vesc, if it has. (if doesn't, it is fine) Below picture show the connection.<br>
<img src="photo/encoder_conn.jpeg" height="500">
<img src="photo/encoder_conn2.png" height="500"><br><br>

Then, connect the vesc to PC and turn on the estop. Run the VESC Tool. In "Welcome & Wizards" page, click "AutoConnect".<br>
<img src="photo/conn1.bmp" width="800"><br><br>
If auto connection failed, we need to manual connect, the operation is similar with Arduino IDE. Change to "Connection" page. Reflash the COM list and select correct COM. Set the baud rate is ***115200***. And connect. If it does not work, please check the connection cable and power source.<br>
*p.s. The vesc should light up the LEDs, if doesn't, it means that no power supply from battery. It would not working.*<br>
<img src="photo/conn2.bmp" width="800"><br><br>

If you see the rigth corner show message like below, it connected.<br>
<img src="photo/conn3.PNG">

#### Calibration <a name="vesctool_calib"></a>
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!<br>
<span style="color:red">***If you change the setup of motor or replace motor, you need to re-calibration again. It is very important. Otherwise it may lose control and burn the driver and motor.***</span><br>
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!<br>

Back to "Welcome & Wizards" page, click "Setup Motors FOC" to calibrate.<br>
<img src="photo/calib1.bmp" width="800"><br><br>

It will show the pop up. Based on your devices, select the suitable choice. For example, DJI M3508 P19 is an outrunner motor and the weight is around 380g. Therefore, we select 200g outrunning motor. And click "Next". It will show a warning. If you confirm it is fine, just click yes.<br>
<img src="photo/calib2.bmp" width="800"><br><br>

<img src="photo/calib3.png" width="800"><br><br>
Select the type of battery, we always use Li-ion battery (?????????).<br>
Below figures are example, it show how to know the number of cells series.<br>
1. Check the label on the packet. "P" part means Parallel. The "S" part means "Series". "6S1P" means 6 cells in serises, 1 parallel. Therefore, we should type 6 in the box.<br><br>
*!!!!!!  Warning  !!!!!!<br>
Don't mxied up the "Series" and "Parallel", you should type **the number of "Series"**.<br>
Otherwise it may damage the vesc, motor and battery*<br>
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!<br>
<img src="photo/batt1.jpeg" width="800"><br>

2. Count number of the packet number. <br>
<img src="photo/batt2.jpeg" width="800"><br><br>

The battery packet labels its capacity. 1000mAH = 1AH, transform by yourself or online calculator. In the example, 3200mAh = 3.2Ah, therefore we should type 3.2. And click "Next".<br>

Check the "Direct Drive". then click "Run Detection". <br>
It will popup a message. Before you confirm it, please make sure that the motor is clear and hold your estop. After you confirmed, it will make some noise and start to rotate. It is normal. *If you don't think so, press the estop button immediately*.<br>
<img src="photo/setup1.bmp" width="800"><br>

Wait a few mins, it will show you the message like below. It means the calibration finished.<br>
<img src="photo/setup2.bmp" width="800"><br>

#### Controlling <a name="vesctool_control"></a>
1.Click the "Stream realtime data".<br>
2.Click the "Realtime Data".<br>
3.Open the RPM graphs.<br>
If you run a motor and put some load on it, you can see that reflected right away in the RPM graphs.<br>
<img src="photo/realtime.png" width="800"><br><br>
Click the "Enable keyboard control". Then you can use the arrow keys to control the motor.<br>
<img src="photo/controlling.png" width="800"><br>
Up and Down Arrow Keys:<br>
Current control using the current value in the lower left corner.<br><br>
Right and Left Arrow Keys:<br>
Duty cycle control. Slowly ramps up and down the cuty cycle. When e.g. starting with right and then also holding left, the duty cycle is ramped higher.<br><br>
Page Down:<br>
Brake with the current set in the lower left corner.<br>
<img src="photo/keyboard.jpeg" width="800"><br><br>

You can also change the value and press the button to turn on the motor. The following are the main settings that will be used.<br>
1.Duty cycle<br>
2.RPM<br>
3.Full brake<br>
4.Switch off<br>
<img src="photo/controlling2.png" width="800"><br><br>

## With coding: MUCs <a name="withcoding"></a>
Coming soon~
