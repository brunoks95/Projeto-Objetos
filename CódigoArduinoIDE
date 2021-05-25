#include <LiquidCrystal.h> 
LiquidCrystal lcd(7,6, 5, 4, 3, 2);
 
const int Sensor = 0;
float temp;

void setup() {
  Serial.begin(9600);
  lcd.begin(16, 2); 
  lcd.clear(); 
  pinMode(8, OUTPUT);
  pinMode(Sensor, INPUT);
}
 
void loop() { 
   Serial.print(Sensor);
   delay(1000);
    for (int i=0;i<1000;i++) {
        temp = temp + float(analogRead(Sensor))*167.15/(1023);
    }
    temp = temp/1000; 
    Serial.print(temp);
    if(temp < 12) {
        lcd.setCursor(0,1);
        lcd.write("Cooler desligado !"); 
        digitalWrite(8, LOW); 
    } else {
        lcd.setCursor(0,1);
        lcd.write("Cooler Ligado !"); 
        digitalWrite(8, HIGH); 
    }
    delay(1000); 
    lcd.clear(); 
    lcd.print("Temp.: "); 
    lcd.print(temp);
    lcd.write(B11011111); 
}
