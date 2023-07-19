/* 
 *  Ex_11 - Conditional
 *  Simple communication through the Serial monitor.
 *  
 */
String rcvString = "";
int BMI = 0;

void setup() {
   Serial.begin(115200); //set up serial library baud rate to 115200
   delay(2000);
   Serial.println("waht is your BMI? ");
}

void loop() {
   if(Serial.available()) { //if number of bytes (characters) available for reading
      Serial.print("Your BMI "); //print I received
      rcvString = Serial.readString();
      BMI= rcvString.toInt(); // read string until newline character
      Serial.print(BMI); 
      Serial.println(" is! ");

      if (BMI > 40) {
        Serial.println("Morbidly Obese");
      }
      else if (BMI > 35) {
        Serial.println("Severely Obese");
      }
       else if (BMI > 30) {
        Serial.println("Moderately Obese");
      }
       else if (BMI > 25) {
        Serial.println("Overweight");
      }
       else if (BMI > 18.5) {
        Serial.println("Normal");
      }
       else if (BMI > 16) {
        Serial.println("underweighted");
      }
       else if (BMI < 16) {
        Serial.println("Severely Undeweight");
      }

      Serial.println("");
      Serial.println("waht is your BMI?");
   }
}
                    
                
