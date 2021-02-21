# CAMP
CAMP (automatic plantation monitoring controller), is a real-time monitoring system of an apartment greenhouse or house without garden, designed for stm32F407VG, since the general idea of ​​the project is to be used in reduced spaces in order to have a home ornamental planting. In this cabin you can control the on and off of the lights, the humidity of the soil, the humidity of the air and the temperature, in addition to being able to save the data on an SD card and view them through the display or via Bluetooth on the cellular.


Software microcontrolador

A la hora de realizar el software del programa se utilizó la aplicación Atollic perteneciente a STM creadora del microcontrolador, y el lenguaje de programación utilizado fue C. 
En cuanto a la estructura del programa se utilizan interrupciones y contadores para poder realizar las tareas de censado, guardado en la SD y transmisión de datos por Bluetooh, en el while principal del sistema se corre el menú que va a ser lo que se muestre en pantalla todo el tiempo de ejecución y por el cual se controlara todo el sistema. 
Mediante el Systick del sistema se controla los tiempos de censado, y la utilización de una librería para el control del RTC se maneja el horario de las luces. Luego mediante interrupciones del sistema se activan el uso de los botones.
Se utiliza un Timer del sistema, que es el Timer2 para poder realizar un delay y así utilizar el sensor DHT22, el control de el modulo SD se realiza mediante SPI, USART2 para el control de la transmisión de datos Bluetooh y el RTC propio del sistema para poder generar el horario.

Librerías

Para el desarrollo del software se utilizaron librerías de terceros que facilitaron la programación y generaron una mayor facilidad a la hora de poder utilizar los periféricos correspondientes
Nombre de la librería	Periférico que controla	Autor
ADC	ADC1	Propia
DHT22	Sensor DHT22	ControllerTech
STM32F4xx	Todos los periféricos de la STM32F407VG	STM
FATDS_SDIO	Tarjeta SD	Uwe Becker
LCD 4x20	Display LCD	Uwe Becker (con adaptación propia, ya que era originalmente para el display de 2x16)
TM-STM32F4 RTC 	Reloj RTC STM32F4	Tilen Majerle

A su vez dichas librerías poseen correlación con otras librerías propias de STM para poder realizar toda la interacción entre los distintos periféricos y capacidades de la placa.
