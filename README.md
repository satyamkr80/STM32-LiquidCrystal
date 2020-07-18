# STM32-LiquidCrystal

This library allows a STM32 ARM microcontroller to control LiquidCrystal displays (LCDs) based on the Hitachi HD44780 (or a compatible) chipset, which is found on most text-based LCDs. This is a part of LiquidCrystal library from Arduino.

## Functionality Supported by this library

* AutoScroll
* Blink
* En/Dis Cursor
* Custom Character
* Display On/Off
* Left/Right Scroll
* Set Cursor position
* Change Text Direction
* Print Integer/Float

#### Change this line as per board/ic you are using
```c
#include "stm32f4xx_hal.h" // change this line accordingl

```
#### How to use ?

* Add both Library file .c and .h in your project and call this line in main ()

```c
LiquidCrystal(GPIOC, GPIO_PIN_8, GPIO_PIN_9, GPIO_PIN_10, GPIO_PIN_11, GPIO_PIN_12, GPIO_PIN_13, GPIO_PIN_14);

```
* Now call print commmand to print text on LCD
```c
setCursor(0,0);    // First Column First Row
LCD_print("hello! World "); // Pass String

```
### Complete code will Look Like this

```c
int main(void)
{ 
  HAL_Init();
  
  SystemClock_Config();

  MX_GPIO_Init();
  MX_TIM2_Init();

LiquidCrystal(GPIOC, GPIO_PIN_8, GPIO_PIN_9, GPIO_PIN_10, GPIO_PIN_11, GPIO_PIN_12, GPIO_PIN_13, GPIO_PIN_14);
 
  while (1)
  {
		setCursor(0,1);  // set Cursor to First col/ First Row
		LCD_print("hello! World "); // Print Text
    LCD_int(10);  // Print Integer Value
		LCD_float(02.00); // Print Float value
    }
    }
```
