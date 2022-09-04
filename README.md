# Pic-Interrupciones

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
