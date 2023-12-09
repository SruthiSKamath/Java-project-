import java.util.Scanner;
import java.util.Random;

public class TypingGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        String[] words = {"programming", "challenge", "java", "typing", "code", "speed"};
        int totalWords = words.length;
        int correctCharacters = 0;
        int totalCharacters = 0;

        System.out.println("Welcome to the Typing Game!");

        for (String word : words) {
            System.out.print("Type the word: " + word + "\t");
            long startTime = System.currentTimeMillis();
            String userTypedWord = scanner.next();
            long endTime = System.currentTimeMillis();

            totalCharacters += word.length();

            if (word.equals(userTypedWord)) {
                correctCharacters += word.length();
                System.out.println("Correct!");
            } else {
                System.out.println("Incorrect!");
            }

            long elapsedTime = endTime - startTime;
            double minutes = elapsedTime / 60000.0; // convert milliseconds to minutes

            double cpm = correctCharacters / minutes;
            double wpm = (correctCharacters / 5) / minutes; // assuming an average word length of 5 characters

            System.out.println("CPM: " + cpm);
            System.out.println("WPM: " + wpm);
            System.out.println("Accuracy: " + ((double) correctCharacters / totalCharacters) * 100 + "%");

            // Add suggestions based on performance if needed

        }

        scanner.close();
    }
}
