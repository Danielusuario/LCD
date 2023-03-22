# LCD
![220543090-d59d5918-7afb-4131-bcb9-0680bd0aa362](https://user-images.githubusercontent.com/124211806/223567171-b4373bf1-5460-4795-a608-9896b2da627d.png)
![image](https://user-images.githubusercontent.com/124211806/224199009-f7ff5df1-1021-43e6-b362-d01c8c8b96f4.png)


<div> <h1 align="center">  LCD historia  </h1> </div>


# Marco teorico 

Una pantalla LCD (Liquid Crystal Display) es un tipo de pantalla plana que utiliza cristales líquidos para producir imágenes y texto. La tecnología LCD se basa en la propiedad de algunos materiales de cambiar la polarización de la luz cuando se someten a un campo eléctrico.

La tecnología de las pantallas LCD se originó en la década de 1960, cuando se descubrió la capacidad de ciertos materiales para cambiar la polarización de la luz. La primera pantalla de cristal líquido se construyó en 1968, pero la tecnología no se utilizó ampliamente hasta la década de 1990.

![lcd-historia](https://user-images.githubusercontent.com/124211806/223572691-4fab4074-73ba-4393-aed5-91dfd404a989.jpg)


En los años 90, las pantallas LCD comenzaron a reemplazar a los monitores CRT (Tubo de Rayos Catódicos) en computadoras y televisores debido a su bajo consumo de energía, tamaño compacto y capacidad para producir imágenes de alta calidad. A medida que la tecnología mejoró, las pantallas LCD se hicieron más populares y se utilizaron en una amplia variedad de dispositivos, desde relojes digitales hasta calculadoras y teléfonos móviles.

En la actualidad, las pantallas LCD se encuentran en una gran cantidad de dispositivos electrónicos, desde televisores hasta consolas de videojuegos y dispositivos móviles. La tecnología ha avanzado significativamente en los últimos años, con la introducción de pantallas LCD con retroiluminación LED y pantallas táctiles capacitivas.

![descarga](https://user-images.githubusercontent.com/124211806/223570252-9d57c68a-cf20-4d6a-909f-f1fec27ad3c6.jpg)

#Raspberry Pi Pico y la pantalla LCD

En cuanto a su implementación en Raspberry Pi Pico, esta placa de desarrollo cuenta con pines GPIO que permiten la conexión de pantallas LCD mediante el uso de librerías específicas, como la librería "RPi.GPIO" y la librería "Adafruit CircuitPython". Estas librerías facilitan la implementación de la pantalla LCD en el proyecto, permitiendo la configuración de pines específicos y la comunicación con la pantalla a través de un protocolo como I2C o SPI.



En conclusión, las pantallas LCD son un tipo de pantalla plana que utiliza cristales líquidos para producir imágenes y texto. La tecnología se originó en la década de 1960, pero no se popularizó hasta la década de 1990 debido a su capacidad para producir imágenes de alta calidad, bajo consumo de energía y tamaño compacto. En Raspberry Pi Pico, se pueden implementar pantallas LCD mediante el uso de librerías específicas que permiten la comunicación con la pantalla a través de pines GPIO.




# esquema de pantalla LCD con conexion a rasperri pi pico

![image](https://user-images.githubusercontent.com/124211806/227034391-a3eef424-ceba-4b41-a186-b2429d10ae80.png)


#Especificaciones y Caracteristicas 

>* Tipo: Pantalla LCD Monocromática
>* Voltaje de alimentación: 3.3V / 5V DC
>* Interfaz: Paralelo 4 y 8 bits
>* 6800 paralelo de 4 bits
>* 6800 paralelo de 8 bits
>* Filas: 2
>* Columnas: 16
>* Controlador o equivalente: AIP31066, HD44780, KS0066 , SPLC780 , ST7066
>* Color disponible:
>* Fondo azul y texto blanco
>* Fondo amarillo y texto negro

# codigo en .ino (Arduino)

```javascript

// LCD1602 and Pi Pico!

#include <LiquidCrystal.h>

LiquidCrystal lcd(12, 11, 10, 9, 8, 7);

void setup() {
  lcd.begin(16, 2);
  lcd.print("LCD");

  lcd.setCursor(2, 1);
  lcd.print("> Pi Pico <");
}

void loop() {
  delay(1); // Adding a delay() here speeds up the simulation
}

```
>

# Codigo Json (JavaScript Object Notation)

```javascript 
{
  "version": 1,
  "author": "Uri Shaked",
  "editor": "wokwi",
  "parts": [
    {
      "type": "wokwi-pi-pico",
      "id": "pico",
      "top": 123.67,
      "left": 135.97,
      "rotate": 90,
      "hide": false,
      "attrs": { "env": "arduino-community" }
    },
    {
      "type": "wokwi-lcd1602",
      "id": "lcd",
      "top": -17.85,
      "left": 22.03,
      "rotate": 0,
      "hide": false,
      "attrs": {}
    },
    {
      "type": "wokwi-resistor",
      "id": "r1",
      "top": 114.8,
      "left": 226.31,
      "rotate": 0,
      "hide": false,
      "attrs": { "value": "220" }
    }
  ],
  "connections": [
    [ "pico:GND.1", "lcd:VSS", "black", [ "v-51", "*", "h0", "v18" ] ],
    [ "pico:GND.1", "lcd:K", "black", [ "v-51", "*", "h0", "v18" ] ],
    [ "pico:GND.1", "lcd:RW", "black", [ "v-51", "*", "h0", "v18" ] ],
    [ "pico:VSYS", "lcd:VDD", "red", [ "v16", "h-16" ] ],
    [ "pico:VSYS", "r1:2", "red", [ "v16", "h0" ] ],
    [ "r1:1", "lcd:A", "pink", [] ],
    [ "pico:GP12", "lcd:RS", "blue", [ "v-16", "*", "h0", "v20" ] ],
    [ "pico:GP11", "lcd:E", "purple", [ "v-20", "*", "h0", "v20" ] ],
    [ "pico:GP10", "lcd:D4", "green", [ "v-24", "*", "h0", "v20" ] ],
    [ "pico:GP9", "lcd:D5", "brown", [ "v-28", "*", "h0", "v20" ] ],
    [ "pico:GP8", "lcd:D6", "gold", [ "v-32", "*", "h0", "v20" ] ],
    [ "pico:GP7", "lcd:D7", "gray", [ "v-36", "*", "h0", "v20" ] ]
  ]
}

```


# Funcionamiento en Wokwi 

![image](https://user-images.githubusercontent.com/124211806/227040657-aa2183c0-3ab4-4adb-acc6-0531a6eb5265.png)

> # Link de proyecto en wokwi
> https://wokwi.com/projects/297323005822894602

# Bibliografia 
> https://www.um.es/docencia/barzana/DIVULGACION/ELECTRONICA/LCD-historia.html#:~:text=Paneles%20LCD&text=En%20el%20a%C3%B1o%201964%20en,t%C3%A9cnica%20en%20aquel%20entonces%20revolucionaria.

> https://visualled.com/pantallas-led-info/pequena-historia-del-lcd/


