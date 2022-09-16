# Sensor de Ultrasonido

En esta práctica se presenta el sensor de ultrasonido para diferentes usos.\
Un sensor de ultrasonido puede medir distancia. La distancia puede ser la variable de un volumen de área de base constante o la posición cambiante en el tiempo de un cuerpo.\
A continuación se describen brevemente dos de estos.

### · HC - SR04 ·
Este dispositivo trabaja con valores de tensión típicos de $5 [V]$ y $15 [mA]$ de corriente. El rango de medición es de $2x10^{-2}[m]$ a $4 [m]$, con un error de $3x10^{-3} [m].$
Para poder operar correntamente, no debe ser colocado en áreas menores a $0.5 [m^2].$\
EL funcionamiento comienza con el disparo de un pulso de $10x10^{-6} [s].$ Seguidamente se envía un tren de 8 pulsos de $40 [Hz]$ y se espera el eco. Para evitar que un trigger se lea erróneamente como un eco, el próximo trigger se enviará con $60x10{-3}[s]$ de diferencia.\
El dato de entrada es el tiempo $t$ en ALTO de la respuesta. Conocida la velocidad del sonido para medios libres ideales como $v=343 [m/s]$ se cumple que

<p align="center"> $d =\frac{1}{2} v t$ </p>

### · US-100 Ultrasonic Distance Sensor - 3V or 5V Logic ·
Este dispositivo trabajo con valores de tensión menores al anterior, lo que lo hace funcional al SoC ESP32 cuando no se desea incorporar adaptadores de tensión.\
Trabaja como un HC - SR04, auqnue también puede ser utilizado en modo UART a $9600 \ baudios$ con $0x55$ para recibir 16 bits de respuesta, en milímetros. \
También este sensor mide temperatura, para lo que en modo UART se envía $0x50$ para obtener una medición en grados centígrados.



