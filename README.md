# Testdoor

interface Door {
   public void open();
   public void close();   
}
interface LockableDoor extends Door {
   public void lock();
   public void unlock();
}
interface Alarm {
   public boolean isAlarmOn();
   public void turnOnAlarm();
   public void tunrOffAlaram();
}
class CarPart   {
   private int partID;
   private float weight;
   private float cost;
   public void aMethod()   {
      System.out.println( "This is a car part method" );
   }
   // Implement this method
   public float getWeight() {
       return weight;
      

   }
   // Implement this method
   public float getPartID() {
      return partID;

   }
   // Implement this method
   public float getCost() {

      return cost;

   }
}

class CarDoor extends CarPart implements LockableDoor, Alarm 
{
   // Car door has a lock
   private boolean lockFlag = false;
   // Car door has an alarm switch for you to turn on/off alarm
   private boolean alarmFlag = false;
   // Implement this method
   public boolean isAlarmOn() {
       return lockFlag = true;
       
      
   }
   // Implement this method
   public void turnOnAlarm()   {  
       unlock();
       alarmFlag = true;
       System.out.println("Turn on the Alaram"); 
      
   }
   // Implement this method
   public void tunrOffAlaram() {   
       lock();
       alarmFlag = false; 
       System.out.println("Turn off the Alaram");
      
   }
   
   
   // To simulate the situation that you open a car while
   // sitting in the car
   //
   // Step 1: Turn on the alarm
   // Step 2: Unlock the car 
   // Step 3: Display "Look out, opening the door"
   public void open() {
       turnOnAlarm();

       System.out.println("Look out, opening the door");
      
   }
   
   // To simulate the situation that you close a car while
   // sitting in the car
   //
   // Step 1: Display "Look out, closing the door"
   // Step 2: lock the car 
   // Step 3: Turn off the alarm
   public void close() {
       tunrOffAlaram();
    System.out.println("Look out, closing the door");
      
   }
   // Implement this method
   public void lock() { 
        isAlarmOn();
      if (alarmFlag = true){
          System.out.println("unlock the car");
        }
      
   }
   // Implement this method
   public void unlock() { 
       isAlarmOn();
       if (alarmFlag= false){
           System.out.println("lock the car");
       } 

      
   }
}

public class TestDoor {
   public static void main( String[] args ) {
      // I have an sedan car
      CarDoor sedan = new CarDoor();
      
      sedan.open();
      // I close the door
      sedan.close();

      
   }
}
