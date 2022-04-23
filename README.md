PROJECT NAME : ATMega328 Amtel Studio LED Blink

DESCRIPTION : First, the clock frequency must be defined (#define F_CPU 16000000UL). This corresponds to the frequency of the oscillator which in this example is 16MHz (16000000Hz). In the other two lines, two libraries must be integrated into the project. IIn the main program, pin 15 (PORTB 1) is defined as the first digital output. Then the rest of the code in the while loop is executed permanently. PORTB1 switches now on, then the controller wait one second before PORTB1 goes off again. Before PORTB1 is switched on again, the controller wait one sec 

CODE:
     #define F_CPU 16000000UL
#include <avr/io.h>
#include <util/delay.h>

int main(void)
{
	DDRB |= (1<<DDB1);
    while (1) 
    {
	PORTB |= (1<<PORTB1);
	_delay_ms(1000);
	PORTB &= ~ (1<<PORTB1);
	_delay_ms(1000);
    }
}
