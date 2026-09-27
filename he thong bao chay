const float nhiet_do_nguong = 40.0;
const int gas_nguong = 250; 
const int coi = 2;
const int leddo = 4;
const int ledxanh = 7;

void setup() {
  pinMode(coi, OUTPUT);
  pinMode(leddo, OUTPUT);
  pinMode(ledxanh, OUTPUT);
  Serial.begin(9600);   
}

void loop() {
  analogRead(A0); 
  delay(10);
  int tmpread = analogRead(A0); 
  float dienap = tmpread * (5.0 / 1023.0); 
  float do_c = (dienap - 0.5) * 100.0;
  
  analogRead(A1); 
  delay(10);
  int gasread = analogRead(A1); 
  
  Serial.print("nhiet do: "); 
  Serial.print(do_c);
  Serial.print(" | khoi: ");
  Serial.println(gasread); 
  
  if (do_c >= nhiet_do_nguong || gasread >= gas_nguong) {
    digitalWrite(coi, HIGH);
    digitalWrite(leddo, HIGH);
    delay(150);
    digitalWrite(coi, LOW);
    digitalWrite(leddo, LOW);
    delay(150);
  } else {
    digitalWrite(coi, LOW);
    digitalWrite(leddo, LOW);
    digitalWrite(ledxanh, HIGH);
  }
  delay(200);
}
