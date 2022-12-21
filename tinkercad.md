#bi0s tinkercad challenges
#1) blink an LED
```cpp
#define ledpin 11
void setup()
{
  pinMode(ledpin, OUTPUT);
}

void loop()
{
  digitalWrite(ledpin, HIGH);
  delay(1000);
  digitalWrite(ledpin, LOW);
  delay(1000);
}
```


#2) LED with button
```cpp
void setup()
{
  pinMode(11, INPUT);
  pinMode(6, OUTPUT);
}

void loop()
{
  if (digitalRead(11) == HIGH) {
    digitalWrite(6, HIGH);
  } else {
    digitalWrite(6, LOW);
  }
  delay(10);
}
```
#3) LED with Potentiometer
```cpp
#define ledpin 11
#define potpin A0
void setup()
{
  pinMode(ledpin, OUTPUT);
}

void loop()
{
  int brightness=map(analogRead(potpin),0,1023,0,255);
  analogWrite(ledpin,brightness);
}
```
#4) measure temperature with thermistor
```cpp
#define sensorpin A0
#define ledpin 6
void setup()
{
  pinMode(ledpin, OUTPUT);
  Serial.begin(115200);
}

void loop()
{
  int sensorval=analogRead(sensorpin);
  int brightness=map(sensorval,20,358,-40,125);
  analogWrite(ledpin,brightness);
  Serial.println(brightness);
}
```
#4) Servo with Potentiometer
```cpp
#include <Servo.h>
#define potpin A0

Servo servomotor;

void setup()
{
  servomotor.attach(5, 500, 2500);
}

void loop()
{
  servomotor.write(map(analogRead(potpin), 0, 1023, 0, 180));
  delay(10);
}
```
