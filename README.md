# dht1
#include<DHT.h>

#define DHTPIN D5
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup(){
  Serial.begin(9600);
  dht.begin();
  }

void loop(){
  float t = dht.readTemperature();
  float f = dht.readTemperature(true);
  float h = dht.readHumidity();
  delay(2000);

  Serial.print("Temperature Celcius : ");
  Serial.println(t);

  Serial.print("Temperature Farenheit : ");
  Serial.println(f);

  Serial.print("Humidity : ");
  Serial.println(h);
  }
