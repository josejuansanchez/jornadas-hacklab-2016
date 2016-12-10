# III Jornadas HackLab Almería 2016

Recursos usados en la charla **«Experimenta y aprende programando con [NanoPlayBoard][1]»**.  
[III Jornadas HackLab Almería 2016][2]. 10 y 11 de Diciembre en El Ejido (Almería).

## Datos de la charla

* **Título**: Experimenta y aprende programando con [NanoPlayBoard][1].
* **Tipo**: Charla + Taller (Si disponemos de placas suficientes).
* **Descripción larga**: Haremos un recorrido por todos los recursos que hay disponibles para programar la placa [NanoPlayBoard][1]. Veremos algunos ejemplos de uso con diferentes lenguajes de programación como `C++`, `JavaScript`, `Python` o `Java`. También veremos cómo interaccionar con la placa desde un dispositivo `Android` o un navegador web, y por qué no, también haremos algún que otro `NanoPlayBot`.
* **Material necesario**: Proyector, Internet.
* **Fecha posible**: Sábado por la tarde.
* **Duración**: 45 min.
* **Nivel**: Introducción.
* **Conocimientos previos**: Conocimientos básicos de programación.

## NanoPlayBoard API

### Potentiometer

```c++
int read();
int scaleTo(int to_low, int to_high);
```

* `read` (Serial). 
  * Mostrar datos con *Serial Monitor* del Arduino IDE.
  * Conectar por **USB OTG** a la **aplicación Android** y mostrar los datos en el *Terminal*.
* `read` (Bluetooth). 
  * Conectar por **Bluetooth** con la **aplicación Android** y mostrar los datos en el *Terminal*.
* `scaleTo`

**Nota**: Comentar que en esta versión de la placa `Serial`y `Bluetooth` comparten los pines Rx, Tx, por lo que hay que desconectar el módulo de Bluetooth cada vez que se quiera subir un nuevo sketch a la placa.

### LDR

```c++
int read();
int scaleTo(int to_low, int to_high);
```

* `read` (Serial). 
  * Mostrar datos con *Serial Monitor* del Arduino IDE.
  * Conectar por **USB OTG** a la **aplicación Android** y mostrar los datos en el *Terminal*.
* `read` (Bluetooth). 
  * Conectar por **Bluetooth** con la **aplicación Android** y mostrar los datos en el *Terminal*.
* `scaleTo`

### Cómo enviar datos por el `Serial` a Processing

* Mostrar algunos ejemplos sencillos de cómo podemos usar los valores leídos con los sensores de la placa y manipular algún objeto en Processing con ellos.
* [Referencia](https://github.com/josejuansanchez/NanoPlayBoard-Processing).

### Buzzer

```c++
void playTone(unsigned int frequency);
void playTone(unsigned int frequency, unsigned long duration);
void stopTone();
```

### RGB LED

```c++
void setColor(uint8_t r, uint8_t g, uint8_t b);
void setColor(String color);
void setIntensity(uint8_t intensity);
void on();
void off();
void toggle();
```

### LED Matrix

```c++
void clear();
void print(char symbol);
void print(const byte pattern[5]);
void print(char message[]);
void print(String message);
void setScrollSpeed(uint8_t speed);
void printInLandscape(uint8_t number);
```

### Aplicación Android

* Cargar el sketch para comunicar la aplicación Android con la placa por Bluetooth y enseñar todas las funcionalidades que tiene para los elementos que se han mostrado previamente.
* [Android controlled RGB LED using NanoPlayBoard and Bluetooth](http://nanoplayboard.org/articles/android-controlled-rgb-led-using-nanoplayboard.html).
* [Experimenting with NanoPlayBoard and MQTT](http://nanoplayboard.org/articles/experimenting-with-nanoplayboard-and-mqtt.html).

### Servo

```c++
void to(uint8_t degrees);
```

* [How to calibrate a continuous rotation servo using NanoPlayBoard](http://nanoplayboard.org/articles/how-to-calibrate-a-continuous-servo.html).

### Servos

```c++
void goForward(uint32_t milliseconds);
void goBackward(uint32_t milliseconds);
void goRight(uint32_t milliseconds);
void goLeft(uint32_t milliseconds);
void goForward();
void goBackward();
void goRight();
void goLeft();
void stop();
void setSpeed(uint8_t speed);
```

* [How to build a basic obstacle avoiding robot using NanoPlayBoard](http://nanoplayboard.org/articles/how-to-build-a-basic-obstacle-avoiding-nanoplaybot.html).

### Rotary Encoder

```c++
long getPosition();
```

### Ultrasonic Sensor

```c++
unsigned long pingCm(unsigned int max_cm_distance = 0);
```

* Reference: [NewPing Library](https://bitbucket.org/teckel12/arduino-new-ping/downloads).

### Accelerometer

```c++
float getX();
float getY();
float getZ();
bool isFront();
bool isBack();
bool isUp();
bool isDown();
bool isLeft();
bool isRight();
bool isXTapped();
bool isYTapped();
bool isZTapped();
bool isShaked();
```

### DHT

```c++
float readTemperature(bool S=false, bool force=false);
float readHumidity(bool force=false);
```

* Reference: [DHT Library](https://github.com/adafruit/DHT-sensor-library).

### Button

```c++
bool isPressed();
```

### MIDI

Mostrar cómo podemos convertir la NanoPlayBoard en un controlador MIDI con la ayuda de *hairless-midiserial* y *Garage Band*.

### Firmata

* http://firmata.org
* https://github.com/josejuansanchez/NanoPlayBoard-Firmata
* Mostrar todos los clientes que existen para usar con Firmata: [Johnny-Five](https://github.com/josejuansanchez/NanoPlayBoard-Johnny-Five), [Python](https://github.com/josejuansanchez/NanoPlayBoard-Python-Library), [ScratchX](https://github.com/josejuansanchez/scratch-arduino-extension), etc.

### Node-Red

* https://github.com/josejuansanchez/NanoPlayBoard-Node-Red

### Book

* https://www.gitbook.com/book/josejuansanchez/nanoplayboard/details

[1]: http://nanoplayboard.org
[2]: http://hacklabalmeria.net/2016/12/10/iii-jornadas-hacklab.html
