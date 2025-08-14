# MentorBit-PoteRueda

Esta librería está diseñada para que puedas obtener fácilmente el valor analógico del módulo de **potenciómetro de rueda**, conectando tu placa MentorBit mediante un **puerto analógico-digital** y un conector JST de 4 pines.

Si estás empezando en el mundo de la electrónica, ¡no te preocupes! MentorBit está pensado para que aprender sea fácil y divertido. Esta placa ya incluye un montón de componentes (LEDs, pulsadores, pantallas, etc.) y utiliza conectores especiales (JST) para que puedas añadir nuevos sensores y módulos sin tener que pelearte con un montón de cables. Pásate por nuestra web para saber más de MentorBit y nuestros productos [pinchando aquí](https://digitalcodesign.com/).

![Render del MentorBit módulo de potenciómetro de rueda.](https://github.com/DigitalCodesign/MentorBit-PoteRueda/blob/main/assets/PoteRueda.png)

Con esta librería, podrás obtener el valor analógico del potenciómetro para usarlo como control de entrada en tus proyectos.

---

## Descripción

### ¿Qué es un potenciómetro de rueda?

Un potenciómetro de rueda es un componente que varía su resistencia dependiendo de la posición de giro de una rueda. Es muy útil para:

- Controlar velocidad, brillo o volumen.
- Ajustar valores en tiempo real.
- Crear interfaces físicas para proyectos educativos e interactivos.

---

### ¿Qué hace esta librería?

La librería **MentorBit-PoteRueda** permite:

- Inicializar el módulo de potenciómetro.
- Leer su valor analógico de forma sencilla.

---

### ¿Qué puedes construir con este módulo?

- Controladores de velocidad, brillo o volumen.
- Interfaces físicas para robots o dispositivos educativos.
- Paneles de control interactivos.
- Proyectos donde necesites entradas de tipo rueda para ajustes precisos.

---

## Cómo empezar

### 1. **Conexión del Módulo**

Conecta el módulo de potenciómetro de rueda a uno de los **puertos analógico-digital** con conector JST de 4 pines en la sección "Puertos para Módulos" de la placa MentorBit. Este módulo utiliza la lectura analógica para determinar la posición de la rueda.

### 2. **Instalación de la Librería**

- Abre tu entorno de programación IDE de Arduino.
- Ve al menú *Programa -> Incluir Librería -> Administrar Librerías...*
- En el buscador, escribe ***MentorBit-PoteRueda*** y haz clic en "Instalar".

![Ejemplo de búsqueda en el gestor de librerías del IDE de Arduino.](https://github.com/DigitalCodesign/MentorBit-PoteRueda/blob/main/assets/library_instalation_example.png)

---

## Ejemplo Básico: Leer valor del potenciómetro

Este ejemplo lee el valor analógico del potenciómetro y lo imprime por el monitor serie.

```cpp
// Se incluye la libreria MentorBitPoteRueda
#include <MentorBitPoteRueda.h>

// Se definen los pines a los que esta conectado el modulo de potenciometro
#define Pin_Potenciometro A4
#define Pin_Led 24

// Se crea el objeto potenciometro
MentorBitPoteRueda potenciometro(Pin_Potenciometro, Pin_Led);

void setup() {
    // Inicializamos el monitor seerial a una velocidad de 9600 baudios
    Serial.begin(9600);
}

void loop() {

    // Enviamos por monitor serial el valor de lectura del potenciometro
    Serial.println("Valor del potenciometro: " + String(potenciometro.obtenerLectura()));

    // Ponemos un pequeño delay para evitar llenar el monitor serial de mensajes
    delay(1000);
}
```

---

## Funciones Principales

- `uint16_t obtenerLectura()`  
  Devuelve el valor analógico leído del potenciómetro.

- `void encenderLed(bool value)`  
  Enciende o apaga el led integrado en la palca del módulo en función del valor recibido (true o false).

---

## Recursos Adicionales

- [Web del fabricante](https://digitalcodesign.com/)
- [Tienda Online de Canarias](https://canarias.digitalcodesign.com/shop)
- [Tienda Online de Península](https://digitalcodesign.com/shop)
- [Web Oficial de MentorBit](https://digitalcodesign.com/mentorbit)
- [Web Oficial del Módulo Potenciómetro de Rueda](https://canarias.digitalcodesign.com/shop/00038874-mentorbit-modulo-de-potenciometro-de-rueda-8118?category=226&order=create_date+desc#attr=)
- [Manual de usuario del Módulo](https://drive.google.com/file/d/10pd2Kjo4I3TvrUrykTeTu_1VUUFJpEJq/view?usp=drive_link)
- [Modelo 3D del Módulo en formato .STEP](https://drive.google.com/file/d/16xWiYqsKtsw9K8Yrt2Mj0SjsGPkYStNZ/view?usp=drive_link)
