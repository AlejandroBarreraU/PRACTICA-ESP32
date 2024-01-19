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
Paso 1. Abrir la terminal de programación y colocar la siguente codigo:
```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
} 
```
Paso 2. Instalar la libreria de DHT sensor library for ESPx como se muestra en la siguente imagen.
![](wokwi  1.png)
Paso 3. Añadir sensor DHT22.
![]()
Paso 4.Hacer la conexion de DHT22 con la ESP32 como se muestra en la siguente imagen.
![]()
### Instrucciones de operación.
1. Iniciar simulador.
2. Visualizar los datos en el monitor serial.
3. Colocar la temperatura y humedad dando doble click al sensor DHT11
## Resultados
Una vez ejecutado, verás los valores dentro del monitor serial como se muestra en la siguente imagen.
## Créditos
Desarrollador por el Ing. Diego Jasso y el Ing. Alejandro Barrera.

