void setup(){
  Serial.begin(9600);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, INPUT_PULLUP);
  pinMode(10, INPUT_PULLUP);
  pinMode(11, INPUT_PULLUP);
}

void loop(){
  boolean button1 = !digitalRead(9);
  boolean button2 = !digitalRead(10);
  boolean button3 = !digitalRead(11);
  
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
    delay(2000);
    digitalWrite(2, LOW);
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
    digitalWrite(7, LOW);
    digitalWrite(8, LOW);
    delay(2000);
  }
  else if(button2){
    button1 = false;
    button3 = false;
    
    for (int i=0; i<255; i++)
    {
      analogWrite(2, i);
      analogWrite(3, i);
      analogWrite(4, i);
      analogWrite(5, i);
      analogWrite(6, i);
      analogWrite(7, i);
      analogWrite(8, i);
      delay(5);
    }
    delay(200);
    for (int i=255; i>0; i--)
    {
      analogWrite(2, i);
      analogWrite(3, i);
      analogWrite(4, i);
      analogWrite(5, i);
      analogWrite(6, i);
      analogWrite(7, i);
      analogWrite(8, i);
      delay(5);
    }
    delay(200);
  }
  else if (button3) {
    button2 = false;
    button1 = false;

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
  else {
    digitalWrite(2, LOW);
    digitalWrite(3, LOW);
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
    digitalWrite(7, LOW);
    digitalWrite(8, LOW);
  }
}
