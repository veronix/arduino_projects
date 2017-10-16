#define WATERPIN 2 // water pump
#define READSOILPIN A0 // moisture sensor


#define MAXDRYNESS 700 // higher number is more dry

#define WATERDELAY 800 // delay between watering (pumping water)
#define WATERPOSTDELAY 5000 // break after continously waater

void setup()
{
  Serial.begin(9600);
  pinMode(READSOILPIN, INPUT);
  pinMode(WATERPIN, OUTPUT);
}

void loop()
{
  int SensorValue = analogRead(READSOILPIN); //take a sample
  Serial.print(SensorValue); 
  Serial.print(" - ");
  
  if(SensorValue >= MAXDRYNESS) // if soil is too dry (over maximum dryness level acceptable)
  {
   // if the soil is too dry start watering for 3/4 a second then
   // wait for WATERDELAY seconds before monitoring again
   Serial.println("Soil dry start watering");
   digitalWrite(WATERPIN, HIGH);
   delay(WATERDELAY);
   digitalWrite(WATERPIN, LOW);
   delay(WATERPOSTDELAY); // break
  }
  
  delay(50);
}