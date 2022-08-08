# Merging code
## Most of the time we will need to take two (or more) separate snippets of code and weave or merge them together.
* Copy and paste the code(s) to a text-friendly app (like notes or Atom)
* Find & highlight your functions
* Find & Highlight your variables ==> *you must not use the same name for more than one thing*
* Make sure there are NO DUPLICATE FUNCTIONS --> YOU CAN ONLY HAVE ONE setup() and one loop() function
* Make your if else statements talk to each other
<br/>
## Let's try it!
We will merge our 'Blink' sketch and a 'Fade' sketch
### Blink (flashes built-in LED):
<pre>
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
</pre>
### Fade (fades an LED on pin 9):
<pre>

int led = 9;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(led, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // set the brightness of pin 9:
  analogWrite(led, brightness);

  // change the brightness for next time through the loop:
  brightness = brightness + fadeAmount;

  // reverse the direction of the fading at the ends of the fade:
  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }
  // wait for 30 milliseconds to see the dimming effect
  delay(30);
}
</pre>
& merged
<pre>
#include <Servo.h>
// create servo object to control a servo (up to 12?)
Servo myservo;  
int pos = 0; // variable to store the servo position

// constants won't change. 
// Used here to set a pin number:
const int ledPin =  LED_BUILTIN;
// ledState used to set the LED
int ledState = LOW; 
// will store last time LED was updated
unsigned long previousMillis = 0;        
// constants won't change
// interval at which to blink (milliseconds)
const long interval = 1000; 
        
void setupBlink() {
  // set the digital pin as output:
  pinMode(ledPin, OUTPUT);
}
void setup() {
  // attaches the servo on pin 9 to the servo object
  myservo.attach(9);
  setupBlink();
}

void loopBlink() {
  // currentMillis = will store how much time has passed
  unsigned long currentMillis = millis();

  if (currentMillis - previousMillis >= interval) {
    // save the last time you blinked the LED
    previousMillis = currentMillis;

    // if the LED is off, turn it on, and vice-versa
    if (ledState == LOW) {
      ledState = HIGH;
    } else {
      ledState = LOW;
    }

    // set the LED with the ledState of the variable
    digitalWrite(ledPin, ledState);
  }
}

void loop() {
  // goes from 0 degrees to 180 degrees
  for (pos = 0; pos <= 180; pos += 1) { 
    // go to position in variable 'pos’
    myservo.write(pos);
    loopBlink();              
    delay(5); 
  }
  
for (pos = 180; pos >= 0; pos -= 1) { 
    myservo.write(pos); 
    loopBlink();
    delay(5);
  }
}
    </pre>
[This extended tutorial](https://en.wikiversity.org/wiki/Arduino_Sketch_Merge) can explain in more detail.
