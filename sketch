#include <MD_Parola.h>  
#include <MD_MAX72xx.h>
#include <SPI.h>  

const uint16_t WAIT_TIME = 1000;

#define HARDWARE_TYPE MD_MAX72XX::FC16_HW

#define MAX_DEVICES 4  
#define CLK_PIN   13   
#define DATA_PIN  11  
#define CS_PIN    10   

MD_Parola Mx = MD_Parola(HARDWARE_TYPE, CS_PIN, MAX_DEVICES);

void setup()
{
  Mx.begin();         // instruksi untuk memulai 
  Mx.setIntensity(3); // instruksi untuk mengatur intensitas cahaya (0-15)
}

void loop()
{
  Mx.print("ALTOP");  // instruksi untuk menampilkan karakter
  delay(1000);
  Mx.displayClear();
  delay(1000);
}
