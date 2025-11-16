# Ultrasonic Distance Finder (Arduino Project)

This project explains how to make a **distance finder using the HC-SR04 ultrasonic sensor** and Arduino.  
It is perfect for beginners who want to understand how the TRIG and ECHO pins work.

---

## 📷 Circuit Diagram
*(Upload your image first → Add file → Upload → circuit.jpg)*  
Then use this line to show your image:

![Circuit Diagram](circuit.jpg)

---

## 💻 Arduino Code


int trigPin = 9;
int echoPin = 10;
int duration;
int distance;

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(500);
}
