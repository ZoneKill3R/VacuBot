# VacuBot

int triggerPin =2;
int echoPin = 3;
int minimum = 5;
int entfernung;
int Speed = 100;             //Drehgeschwindigkeit der Motoren anpassen
int Pin;
int MotorL=6;
int MotorR=9;
int SignalPin =10;

long messung = 0;



void Measure()
  {
  digitalWrite(triggerPin,LOW);
  delayMicroseconds(2);
  digitalWrite(triggerPin,HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin,LOW); 
  messung = pulseIn(echoPin,HIGH);
  entfernung = (messung*0.0343)/2;   
  }



void Forward()
  {
    digitalWrite(5,HIGH);
    digitalWrite(8,HIGH);
    digitalWrite(4,LOW);
    digitalWrite(7,LOW);
    analogWrite(MotorR,Speed);
    analogWrite(MotorL,Speed);
   }

void TurnLeft()
  {
   digitalWrite(5,LOW);
   
   digitalWrite(4,HIGH);
 
   analogWrite(MotorR,70);
   analogWrite(MotorL,70);
  }

void setup()
  {
    pinMode(triggerPin,OUTPUT);
    pinMode(echoPin,INPUT);
    pinMode(SignalPin,INPUT);
  }
void loop()
{

delay(60);

if(digitalRead(SignalPin) == HIGH) 
  {
   Measure();
   while(entfernung < minimum)
   {
    TurnLeft();
    delay(60);
    digitalRead(SignalPin);
    
   }
   Forward();
   Measure();
   delay(60);
   digitalRead(SignalPin);
  }
else if (digitalRead(SignalPin)==LOW)
{
  digitalRead(SignalPin);
  analogWrite(MotorR,0);
  analogWrite(MotorL,0);
}
}
