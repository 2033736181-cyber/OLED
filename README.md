# OLED
#include <Arduino.h>
#include <U8g2lib.h>
#include <Wire.h>

U8G2_SSD1306_128X64_NONAME_F_HW_I2C u8g2(U8G2_R0, U8X8_PIN_NONE);

void setup(void) {
  u8g2.begin();               
  u8g2.enableUTF8Print();     
}
void loop(void) {
  u8g2.clearBuffer();                     
  u8g2.setFont(u8g2_font_ncenB08_tr);    
  u8g2.drawStr(0, 10, "Hello!");
  u8g2.setFont(u8g2_font_unifont_t_chinese2); 
  u8g2.drawUTF8(0, 30, "你好！");
  u8g2.sendBuffer();                     
  delay(1000);
}
