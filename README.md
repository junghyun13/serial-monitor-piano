# serial-monitor-piano
아두이노를 이용한 피아노 만들기

#define NOTE_C4 262 //도
#define NOTE_D4 294 //레
#define NOTE_E4 330
#define NOTE_F4 349
#define NOTE_G4 392
#define NOTE_A4 440
#define NOTE_B4 494
#define NOTE_C5 523 //높은도
void setup() {
  Serial.begin(9600); 
  pinMode(10,OUTPUT); //수동부저 10번 핀 연결 소리가 나야해서 output
}

void loop() {
  // put your main code here, to run repeatedly:
  if(Serial.available()>0){
    byte data=Serial.read();
    if(data=='1'){ //시리얼 모니터에 1번을 누르면 do가 출력 (1은 문자상수)
      Serial.println("do");
      tone(10,NOTE_C4,1000); //1초동안 소리가 난다!
      delay(500);
      noTone(10);
    }
    else if(data=='2'){
      Serial.println("re");
      tone(10,NOTE_D4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='3'){
      Serial.println("mi");
      tone(10,NOTE_E4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='4'){
      Serial.println("pa");
      tone(10,NOTE_F4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='5'){
      Serial.println("sol");
      tone(10,NOTE_G4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='6'){
      Serial.println("ra");
      tone(10,NOTE_A4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='7'){
      Serial.println("shi");
      tone(10,NOTE_B4,1000);
      delay(500);
      noTone(10);
    }
    else if(data=='8'){
      Serial.println("do");
      tone(10,NOTE_C5,1000);
      delay(500);
      noTone(10);
    }
  }
}
