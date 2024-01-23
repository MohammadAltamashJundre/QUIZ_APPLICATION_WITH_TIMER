# QUIZ_APPLICATION_WITH_TIMER
import java.util.Scanner;

public class Quiz {
    public static void main(String[] args) {
        // Store quiz questions along with multiple-choice options and correct answers
        String[][] questions = {
                {"What is the capital of France?", "A. Paris", "B. London", "C. Rome", "D. Madrid", "A"},
                {"Who painted the Mona Lisa?", "A. Vincent van Gogh", "B. Leonardo da Vinci", "C. Pablo Picasso", "D. Michelangelo", "B"},
                {"What is the largest planet in our solar system?", "A. Mars", "B. Jupiter", "C. Earth", "D. Saturn", "B"}
        };

        int score = 0;
        Scanner scanner = new Scanner(System.in);

        // Present one question at a time with multiple-choice options
        for (int i = 0; i < questions.length; i++) {
            System.out.println("Question " + (i + 1) + ":");
            System.out.println(questions[i][0]);
            for (int j = 1; j < questions[i].length - 1; j++) {
                System.out.println(questions[i][j]);
            }

            // Answer Submission: Allow users to select an option and submit their answer within the given time
            System.out.print("Enter your answer (A, B, C, or D): ");
            String answer = scanner.nextLine().toUpperCase();

            // Check if the answer is correct
            if (answer.equals(questions[i][questions[i].length - 1])) {
                score++;
                System.out.println("Correct!");
            } else {
                System.out.println("Incorrect!");
            }

            System.out.println();
        }

        // Display the final score and a summary of correct/incorrect answers
        System.out.println("Quiz completed!");
        System.out.println("Your score: " + score + "/" + questions.length);
    }
}
