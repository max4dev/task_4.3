# task_4.3


public class Main {

    public static void main(String[] args) {
        Cat whiteCat = new Cat (1, 2, 6); //болеем за whiteCat, если побеждает имееем - true
        Cat blackCat = new Cat(1, 2, 5);
        System.out.println(Cat.fight (whiteCat, blackCat));

    }
}

class Cat {

    private int weight = 0;
    private int age = 0;
    private int strength = 0;
    private int winCounter = 0;
    static int countA = 0;
    static int countB = 0;


    Cat(int weight, int age, int strength) {
        this.weight = weight;
        this.age = age;
        this.strength = strength;
    }
   
   static void comparisonCharacteristic(int a, int b) {  // метод реализующий механизм сравнения внутри одного параметра класса Cat
      
        countA = 0;                                      
        countB = 0;
       if (a == b) {
           countA++;
           countB++;
       } else
           if (a > b) countA++;
            else countB++;
   }

   static boolean fight (Cat cat1, Cat cat2) {
   
        comparisonCharacteristic(cat1.weight, cat2.weight);
        cat1.winCounter += countA;
        cat2.winCounter += countB;

        comparisonCharacteristic(cat1.age, cat2.age);
        cat1.winCounter += countA;
        cat2.winCounter += countB;

        comparisonCharacteristic(cat1.strength, cat2.strength);
        cat1.winCounter += countA;
        cat2.winCounter += countB;

       boolean win = true;
       if (cat1.winCounter == cat2.winCounter) {
            System.out.println("Ничья");
            return win;
        } else if (cat1.winCounter > cat2.winCounter)
            return win;
        return false;
    }
}

