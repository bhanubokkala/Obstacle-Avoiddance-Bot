onst int M1_1 = 2;
const int M1_2 = 3;
const int M2_1 = 5;
const int M2_2 = 4;
const int M3_1 = 6;
const int M3_2 = 7;
const int M4_1 = 8;
const int M4_2 = 14;
long readUltrasonicDistance(int triggerPin, int echoPin)
{
pinMode(triggerPin, OUTPUT);
digitalWrite(triggerPin, LOW);
delayMicroseconds(2);
digitalWrite(triggerPin, HIGH);
delayMicroseconds(10);
digitalWrite(triggerPin, LOW);
pinMode(echoPin, INPUT);
return pulseIn(echoPin, HIGH);
}
void setup()
{
pinMode(2, OUTPUT);
pinMode(3, OUTPUT);
pinMode(5, OUTPUT);
pinMode(4, OUTPUT);
pinMode(6, OUTPUT);
pinMode(7, OUTPUT);
pinMode(8, OUTPUT);
pinMode(14, OUTPUT);
}
void loop()
{
if (( 0.01723 * readUltrasonicDistance(10, 11) < 20))
{
digitalWrite(M1_1, LOW);
digitalWrite(M1_2, LOW);
digitalWrite(M2_1, LOW);
digitalWrite(M2_2, LOW);
digitalWrite(M3_1, LOW);
digitalWrite(M3_2, LOW);
digitalWrite(M4_1, LOW);
digitalWrite(M4_2, LOW);
delay(2*1000);
digitalWrite(M1_1, LOW);
digitalWrite(M1_2, HIGH);
digitalWrite(M2_1, LOW);
digitalWrite(M2_2, HIGH);
digitalWrite(M3_1, LOW);
digitalWrite(M3_2, HIGH);
digitalWrite(M4_1, LOW);
digitalWrite(M4_2, HIGH);
delay(2*1000);
digitalWrite(M1_1, LOW);
digitalWrite(M1_2, HIGH);
digitalWrite(M2_1, LOW);
digitalWrite(M2_2, HIGH);
digitalWrite(M3_1, HIGH);
digitalWrite(M3_2, LOW);
digitalWrite(M4_1, HIGH);
digitalWrite(M4_2, LOW);
delay(3*1000);
}
else
{
digitalWrite(M1_1, HIGH);
digitalWrite(M1_2, LOW);
digitalWrite(M2_1, HIGH);
digitalWrite(M2_2, LOW);
digitalWrite(M3_1, HIGH);
digitalWrite(M3_2, LOW);
digitalWrite(M4_1, HIGH);
digitalWrite(M4_2, LOW);
}
}
