# jornadas-hacklab-2016

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


