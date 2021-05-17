# Ipiales-Marlon_DEBER-3.1_SE
Ipiales Marlon_DEBER 3.1_SE
/*
*CAPITULO III: MODULOS DE COMUNICACIONES
*CODIGO 3.1
*NOMBRE: Marlon Ipiales 
*NOTA: Para que el codigo compile debe estar seleccionado con Arduino Uno WiFi caso contrario si no funcionara seleccionar Arduino Uno 
*/

////////////////////////////////////////MASTER////////////////////////////////////////

#include <Wire.h>   //Libreria I2C
char dato;           //Variable de almacenamiento de datos

void setup() {
  Wire.begin();            //Inicia comunicacion I2C
  Serial.begin(9600);      //Inicia comunicacion serial 
}

void loop() {
  if(Serial.available()>0){     //Verificar que exista datos
    dato=Serial.read();         //Almacena el dato en la variable
    Wire.beginTransmission(4);  //Empieza la comunicacion I2C
    Wire.write(dato);           //Envio dato
    Wire.endTransmission();     //Termina la comunicacion I2C
  }
}
////////////////////////////////////////ESCLAVO 1 ////////////////////////////////////////
#include <Wire.h>      //Libreria I2C
char dato;             //Variable de almacenamiento de dato
const int led1=8;      //led1 en pin8
const int led2=9;      //led1 en pin9
const int led3=10;     //led1 en pin10
int i=0;
int k;

void setup() {
  Wire.begin(4);      //Id de esclavo
  Wire.onReceive(receiveEvent); 
  Serial.begin(9600); 
  pinMode(led1,OUTPUT); //Pin8 como salida
  pinMode(led2,OUTPUT); //Pin9 como salida
  pinMode(led3,OUTPUT); //Pin10 como salida
}

void loop() {

}

void receiveEvent(int bytes){
  while(Wire.available()){
    dato=Wire.read();
    switch(dato){
      case 'A':

      for(k=0;k<=1;k++){
      digitalWrite(led1,HIGH);   //Envia 5V al pin8
      delay(500);
      digitalWrite(led1,LOW);  //Envia 0V al pin8
      delay(500);
      digitalWrite(led2,HIGH);   //Envia 5V al pin9
      delay(500);
      digitalWrite(led2,LOW);  //Envia 0V al pin9
      delay(500);
      digitalWrite(led3,HIGH);   //Envia 5V al pin10
      delay(500);
      digitalWrite(led3,LOW);  //Envia 0V al pin10
      delay(500);    
    }
      break;

      default: 
      digitalWrite(led1,LOW);
      digitalWrite(led2,LOW);
      digitalWrite(led3,LOW);
      break;
    }
  }
}
////////////////////////////////////////ESCLAVO 2 ////////////////////////////////////////
#include <Wire.h>      //Libreria I2C
char dato;             //Variable de almacenamiento de dato
const int led1=8;      //led1 en pin8
const int led2=9;      //led1 en pin9
const int led3=10;     //led1 en pin10
int i=0;
int k;

void setup() {
  Wire.begin(4);      //Id de esclavo
  Wire.onReceive(receiveEvent); 
  Serial.begin(9600); 
  pinMode(led1,OUTPUT); //Pin8 como salida
  pinMode(led2,OUTPUT); //Pin9 como salida
  pinMode(led3,OUTPUT); //Pin10 como salida
}

void loop() {

}

void receiveEvent(int bytes){
  while(Wire.available()){
    dato=Wire.read();
    switch(dato){
      case 'B':

      for(k=0;k<=1;k++){
      digitalWrite(led1,HIGH);   //Envia 5V al pin8
      delay(500);
      digitalWrite(led1,LOW);  //Envia 0V al pin8
      delay(500);
      digitalWrite(led2,HIGH);   //Envia 5V al pin9
      delay(500);
      digitalWrite(led2,LOW);  //Envia 0V al pin9
      delay(500);
      digitalWrite(led3,HIGH);   //Envia 5V al pin10
      delay(500);
      digitalWrite(led3,LOW);  //Envia 0V al pin10
      delay(500);    
    }
      break;

      default: 
      digitalWrite(led1,LOW);
      digitalWrite(led2,LOW);
      digitalWrite(led3,LOW);
      break;
    }
  }
}
////////////////////////////////////////ESCLAVO 3 ////////////////////////////////////////
#include <Wire.h>      //Libreria I2C
char dato;             //Variable de almacenamiento de dato
const int led1=8;      //led1 en pin8
const int led2=9;      //led1 en pin9
const int led3=10;     //led1 en pin10
int i=0;
int k;

void setup() {
  Wire.begin(4);      //Id de esclavo
  Wire.onReceive(receiveEvent); 
  Serial.begin(9600); 
  pinMode(led1,OUTPUT); //Pin8 como salida
  pinMode(led2,OUTPUT); //Pin9 como salida
  pinMode(led3,OUTPUT); //Pin10 como salida
}

void loop() {

}

void receiveEvent(int bytes){
  while(Wire.available()){
    dato=Wire.read();
    switch(dato){
      case 'C':

      for(k=0;k<=1;k++){
      digitalWrite(led1,HIGH);   //Envia 5V al pin8
      delay(500);
      digitalWrite(led1,LOW);  //Envia 0V al pin8
      delay(500);
      digitalWrite(led2,HIGH);   //Envia 5V al pin9
      delay(500);
      digitalWrite(led2,LOW);  //Envia 0V al pin9
      delay(500);
      digitalWrite(led3,HIGH);   //Envia 5V al pin10
      delay(500);
      digitalWrite(led3,LOW);  //Envia 0V al pin10
      delay(500);    
    }
      break;

      default: 
      digitalWrite(led1,LOW);
      digitalWrite(led2,LOW);
      digitalWrite(led3,LOW);
      break;
    }
  }
}
