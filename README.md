## Dimmable_LED_Project
//do include the graph and eqn building up as well


## COMPONENTS
1.Arduino UNO
2.A LED
3.Potentiometer
4.1K ohm resisitr
5.Jumper wires

## THE CONNECTIONS
The final reading of potentiometer is taken via the Analog pin A2 and two of the other pins are connceted to 5 volts supply and grounded respectively. The power supply for the LED is provided via the digital pin 6 and the LED is grounded to complete the ckt involving the resistor too.

## HOW IT WORKS
The pin A2 for potentiometer is taken as the input pin while the pin 6 for the LED is taken as the ouput pin. As the reading from the potentiometer is in the range of 0 to 1023 meanwhile the input range for the analog input for LED is 0 to 255, there is the need of conversion of reading from potentiometer to the suitable range for analog input for LED.
So, a equation is built up and used accordingly for the conversion. And the input value for LED is printed in terms of volts (ie.of the range 0 to 5 volt) for more easy understanding.
Thus, the output from the potentiometer is taken as the input for the LED which thence controls the voltage supply to LED and the potentiometer can be used for controlling the intensity of the LED.

## CODE
int potentiometer=A2;
int led=6;
float potval;
float ledval;
void setup()
{
  pinMode(potentiometer,INPUT);
  pinMode(led,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  ledval=(255.0/1023.0)*analogRead(potentiometer);
  analogWrite(led,ledval);
  Serial.println(ledval*(5.0/255.0));
  delay(780);
}

## CHALLENGES
The conversion of potentiometer reading to different range caused a difficulty which was overcome building a equation using graph for both the ranges.

## FUTURE IMPROVEMENTS
It can be improves using different LEDs and eperimenting with them using the same potentiometer according to your need. 
