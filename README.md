public class PrimeNumbersUpTo500 {

    public static void main(String[] args) {
        int limit = 500;
        int count = 0;

        System.out.println("Prime numbers between 0 and " + limit + ":");

        for (int number = 0; number <= limit; number++) {
            if (isPrime(number)) {
                System.out.print(number + " ");
                count++;
            }
        }

        System.out.println("\n\nTotal prime numbers found: " + count);
    }

    /**
     * Checks whether a given integer is prime.
     */
    public static boolean isPrime(int n) {
        // 0 and 1 are not prime numbers
        if (n <= 1) {
            return false;
        }

        // 2 is the only even prime number
        if (n == 2) {
            return true;
        }

        // Eliminate all other even numbers
        if (n % 2 == 0) {
            return false;
        }

        // Check odd divisors up to the square root of n
        for (int divisor = 3; divisor * divisor <= n; divisor += 2) {
            if (n % divisor == 0) {
                return false;
            }
        }

        return true;
    }
}
