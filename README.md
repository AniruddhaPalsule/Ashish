# Ashish 
New code

#define m11 2 // M1a
#define m12 3 // M1b
#define m21 4 // M2a
#define m22 5 // M2b
int data;
void forward()
{
digitalWrite(m21, HIGH);
digitalWrite(m22, LOW);
}
void left()
{
digitalWrite(m11, LOW);
digitalWrite(m12, HIGH);
delay(950);
digitalWrite(m12, LOW);
}
void backward()
{
digitalWrite(m21, LOW);
digitalWrite(m22, HIGH);
}
void right()
{
digitalWrite(m11, HIGH);
digitalWrite(m12, LOW);
delay(950);
digitalWrite(m11, LOW);
}
void Stop()
{
digitalWrite(m11, LOW);
digitalWrite(m12, LOW);
digitalWrite(m21, LOW);
digitalWrite(m22, LOW);
}
void setup()
{
Serial.begin(9600);
pinMode(m11, OUTPUT);
pinMode(m12, OUTPUT);
pinMode(m21, OUTPUT);
pinMode(m22, OUTPUT);
}
void loop()
{
while(Serial.available()>0)
{
 data = Serial.read();

if(data ==’1′) // forward
{
Serial.println(“Forward”);
forward();

}
else if(data ==’2′) //left
{
Serial.println(“Left”);
right();

}
else if(data ==’3′) //right
{
Serial.println(“right”);
left();

}

else if(data ==’4′) //backward
{
Serial.println(“backward”);
backward();

}
else if(data ==’5′) //stop
{
Serial.println(“stop”);
Stop();

}
}


}
