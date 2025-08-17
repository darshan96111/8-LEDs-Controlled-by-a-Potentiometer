# 8-LEDs-Controlled-by-a-Potentiometer
“Arduino project to control 8 LEDs in sequence using a potentiometer. Demonstrates analog input reading, mapping values to outputs, and basic embedded systems control.”


int a[8]={2,3,4,5,6,7,8,9};
int pot=A0;
int num=8;
void setup() {
  // put your setup code here, to run once:
  for(int i=0;i<num;i++){
pinMode(a[i],OUTPUT);
  }
}

void loop() {
  // put your main code here, to run repeatedly:
int x=analogRead(pot);
int value=map(x,0,1023,0,num);
for(int i=0;i<num;i++){
  if(value>i){
  digitalWrite(a[i],1);
  }else {
    digitalWrite(a[i],0);
  }
}delay(50);
}
