package qn1_accounts;

import java.util.ArrayList;
import java.util.List;

public class Customer {
    // Private attribute matching the '-' symbol
    private String name;
    
    // Aggregation collection container to hold multiple polymorphic Account objects
    private List<Account> accounts;

    public Customer(String name) {
        this.name = name;
        this.accounts = new ArrayList<>();
    }

    // Public method to add an account to the list collection
    public void addAccount(Account a) {
        this.accounts.add(a);
    }

    // Traverses all linked accounts to compute the total aggregate worth
    public double totalWorth() {
        double totalBalanceSum = 0.0;
        for (Account acc : this.accounts) {
            totalBalanceSum += acc.getBalance();
        }
        return totalBalanceSum;
    }
}
