import java.util.Scanner;

public class TemperatureConverter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user for temperature and unit
        System.out.print("Enter temperature value: ");
        double tempValue = scanner.nextDouble();
        System.out.print("Enter unit (C for Celsius, F for Fahrenheit, K for Kelvin): ");
        char unit = scanner.next().toUpperCase().charAt(0);

        // Convert and display results
        switch (unit) {
            case 'C':
                convertFromCelsius(tempValue);
                break;
            case 'F':
                convertFromFahrenheit(tempValue);
                break;
            case 'K':
                convertFromKelvin(tempValue);
                break;
            default:
                System.out.println("Invalid unit entered!");
        }

        scanner.close();
    }

    private static void convertFromCelsius(double celsius) {
        double fahrenheit = (celsius * 9 / 5) + 32;
        double kelvin = celsius + 273.15;
        System.out.printf("Fahrenheit: %.2f°F\nKelvin: %.2fK\n", fahrenheit, kelvin);
    }

    private static void convertFromFahrenheit(double fahrenheit) {
        double celsius = (fahrenheit - 32) * 5 / 9;
        double kelvin = celsius + 273.15;
        System.out.printf("Celsius: %.2f°C\nKelvin: %.2fK\n", celsius, kelvin);
    }

    private static void convertFromKelvin(double kelvin) {
        double celsius = kelvin - 273.15;
        double fahrenheit = (celsius * 9 / 5) + 32;
        System.out.printf("Celsius: %.2f°C\nFahrenheit: %.2f°F\n", celsius, fahrenheit);
    }
}


