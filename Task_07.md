/* * Project: Task 7 - Ultrasonic Radar System with LCD Interface
 * Author: Anvita Pranjal (BTech ECE, UVCE)
 * Tinkercad Link: (https://www.tinkercad.com/things/fEPJFLWaGIp/editel?returnTo=%2Fdashboard&sharecode=7pjNjsQmSbtVaAE-kbRMMKHs5v5eo0lf9pb8UROkteQ)]
 * -----------------------------------------------------------
 * Description: Scans 150-degree field using HC-SR04 and Servo.
 * Displays real-time coordinates on an I2C 16x2 LCD.
 */

#include <Wire.h> 
#include <LiquidCrystal_I2C.h>
#include <Servo.h>

// Initialize LCD (Address 0x27 or 0x3F are common for I2C)
LiquidCrystal_I2C lcd(0x27, 16, 2); 
Servo myServo;

const int trigPin = 9;
const int echoPin = 10;

void setup() {
  lcd.init();
  lcd.backlight();
  myServo.attach(11); // Signal pin for Servo
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  
  // Quick Welcome Message
  lcd.setCursor(0,0);
  lcd.print("Radar System");
  lcd.setCursor(0,1);
  lcd.print("Initializing...");
  delay(2000);
}

void loop() {
  // Sweep from 15 to 165 degrees
  for(int i=15; i<=165; i++) {  
    myServo.write(i);
    int dist = getDistance();
    updateLCD(i, dist);
    delay(50); // Small delay for stable LCD refresh
  }
  
  // Sweep back from 165 to 15 degrees
  for(int i=165; i>=15; i--) {  
    myServo.write(i);
    int dist = getDistance();
    updateLCD(i, dist);
    delay(50);
  }
}

long getDistance() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  long duration = pulseIn(echoPin, HIGH);
  return duration * 0.034 / 2;
}

void updateLCD(int angle, int distance) {
  lcd.clear();
  lcd.setCursor(0,0);
  lcd.print("Angle: ");
  lcd.print(angle);
  lcd.print((char)223); // Prints the degree symbol °
  
  lcd.setCursor(0,1);
  lcd.print("Dist: ");
  if (distance > 100) {
    lcd.print("Clear"); // Visual logic for "No obstacle"
  } else {
    lcd.print(distance);
    lcd.print(" cm");
  }
}
