### README.md

 - ���������� ���� 250�̻��̸� ���� �߾ӿ��� �� , �� , �� , ��� �����̸鼭 ���� ���ϴ� �ڵ��Դϴ�.

 - ���������� ���� 250���ϰ� �Ǹ� ��� ���� �߾����� ���̰� ���������� ���մϴ�.

 - ������ ���� �����ٰ� �ٽ� ���ƿ��� ���α׷��� �����Ϸ��� ������ ������� �������� �����߽��ϴ�.

 - C��� ����̱� ������ ���μ����� �𸣱⿡ ������ ���α׷��ֵ� �����ϱ� ��ٷο����ϴ�.

 - �ڵ嵵 ������� �������� �ʾ� ����ϰ� ¥�� ���� ���� ������ �ɸ��� ���������ϴ�.

 - ������ ���� �����Ͽ� ���μ����� �����ϵ��� �ϰڽ��ϴ�.


- �Ƶ��̳� �ڵ��Դϴ�.

 - void setup() {  
 - Serial.begin(9600);
 - }
 - void loop() {
- int a = analogRead(A0);
  - Serial.println(a);
  - delay(100);
- } 


- ���μ��� �ڵ��Դϴ�.

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
