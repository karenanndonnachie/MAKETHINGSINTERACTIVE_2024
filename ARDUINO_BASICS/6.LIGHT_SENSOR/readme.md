# [LIGHT SENSOR (aka LDR)](https://www.tinkercad.com/things/gu7CLzyeVhF-copy-of-mti-wk2-sensors-map/editel?sharecode=WilmZ7wfkVtoqnx7rTrnqMaZHjRcI15Nl5ol3zcng9Q)
Notice the addition of the "multi-meter" in teh Tinkercad circuit, this is useful to test how much electricity is passing through two points.<br/>
## This circuit uses a Light-Dependent-Resistor (LDR) + LED + 220 ohm resistor + 1k ohm resistor<br/>
[see Tinkercad Circuit](https://www.tinkercad.com/things/gu7CLzyeVhF-copy-of-mti-wk2-sensors-map/editel?sharecode=WilmZ7wfkVtoqnx7rTrnqMaZHjRcI15Nl5ol3zcng9Q)
![Copy of MTI Wk2 – Sensors + map() (1)](https://user-images.githubusercontent.com/10482948/226572025-76f4f03c-6d7d-4db5-bd23-56b56a401cd0.png)
<pre>
int ldrPin = A0;
int ldrVal = 0;
int ledPin = 3;

int mappedVal = 0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  ldrVal = analogRead(ldrPin);
  
  mappedVal = map(ldrVal, 6, 679, 0, 255);
  
  analogWrite(ledPin, mappedVal);
  
  Serial.println(mappedVal);
  delay(50);
}
</pre>
