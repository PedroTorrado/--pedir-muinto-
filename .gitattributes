# Auto detect text files and perform LF normalization
* text=auto
#include <Servo.h>

Servo b; //Base servo defined
Servo s; //Shoulder servo defined
Servo e; //Elbow servo defined
Servo w; //Wrist servo defined
Servo h; //Hand servo defined

int count = 1;

int move(int pot, int servo_angle);
int b_pot = A1, b_pot_value, b_servo_angle; //base variables
int s_pot = A2, s_pot_value, s_servo_angle; // shoulder varialbes
int e_pot = A3, e_pot_value, e_servo_angle; //elbow variables
int w_pot = A4, w_pot_value, w_servo_angle; //wrist variables
int h_pot = A5, h_pot_value,h_servo_angle; //hand variables

//variables to turn the analog value into angle output
int min_pot_value = 0; // min value defined by the potentiometer
int max_pot_value = 1024; // max value defined by the potentiometer
int max_servo_angle = 180; // max angle of the servo motor

void setup() {
  Serial.begin(9600);

  b.attach(8);
  pinMode(b_pot, INPUT);
  s.attach(7);
  pinMode(s_pot, INPUT);
  e.attach(6);
  pinMode(e_pot, INPUT);
  w.attach(5);
  pinMode(w_pot, INPUT);
  h.attach(4);
  pinMode(h_pot, INPUT);
}

void loop() {
  Serial.print("b.");
  b_servo_angle = move(b_pot, b_servo_angle);
  b.write(b_servo_angle);

  Serial.print("s.");
  s_servo_angle = move(s_pot, s_servo_angle);
  s.write(s_servo_angle);

  Serial.print("e.");
  e_servo_angle = move(e_pot, e_servo_angle);
  e.write(e_servo_angle);

  Serial.print("w.");
  w_servo_angle = move(w_pot, w_servo_angle);
  w.write(w_servo_angle);

  Serial.print("h.");
  h_servo_angle = move(h_pot, h_servo_angle);
  h.write(h_servo_angle);
  
  Serial.println("___________");
}

int move(int pot, int servo_angle){
	count++;
	int pot_value = analogRead(pot);
  servo_angle = pot_value / ((max_pot_value - min_pot_value) / max_servo_angle);
	Serial.print(pot_value);
  	Serial.print(" - ");
	Serial.println(servo_angle);
  return servo_angle;
}