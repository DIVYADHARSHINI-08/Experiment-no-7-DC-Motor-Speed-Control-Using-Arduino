###  DATE: 05-04-2024 
###  NAME: R.DIVYA DHARSHINI
###  ROLL NO : 212223040042
###  DEPARTMENT: B.E.CSE
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int in1=5;
int in2=6;
int en=3;

void setup()
{
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(en, OUTPUT);
}

void loop()
{
  analogWrite(en,50);
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  delay(500);
  
}
```

### OUTPUT
![EXP DD](https://github.com/DIVYADHARSHINI-08/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/145210448/379d8aae-4c8e-4b68-8aae-c8925c14f714)

![2](https://github.com/DIVYADHARSHINI-08/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/145210448/0811ca8e-63bf-4465-beaa-bf0d81c5c6ef)

### GRAPH AND TABULATION

![3](https://github.com/DIVYADHARSHINI-08/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/145210448/edad0839-8b30-4d04-b923-45ada7e5ea19)

![4](https://github.com/DIVYADHARSHINI-08/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/145210448/9e327594-f206-4d79-8ba9-9d559be687fd) 

### RESULTS AND DISCUSSION 

Thus, the speed and the direction of a DC motor using L293D driver ic( H- bridge) is controlled.
