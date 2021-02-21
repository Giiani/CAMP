# CAMP
CAMP (automatic plantation monitoring controller), is a real-time monitoring system of an apartment greenhouse or house without garden, designed for stm32F407VG, since the general idea of ​​the project is to be used in reduced spaces in order to have a home ornamental planting. In this cabin you can control the on and off of the lights, the humidity of the soil, the humidity of the air and the temperature, in addition to being able to save the data on an SD card and view them through the display or via Bluetooth on the cellular.

Microcontroller software

When creating the program software, the Atollic application belonging to STM, which created the microcontroller, was used, and the programming language used was C. As for the structure of the program, interrupts and counters are used to perform the census tasks, saved in the SD and data transmission by Bluetooh, in the main while of the system the menu that will be what is shown on the screen all the execution time and by which the whole system will be controlled. By means of the Systick of the system, the census times are controlled, and the use of a library for the control of the RTC controls the schedule of the lights. Then by system interrupts the use of the buttons is activated. A system Timer is used, which is Timer2 to be able to perform a delay and thus use the DHT22 sensor, the control of the SD module is carried out through SPI, USART2 to control the transmission of Bluetooh data and the system's own RTC to be able to generate the schedule.

Bookstores

For the software development, third-party libraries were used that facilitated programming and made it easier to use the corresponding peripherals.
Name of the library| Peripheral that controls |Author
ADC                |ADC1                      |Own
DHT22 Sensor       |DHT22                     |ControllerTech
STM32F4xx          |Peripherals of STM32F407VG|STM
FATDS_SDIO         |SD card                   |Uwe Becker
LCD 4x20           |LCD display               |Uwe Becker  (with own adaptation, since it was originally for the 2x16 display)
TM-STM32F4 RTC     |RTC clock STM32F4         |Tilen Majerle

In turn, these libraries have correlation with other STM libraries in order to carry out all the interaction between the different peripherals and capacities of the board.




*Spanish*
Software microcontrolador

A la hora de realizar el software del programa se utilizó la aplicación Atollic perteneciente a STM creadora del microcontrolador, y el lenguaje de programación utilizado fue C. 
En cuanto a la estructura del programa se utilizan interrupciones y contadores para poder realizar las tareas de censado, guardado en la SD y transmisión de datos por Bluetooh, en el while principal del sistema se corre el menú que va a ser lo que se muestre en pantalla todo el tiempo de ejecución y por el cual se controlara todo el sistema. 
Mediante el Systick del sistema se controla los tiempos de censado, y la utilización de una librería para el control del RTC se maneja el horario de las luces. Luego mediante interrupciones del sistema se activan el uso de los botones.
Se utiliza un Timer del sistema, que es el Timer2 para poder realizar un delay y así utilizar el sensor DHT22, el control de el modulo SD se realiza mediante SPI, USART2 para el control de la transmisión de datos Bluetooh y el RTC propio del sistema para poder generar el horario.

Librerías

Para el desarrollo del software se utilizaron librerías de terceros que facilitaron la programación y generaron una mayor facilidad a la hora de poder utilizar los periféricos correspondientes
Nombre de la librería |Periférico que controla	|Autor
ADC	                  |ADC1	                    |Propia
DHT22	                |Sensor DHT22	            |ControllerTech
STM32F4xx             |Periféricos STM32F407VG	|STM
FATDS_SDIO	          |Tarjeta SD	              |Uwe Becker
LCD 4x20	            |Display LCD	            |Uwe Becker (con adaptación propia, ya que era originalmente para el display de 2x16)
TM-STM32F4 RTC 	      |Reloj RTC STM32F4	      |Tilen Majerle

A su vez dichas librerías poseen correlación con otras librerías propias de STM para poder realizar toda la interacción entre los distintos periféricos y capacidades de la placa.
