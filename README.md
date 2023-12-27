# arduino-robot
Материалы для сборки робота и базовый код для управления можете найти [здесь](https://github.com/m112521/bots).
## Геометрия
В данной работе робот запрограммирован выполнить следующую геометрическую фигуру:
![траектория](траектория.jpg)
## Программный код
Ниже написан код для выполнения заданной фигуры:
```
#include <IRremote.hpp>

#define IR_RECEIVE_PIN 0
#define IR_BUTTON_PLUS 21
#define IR_BUTTON_MINUS 7
#define IR_BUTTON_CH_PLUS 71
#define IR_BUTTON_CH_MINUS 69
#define IR_BUTTON_PLAY_PAUSE 67

#define SPEED_1      5 
#define DIR_1        4
 
#define SPEED_2      6
#define DIR_2        7

void setup(){
  Serial.begin(9600);
  IrReceiver.begin(IR_RECEIVE_PIN);

  for (int i = 4; i < 8; i++) {     
    pinMode(i, OUTPUT);
  }
}

void loop(){
   if (IrReceiver.decode()) {
      IrReceiver.resume(); // Enable receiving of the next value
      int command = IrReceiver.decodedIRData.command;
      
      switch (command) {
        case IR_BUTTON_PLUS: {
          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, HIGH); // set direction
          analogWrite(SPEED_1, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);
          
          digitalWrite(DIR_2, HIGH); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, HIGH); // set direction
          analogWrite(SPEED_1, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, HIGH); // set direction
          analogWrite(SPEED_1, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_2, HIGH); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, HIGH); // set direction
          analogWrite(SPEED_1, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, LOW); // set direction
          analogWrite(SPEED_1, 255); // set speed

          digitalWrite(DIR_2, LOW); // set direction
          analogWrite(SPEED_2, 255); // set speed

          delay(800);

          digitalWrite(DIR_1, HIGH); // set direction
          analogWrite(SPEED_1, 255); // set speed

          delay(800);
          
          analogWrite(SPEED_1, 0); 
          analogWrite(SPEED_2, 0);

          break;
        
        }
        case IR_BUTTON_MINUS: { // stop mototrs
          analogWrite(SPEED_1, 0); 
          analogWrite(SPEED_2, 0);  
          break;
        }
      }
  }
}
```
## Результат
Как робот выполняет поставленную задачу можно увидеть на видео:


https://github.com/OSoba-Mask/arduino-robot/assets/144365335/b45d8a73-005f-4613-b31f-37760b1ba4b9


