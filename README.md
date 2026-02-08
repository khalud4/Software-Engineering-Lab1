# Software-Engineering-Lab1
Lab 1 for Software Engineering course
import java.util.ArrayList;
import java.util.HashMap;
import java.util.Scanner;

public class UniversityFoodOrderingSystem {

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        // Users
        HashMap<String, String> users = new HashMap<>();
        users.put("student1", "1234");

        // Menu
        HashMap<Integer, String> menu = new HashMap<>();
        HashMap<Integer, Integer> prices = new HashMap<>();

        menu.put(1, "Burger");
        prices.put(1, 10);

        menu.put(2, "Pizza");
        prices.put(2, 12);

        menu.put(3, "Coffee");
        prices.put(3, 5);

        // Login
        System.out.print("Enter username: ");
        String username = input.nextLine();

        System.out.print("Enter password: ");
        String password = input.nextLine();

        if (!users.containsKey(username) || !users.get(username).equals(password)) {
            System.out.println("Login failed!");
            return;
        }

        System.out.println("Login successful!");

        // Show menu
        System.out.println("\nFood Menu:");
        for (int key : menu.keySet()) {
            System.out.println(key + ". " + menu.get(key) + " - " + prices.get(key) + " SR");
        }

        // Cart
        ArrayList<Integer> cart = new ArrayList<>();

        System.out.print("\nSelect item number to add to cart: ");
        int choice = input.nextInt();
        cart.add(choice);

        // Order summary
        System.out.println("\nYour Order:");
        int total = 0;
        for (int item : cart) {
            System.out.println(menu.get(item) + " - " + prices.get(item) + " SR");
            total += prices.get(item);
        }

        System.out.println("Total Price: " + total + " SR");
        System.out.println("Order placed successfully!");
    }
}
