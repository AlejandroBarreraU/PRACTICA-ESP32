# PRACTICA-ESP32
## INTRODUCCION 
En esta práctica se muestra a detalle como programar una ESP32 con el sensor DHT11.
## DESCRIPCIÓN
La Esp32 es utilizada en un entorno de adquision de datos, por lo tanto se utilizará un sensor DTH11 para obtener datos de temperatura y humedad del entorno; Como dato adicional, se utilizara WOKI para asimular esta práctica.
## MATERIAL NECESARIO
+ WOKWI
+ Tarjeta ESP 32
+ Sensor DHT11
## INSTRUCCIONES
### REQUISITOS PREVIOS
Para esta practica necesitamos ingresar al simulador WOKWI.
### INSTRUCCIONES DE PREPARACIÓN DEL ENTORNO
Abrir la terminal de programación y colocar la siguente codigo:
``` #include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
} ```

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
