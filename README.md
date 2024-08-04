# PRODIGY_SD_02
Creating A Gussing Game

import java.util.Random;
import java.util.Scanner;

public class RandomNumberGenerator {
    public static void main(String[] args) {
        try (Scanner sc = new Scanner(System.in)) {
            Random random = new Random();
            int randomIntBounded = random.nextInt(1000); // Random number between 0 and 999
            int count = 0;

            System.out.println("Guess the number between 0 and 999:");

            while (true) {
                System.out.print("Enter your guess: ");

                if (sc.hasNextInt()) {
                    int num = sc.nextInt();
                    count++;

                    if (randomIntBounded == num) {
                        System.out.println("You guessed the correct number!");
                        break;
                    } else if (randomIntBounded > num) {
                        System.out.println("Entered number is smaller. Try again.");
                    } else {
                        System.out.println("Entered number is greater. Try again.");
                    }
                } else {
                    System.out.println("Please enter a valid integer.");
                    sc.next(); // Consume the invalid input
                }
            }

            System.out.println("It took you " + count + " attempts.");
        }
    }
}
