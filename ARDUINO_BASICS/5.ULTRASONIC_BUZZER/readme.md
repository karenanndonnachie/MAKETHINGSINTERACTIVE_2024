# Ultrasonic Bag (or box) - head (Ultrasonic obstacle detection)
<img src="ultrasonic_workshop.jpg" width=400 /><br/>
## Make an ultrasonic + buzzer circuit like one of the ones below. Use an external power source (powerbank 9v or 4 x AA batteries will do) for your build and tape it all to the top of a paper bag or box. Place this on your head in a safe environment. Try to navigate. Try again in pairs?
<pre>
/*
This code should work to get warning cross the buzzer when something be closer than 0.5 meter
Circuit is ultrasonic sensor and buzzer +5v and Arduino uno is used
a_atef45@yahoo.com
www.zerosnones.net
+201153300223
*/
// Define pins for ultrasonic and buzzer
int const trigPin = 10;
int const echoPin = 9;
int const buzzPin = 2;
void setup()
{
pinMode(trigPin, OUTPUT); // trig pin will have pulses output
pinMode(echoPin, INPUT); // echo pin should be input to get pulse width
pinMode(buzzPin, OUTPUT); // buzz pin is output to control buzzering
}
void loop()
{
// Duration will be the input pulse width and distance will be the distance to the obstacle in centimeters
int duration, distance;
// Output pulse with 1ms width on trigPin
digitalWrite(trigPin, HIGH);
delay(1);
digitalWrite(trigPin, LOW);
// Measure the pulse input in echo pin
duration = pulseIn(echoPin, HIGH);
// Distance is half the duration devided by 29.1 (from datasheet)
distance = (duration/2) / 29.1;
// if distance less than 0.5 meter and more than 0 (0 or less means over range)
if (distance <= 50 && distance >= 0) {
// Buzz
digitalWrite(buzzPin, HIGH, 120);
} else {
// Don't buzz
digitalWrite(buzzPin, LOW);
}
// Waiting 60 ms won't hurt any one
delay(60);
}
</pre>
