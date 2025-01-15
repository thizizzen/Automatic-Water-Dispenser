#include <Servo.h>
// Pin definitions
const int trigPin = 9;
const int echoPin = 8;
Servo myServo;
const int glassDetectDistance = 20;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  myServo.attach(10);
  myServo.write(0);
  Serial.begin(9600);
}

void loop() {
  int distance = getUltrasonicDistance();

  if (distance <= glassDetectDistance) {
    myServo.write(180);
    Serial.println("Glass detected. Filling...");
  } else {
    myServo.write(0);
    Serial.println("No glass detected.");
  }
}

int getUltrasonicDistance() {
  digitalWrite(trigPin, LOW);
  digitalWrite(trigPin, HIGH);
  digitalWrite(trigPin, LOW);
  return pulseIn(echoPin, HIGH) * 0.034 / 2;
}
