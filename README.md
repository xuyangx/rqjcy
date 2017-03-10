void setup()

{

  pinMode(3, INPUT);

  pinMode(10, OUTPUT);

  pinMode(9, OUTPUT);

}//定义使用的引脚
void loop()

{

  if (!digitalRead(3)) {

    digitalWrite(10,HIGH);

    for (int x = 0; x <= 179; x = x + (1)) {

      tone(9,2000 + int(sin(x / 180.0 * 3.14159) * 1000));

      delay(3);

    }//如果有人经过，人体红外检测输出高电压。使得蜂鸣器发出声响
  } else {

    noTone(9);

    digitalWrite(10,LOW);



  }//若无人经过则不放出声音
}
