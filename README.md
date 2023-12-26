# Waste_Segregation

arduino
const int irSensorPin = 2;            // Digital pin for IR sensor
const int moistureSensorPin = A0;    // Analog pin for moisture sensor

void setup() {
  Serial.begin(9600); // Initialize serial communication
  pinMode(irSensorPin, INPUT);
}

void loop() {
  int irValue = digitalRead(irSensorPin);
  int moistureValue = analogRead(moistureSensorPin);

  if (irValue == LOW) {
    Serial.println("Dry waste detected");
    // Add your action for dry waste
  } else {
    Serial.println("Wet waste detected");
    // Add your action for wet waste
  }

  // You can also check moisture levels for more precision
  if (moistureValue > 500) {
    Serial.println("High moisture content - Wet waste");
  } else {
    Serial.println("Low moisture content - Dry waste");
  }

  delay(1000); // Adjust delay based on your application
}
