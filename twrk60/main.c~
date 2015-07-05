/*
 * File: main.c
 *
 * Copyright (c) karibe 2015, karfes@gmail.com
 *
 * This program is free software. It comes without any warranty, to
 * the extent permitted by applicable law. You can redistribute it
 * and/or modify it under the terms of the Do What You Want
 * To Public License, Version 2, as published by Sam Hocevar. See
 * http://www.wtfpl.net/ for more details.
 *
 */

#include "main.h"

int main(void){	
	//whether to blink LEDS
	blink=1;

	//initialize system
	SystemInit();

	//clear all interrupts and enable interrupts
	nvic->ICPR[2] |= 1 << (87 & 0x1F); //Clear Pending Interrupts
	nvic->ISER[2] |= 1 << (87 & 0x1F); //Enable Interrupts
	
	//initialize GPIO ports
	gpio_init();

	//Loop forever
	while(1)
	{
		if(blink)

                  toggle_LED1(); delay(); toggle_LED2(); delay(); toggle_LED3(); delay(); toggle_LED4();
                  delayl();
                 // toggle_LED4(); delayl(); toggle_LED3(); delayl(); toggle_LED2(); delayl(); toggle_LED1();
                 
                  //toggle_LED4(); toggle_LED3(); toggle_LED2(); toggle_LED1();
                 //delay();
                 
	}
}

/*
	brief  Silly delay
*/
void delay(void)
{
  volatile unsigned int i,j;

  for(i=0; i<3500; i++)
  {
	for(j=0; j<300; j++)
      __asm__("nop");
  }
}




void delayl(void)
{
  volatile unsigned int i,j;

  for(i=0; i<3500; i++)
  {
	for(j=0; j<300; j++)
      __asm__("nop");
  }
}

