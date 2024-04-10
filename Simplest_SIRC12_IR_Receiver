#define IRPin 10

void setup() {
  pinMode(IRPin, INPUT);
  Serial.begin(115200);
}

void loop() {
  int Code = getSIRC12();
  if(Code != -1) Serial.println(Code, HEX);
}

int getSIRC12() {
  if (pulseIn(IRPin, LOW, 55000UL) > 2300) {
    int IRCode = 0;
    for (int i = 0; i < 12; i++) {
      IRCode |= (pulseIn(IRPin, LOW) > 900) << i;
    }
    return IRCode;
  }
  return -1;
}
