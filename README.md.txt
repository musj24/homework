### README.md

 - 광원센서의 값이 250이상이면 원이 중앙에서 상 , 하 , 좌 , 우로 움직이면서 색이 변하는 코드입니다.

 - 광원센서의 값이 250이하가 되면 모든 원이 중앙으로 모이고 빨간색으로 변합니다.

 - 원래는 원이 퍼지다가 다시 돌아오는 프로그램을 구현하려다 서서히 사라지는 형식으로 구현했습니다.

 - C언어 기반이긴 하지만 프로세싱을 모르기에 간단한 프로그래밍도 구현하기 까다로웠습니다.

 - 코드도 마음대로 구현되지 않아 깔끔하게 짜지 못한 것이 마음에 걸리는 과제였습니다.

 - 앞으로 더욱 정진하여 프로세싱을 이해하도록 하겠습니다.


- 아두이노 코드입니다.

 - void setup() {  
 - Serial.begin(9600);
 - }
 - void loop() {
- int a = analogRead(A0);
  - Serial.println(a);
  - delay(100);
- } 


- 프로세싱 코드입니다.

- import processing.serial.*;
- Serial p;
- int x = 300;
- int y = 300;

- int move = 0;
- int Height = 0;
- int Fill = 0;
- void setup(){
 - size(600,600);
 - smooth();
 - p=new Serial(this,"COM5",9600);
- }
- void draw(){
-  if(p.available()>0){
   - String m=p.readString();
   - int a = int(m.trim());
   - println(a);
   -  background(255);
   - if(a>250)
   - {
    -move+=3;
   
   - Fill+=1;
   - fill(Fill+10,Fill+12,Fill+15);
   - ellipse(x+move,y,200, 200); 
   - ellipse(x-move,y,200,200);  
   - ellipse(x,y+move,200,200);
   - ellipse(x,y-move,200,200);
   - }
  -  else    
   - { 
   - move = 0;
   - Fill = 0;
   - fill(255,0,0);
   - ellipse(x,y, 200,200);
 - }
- }
- }
