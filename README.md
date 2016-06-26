# Project-4
RGB LED
const int redLEDPin = 11;
const int blueLEDPin = 10;
const int greenLEDPin = 9; 

const int redSensorPin = A0;
const int blueSensorPin = A1;
const int greenSensorPin = A2;

int redValue = 0;
int blueValue = 0;
int greenValue = 0;

int redSensorValue = 0;
int blueSensorValue = 0;
int greenSensorValue =0;


void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);

pinMode(greenLEDPin, OUTPUT);
pinMode(blueLEDPin, OUTPUT);
pinMode(redLEDPin,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:

  redSensorValue = analogRead(redSensorPin);
  delay (5);
  blueSensorValue = analogRead(blueSensorPin);
  delay (5);
  greenSensorValue = analogRead (greenSensorPin);

redValue = redSensorValue / 4;
greenValue = greenSensorValue / 4;
blueValue = blueSensorValue / 4;

  
  
  Serial.print("Red Value: ");
  Serial.print(redValue);
  Serial.print(", Blue Value: ");
  Serial.print(blueValue);
  Serial.print(", Green Value: ");
  Serial.println(greenValue);
 delay(1000);

  analogWrite(greenLEDPin,greenValue);
  analogWrite(redLEDPin,redValue);
  analogWrite(blueLEDPin,blueValue);
 
}
