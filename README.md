import java.util.Random;
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int randomNumber = random.nextInt(100) + 1;
        int guess = 0;
        int attempts = 0;

        System.out.println("Welcome to the Number Guessing Game!\nI have selected a number between 1 and 100.\nTry to guess it! Type 'quit' to exit the game at any time.");

        while (true) {
            System.out.println("Enter your guess: ");

            if (scanner.hasNextInt()) {
                guess = scanner.nextInt();
                attempts++;

                if (guess < randomNumber) {
                    System.out.println("Your guess is too low!");
                } else if (guess > randomNumber) {
                    System.out.println("Your guess is too high!");
                } else {
                    System.out.println("Congratulations! You've guessed the number in " + attempts + " attempts!");
                    break;
                }
            } else {
                String line = scanner.next();
                if (line.equals("quit")) {
                    System.out.println("Thank you for playing! The secret number was " + randomNumber);
                    break;
                } else {
                    System.out.println("Error: " + line + " is not a number. Please enter a number.");
                }
            }
        }
    }
}
