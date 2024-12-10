# Practica-ESP32-con-DHT22
En este repositorio utilizaremos la ```ESP32``` en un entorno de adquisición de datos, también le conectaremos un sensor ```DTH22``` para que nos muestre periódicamente la temperatura y la humedad; todo esto se hará en el simulador  [WOKWI](https://wokwi.com/).

## Material Necesario
- [WOKWI](https://wokwi.com/)
- Trajeta ESP32
- Senso DTH32


## Instrucciones

### Requisitos Previos

Necesitas abrir la la pagina [WOKWI](https://wokwi.com/).


### Preparación del entorno

1. Ya en la plataforma debes seleccionar la tarjeta que usaremos en este caso seria la  ```ESP32```.
![](https://github.com/AntoniodeJesus19/Practica-ESP32-con-DHT22/blob/main/Captura%20de%20pantalla%202024-12-09%20223637.png?raw=true)

2. Luego bajamos un poco el cursor y en ```Starter Templates``` seleccionamos ESP32.
![](https://github.com/AntoniodeJesus19/Practica-ESP32-con-DHT22/blob/main/Captura%20de%20pantalla%202024-12-09%20224130.png?raw=true)

3. En la terminal de programacion borramos todo y colocamos la siguiente programación:
```
#include "DHTesp.h"


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

4. Instalar la libreria **DHT sensor library for ESPx**.
![](https://github.com/AntoniodeJesus19/Practica-ESP32-con-DHT22/blob/main/Captura%20de%20pantalla%202024-12-09%20225042.png?raw=true)

5. Seleccionamos nuestro sensor en la parte de **Simulacion** en el boton **+** y buscamos **DHT22** le damos click y los conectamos de la siguiente manera.
![](
