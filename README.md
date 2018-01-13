# Kod
Çizgi izleyen kodu



#include <QTRSensors.h>
#define NUM_SENSORS  6// kullanılan sensor sayısı 
QTRSensorsAnalog qtra((unsigned char[]) {0, 1, 2, 3, 4, 5}, NUM_SENSORS);
unsigned int sensorValues[NUM_SENSORS];
int sag_i = 5;
int sag_g = 6;
int hiz_sag = 9;
int sol_i = 7;
int sol_g = 8;
int hiz_sol = 10;
void setup()
{
  pinMode(sag_i, OUTPUT);
  pinMode(sag_g, OUTPUT);
  pinMode(sol_i, OUTPUT);
  pinMode(sol_g, OUTPUT);
  pinMode(hiz_sag, OUTPUT);
  pinMode(hiz_sol, OUTPUT);

  delay(500);
  for (int i = 0; i < 400; i++)
  {
    qtra.calibrate();
  }
  Serial.begin(9600);
  delay(1000);
}


void loop()
{
  unsigned int position = qtra.readLine(sensorValues);
  Serial.println(position); 
  delay(150);

if( position<700)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,140)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,40);  
}
if(position>700 || position<1500)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,160)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,100);  
}
if(position>1500 || position<2100)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,180)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,160);  
}
if(position>2100 || position<3000)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,180)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,180);  
}
if(position>3000 || position<3700)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,160)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,180);  
}
if(position>3700 || position<4300)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,100)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,160);  
}
if(position>4300 || position<5000)
{
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,140)
digitalWrite(sag_i,HIGH);
digitalWrite(sag_g,LOW);
analogWrite(hiz_sag,40);  
}

