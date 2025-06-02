# LED 예제 1
## LED 깜박이기

![LED 00](https://github.com/user-attachments/assets/4b83617f-126a-454f-a67f-2e5dd6450d10)


## 

```C
#define LED_BUILTIN 8

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  digitalWrite(LED_BUILTIN, LOW);   // turn the LED off by making the voltage LOW
  delay(1000);                      // wait for a second
}
```

## a와 b로 LED 켜고 끄기


```C
void setup()
{
  Serial.begin(9600);
  pinMode(8,OUTPUT);
}
void loop()
{
  if(Serial.available()>0)
  {
    char sData = Serial.read();
if(sData == 'a')
{
  digitalWrite(8,HIGH);
}
else if(sData == 'b')
{
digitalWrite(8,LOW);
}
}
}
```
## 3개의 LED 깜박이기

![LED 01](https://github.com/user-attachments/assets/404225fd-1db8-4e80-800e-fa1299b3134e)

```C
#define LED1 6
#define LED2 7
#define LED3 8

void setup()
{
  pinMode(LED1, OUTPUT); pinMode(LED2, OUTPUT); pinMode(LED3, OUTPUT);
}

void loop()
{
  digitalWrite(LED1, HIGH);
  digitalWrite(LED2, HIGH);
  digitalWrite(LED3, HIGH);
  delay(1000);
  digitalWrite(LED1, LOW);
  digitalWrite(LED2, LOW);
  digitalWrite(LED3, LOW);
  delay(1000);
}
```

## 버튼으로 LED 깜박이기

![LED 02](https://github.com/user-attachments/assets/de149b57-5069-4e4f-8120-1b993e3f1e7b)

```C
#define BUTTON 4
#define LED_BLUE 7
#define LED_RED 6
#define DELAY_TIME 80

int state = 0;

void setup()
{
  Serial.begin(9600);
  pinMode(BUTTON, INPUT_PULLUP);
  pinMode(LED_BLUE, OUTPUT);
  pinMode(LED_RED, OUTPUT);
}

void loop()
{
int buttonValue = !digitalRead(BUTTON);

if (buttonValue == 1)
{
 state = !state;
 delay(500);
}

if(state == 0)
{
 digitalWrite(LED_BLUE, HIGH);
 digitalWrite(LED_RED, LOW);
 delay(DELAY_TIME);
 digitalWrite(LED_RED, HIGH);
 digitalWrite(LED_BLUE, LOW);
 delay(DELAY_TIME);
}
else if (state == 1)
{
 digitalWrite(LED_BLUE, LOW);
 digitalWrite(LED_RED, LOW);
}
}
```
