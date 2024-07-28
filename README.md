import java.util.Scanner;

public class CurrencyConverter {

    // Fixed exchange rates
    private static final double INR_TO_USD_RATE = 0.012; // Example rate: 1 INR = 0.012 USD
    private static final double USD_TO_INR_RATE = 83.33; // Example rate: 1 USD = 83.33 INR

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Currency Converter");
        System.out.println("1. Convert INR to USD");
        System.out.println("2. Convert USD to INR");
        System.out.print("Choose an option (1 or 2): ");
        int option = scanner.nextInt();
        
        if (option == 1) {
            // Convert INR to USD
            System.out.print("Enter amount in INR: ");
            double inrAmount = scanner.nextDouble();
            double usdAmount = convertInrToUsd(inrAmount);
            System.out.printf("Amount in USD: %.2f\n", usdAmount);
        } else if (option == 2) {
            // Convert USD to INR
            System.out.print("Enter amount in USD: ");
            double usdAmount = scanner.nextDouble();
            double inrAmount = convertUsdToInr(usdAmount);
            System.out.printf("Amount in INR: %.2f\n", inrAmount);
        } else {
            System.out.println("Invalid option. Please choose 1 or 2.");
        }

        scanner.close();
    }

    public static double convertInrToUsd(double inr) {
        return inr * INR_TO_USD_RATE;
    }

    public static double convertUsdToInr(double usd) {
        return usd * USD_TO_INR_RATE;
    }
}
