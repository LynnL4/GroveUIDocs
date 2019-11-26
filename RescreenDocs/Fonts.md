# Using different Fonts

This repo describes how to use different free fonts(GNU FreeFonts) included in the library. You can follow this guide to choose your favourite font to display on the Rescreen!

## Available Fonts

There are three main fonts that can be used in this lirbrary including `Serif`, `Sans` and `Mono`. Each font is available with few styles(**bold**, *italic*, oblique) and font sizes from 9pt, 12pt, 18pt and 24pt.

## Using Fonts in Rescreen

To use these fonts easily, it is strongly recommended to copy this `Free_Fonts.h` file from `~/Arduino/libraries/Seeed_LCD_master/examples/320 x 240/All_Free_Fonts_Demo` and attach this header file to your sketch location. This would make referencing the fonts much easier.

To save a lot of typing, each font can  be referenced in the sketch in three ways, either with:

1. Font file name with the & in front, such as: &FreeSansBoldOblique24pt7b.

#### Method 1 Example

 ```cpp
 tft.setFreeFont(&FreeSansBoldOblique24pt7b);
```

2. FF# where # is a number determined by looking at the list in the `Free_Fonts.h` 

#### Method 2 Example

 ```cpp
 tft.setFreeFont(FF32);
```

3. An abbreviation of the file name. Look at the list below to see the abbreviations used.

#### Method 3 Example

```cpp
tft.setFreeFont(FSSBO24)
```

Where the letters mean:

- F = Free font
- M = Mono
- SS = Sans Serif (double S to distinguish is form serif fonts)
- S = Serif
- B = Bold
- O = Oblique (letter O not zero)
- I = Italic
- No =  point size, either 9, 12, 18 or 24

## Example code using different fonts

```cpp
#include"TFT_eSPI.h"
#include"Free_Fonts.h" //include the header file
TFT_eSPI tft;

void setup() {
  tft.begin();
  tft.setRotation(3);
  tft.fillScreen(TFT_BLACK); //Black background
  
  tft.setFreeFont(FSSBO12); //select Free, Sans, Bold, Oblique, 12pt.
  tft.drawString("Sans Serif 12pt",70,80);//prints string at (70,80)

  tft.setFreeFont(FMO12); //select Free, Mono, Oblique, 12pt.
  tft.drawString("Mono 12pt",70,110);//prints string at (70,110)

  tft.setFreeFont(FS12); //select Free, Serif, 12pt.
  tft.drawString("Serif 12pt",70,140);//prints string at (70,140)
  
}
```