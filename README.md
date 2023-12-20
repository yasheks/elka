void setup(){
  Serial.begin(9600);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, INPUT);
  pinMode(10, INPUT);
  pinMode(11, INPUT);
}
 
void loop(){
  boolean button1 = digitalRead(9);
  boolean button2 = digitalRead(10);
  boolean button3 = digitalRead(11);
  if (button1) {
    button2 = false;
    button3 = false;
    digitalWrite(2, HIGH);
    digitalWrite(3, HIGH);
    digitalWrite(4, HIGH);
    digitalWrite(5, HIGH);
    digitalWrite(6, HIGH);
    digitalWrite(7, HIGH);
    digitalWrite(8, HIGH);
    
  }
  if(button2){
    button1 = false;
    button3 = false;
    for (int i=0;i<255;i++)
    {
      digitalWrite(2, i);
      digitalWrite(3, i);
      digitalWrite(4, i);
      digitalWrite(5, i);
      digitalWrite(6, i);
      digitalWrite(7, i);
      digitalWrite(8, i);
      delay(5);
    }
    for (int i=255;i>0;i--)
    {
      digitalWrite(2, i);
      digitalWrite(3, i);
      digitalWrite(4, i);
      digitalWrite(5, i);
      digitalWrite(6, i);
      digitalWrite(7, i);
      digitalWrite(8, i);
      delay(5);
    }
  }
  if(button3)
  {
    button2 = false;
    button1 = false;
    while(button3)
    {
      digitalWrite(2, HIGH);
      delay(1000);
      digitalWrite(3, HIGH);
      digitalWrite(4, HIGH);
      delay(1000);
      digitalWrite(5, HIGH);
      digitalWrite(6, HIGH);
      digitalWrite(7, HIGH);
      digitalWrite(8, HIGH);
      delay(1000);
      digitalWrite(2, LOW);
      delay(1000);
      digitalWrite(3, LOW);
      digitalWrite(4, LOW);
      delay(1000);
      digitalWrite(5, LOW);
      digitalWrite(6, LOW);
      digitalWrite(7, LOW);
      digitalWrite(8, LOW);
      delay(1000);
      
    }
  }
}
