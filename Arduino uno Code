#include<Servo.h>
#define numofValsRec 5
#define digitsPerValRec 1

Servo servoThumb;
Servo servoIndex;
Servo servoMiddle;
Servo servoRing;
Servo servoPinky;

int valsRec[numofValsRec];
//$00000 len of the string
int stringLength = numofValsRec * digitsPerValRec +1;
int counter = 0;
bool counterStart = false; //whenever we recieve dollar sign we start our counter
String recievedString;

void setup() {
  // put your setup code here, to run once:
 Serial.begin(9600);
 servoThumb.attach(3);
 servoIndex.attach(5);
 servoMiddle.attach(6);
 servoRing.attach(9);
 servoPinky.attach(10);


}
void recieveData()
{
  while (Serial.available())
  {   
    char c = Serial.read();
    if (c == '$'){
      counterStart = true;
  }
    if (counterStart)
    {
      if (counter < stringLength)
      {
        recievedString = String(recievedString+c); //adding the values recieved from c
        counter++;
      }
        if (counter >= stringLength)
        {
          //$00000 recieved string
          for(int i = 0; i< numofValsRec; i++)
          {
            int num = (i * digitsPerValRec)+1;//store it in the array valRec 
          valsRec[i] = recievedString.substring(num,num + digitsPerValRec).toInt(); //we don't need the dollar so we start from 1 instead of zero
          }
          recievedString = "";
          counter = 0;
          counterStart = false;
          //resets all settings
          
        }
    }
 }
}



void loop() {
  recieveData();
  if (valsRec[0] == 1){
    servoThumb.write(180);
  }
  else{
    servoThumb.write(0);
  }
  if (valsRec[1] == 1){
    servoIndex.write(180);
  }
  else{
    servoIndex.write(0);
  }
  if (valsRec[2] == 1){
    servoMiddle.write(180);
  }
  else{
    servoMiddle.write(0);
  }
  if (valsRec[3] == 1){
    servoRing.write(180);
  }
  else{
    servoRing.write(0);
  }
  if (valsRec[4] == 1){
    servoPinky.write(180);
  }
  else{
    servoPinky.write(0);
  }
}
