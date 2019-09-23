# Temperature

/**
 * Temperature stores a temperature in Fahrenheit, Celsius, and Kelvin scales.
 *
 * @author (Ramiro)
 * @version (1)
 */
public class Temperature {
    private double degreesFahrenheit; // Fahrenheit temperature
    private double degreesCelsius; // Celsius temperature
    private double degreesKelvin; // Kelvin temperature

    /**
     * Default constructor for Temperature sets the default
     * value of the Temperature object to 0.0 degrees
     * Fahrenheit with Celsius and Kelvin equivalents
     */
    public Temperature() {
        this(0.0);
    }

    /**
     * This constructor for Temperature sets the Fahrenheit
     * value to the value from degrees, then calculates
     * equivalent Celsius and Kelvin values using the method
     * setDegreesFahrenheit()
     * 
     * @param degrees degrees Fahrenheit
     */
    public Temperature(double degrees) {
        setDegreesFahrenheit(degrees);
    }

    /**
     * The setDegreesFahrenheit method sets the Fahrenheit temperature
     * and its Celsius and Kelvin equivalents
     * 
     * @param degrees The Fahrenheit value to store 
     */
    public void setDegreesFahrenheit(double degrees) {
        degreesFahrenheit = degrees; // set Fahrenheit value
        degreesCelsius = (degreesFahrenheit - 32.0) * 5.0 / 9.0; // set Celsius
        degreesKelvin = degreesCelsius + 273.15; // set Kelvin value
    }

    /**
     * getDegreesCelsius retrieves the Celsius temperature value
     * 
     * @return a double value containing the Celsius temperature
     */
    public double getDegreesCelsius() {
        return degreesCelsius;
    }

    /**
     * getDegreesKelvin retrieves the Kelvin temperature value
     *
     * @return a double value containing the Kelvin temperature
     */
    public double getDegreesKelvin() {
        return degreesKelvin;
    }
}
import java.util.Scanner;
/**
 * TemperatureDriver runs and tests the Temperature class.
 *
 * @author (Ramiro)
 * @version (1)
 */
public class TemperatureDriver {
    /**
     * main() reads two Fahrenheit temperatures and 
     * displays their Celsius and Kelvin equivalents.
     */
    public static void main(String[] args) {
        double inputTemperature = 0.0;
        Scanner keyboard = new Scanner(System.in); 
        Temperature t1 = new Temperature();
        Temperature t2;
        
        System.out.print("Enter a Fahrenheit temperature: "); 
        inputTemperature = keyboard.nextDouble(); 
        System.out.println("You entered " + inputTemperature + 
                " degrees Fahrenheit"); 
        t1.setDegreesFahrenheit(inputTemperature);
        System.out.println("which is " + t1.getDegreesCelsius() + 
                " degrees Celsius"); 
        System.out.println("and " + t1.getDegreesKelvin() + 
                " degrees Kelvin.");
        System.out.print("Enter another Fahrenheit temperature: ");
        inputTemperature = keyboard.nextDouble();
        System.out.println("You entered " + inputTemperature + 
                " degrees Fahrenheit");
        t2 = new Temperature(inputTemperature);
        System.out.println("which is " + t2.getDegreesCelsius() + 
                " degrees Celsius");
        System.out.println("and " + t2.getDegreesKelvin() + 
                " degrees Kelvin.");
    }
}

