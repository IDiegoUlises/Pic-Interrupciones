# Pic 16F887 Interrupciones

<img src="https://github.com/IDiegoUlises/Pic-Interrupciones/blob/main/Images/16f887-Pic.png"  />

* **El Pin INT funciona como una interrupcion externa**
* Vdd: Positivo del microcontrolador
* Vss: Negativo del microcontrolador
* Clkin: Osicilador conectado a negativo
* Clkout: Osicilador conectado a negativo

### Codigo
```c
#include <16f887.h> //Nombre del microcontrolador
#fuses xt,nowdt  //para osciladores de 4 MegaHertz se usa xt para mayores usa hs
#use delay(clock=4M) //Velocidad del oscilador, la "M" signfica mega

#INT_EXT 
void interrupcion() //Interrupcion
{
   output_low(pin_c0); //Apaga el led
   delay_ms(5000); //Espera de 5 segundo
}


void main()
{
   enable_interrupts(GLOBAL); //Activa las interrupciones
   enable_interrupts(INT_EXT); //Elige el pin donde se realizara la interrupccion

      while(true)//Entra en un bucle infinito
      {
         output_high(pin_c0); //Enciende el led
      }
}
```
### Compilar en Css Compiler
<img src="https://github.com/IDiegoUlises/Pic-Interrupciones/blob/main/Images/Codigo-Imagen.png"  />

### Conectar el Pic al Pickit 
<img src="https://github.com/IDiegoUlises/Pic-Interrupciones/blob/main/Images/Pickit3.jpg" width="1000" height="500" />

### Subir el archivo Hex al Pickit 
<img src="https://github.com/IDiegoUlises/Pic-Interrupciones/blob/main/Images/Importar-Hex.png"  />

### Luego subir el programa al microcontrolador con "Write"
<img src="https://github.com/IDiegoUlises/Pic-Interrupciones/blob/main/Images/Write-pickit.png"  />

### Conexion falta
<img src="https://github.com/IDiegoUlises/Pic-Entradas-Analogicas/blob/main/Images/Circuito-En-Fritzing.png" />

### Funcionamiento
![](https://github.com/IDiegoUlises/Pic-Entradas-Analogicas/blob/main/Images/Entradas-Analogicas-Pic.gif)
