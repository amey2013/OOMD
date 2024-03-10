
# Unusual Spends

#### Description :

You work at a credit card company and as a value-add they want to start providing alerts to users when their spending in any particular category is higher than usual.
 - Compare the total amount paid for the current month, grouped by category with the previous month 
 - Filter down to the categories for which the user spent at least 50% more this month than last month
 - Compose an e-mail message to the user that lists the categories for which spending was unusually high
#### OOMD Design for the Credit Card Company

## class CreditCardUser
- ### States :
    - private long CardNumber
    - private int month
    - private int year
    - private int cvv
    - public String name
    - public String email
- ### Constructor :
    - CreditCardUser(String name, String email)
- ### Behaviors
    - public String getName()
    - public String getEmail()
  
## class Transaction
- ### States :
    - private enum Category
    - private double amount
    - private Map<Category, Double> amountForEachCategory
- ### Constructor:
    - Transaction(double amount, Map<Category, Double> amountForEachCategory)
- ### Behaviour:
    - public Map<Category, Double> getAmountForEachCategory()
    - public double getAmount()

## class TransactionAnalyzer
- ### States:
    - private List<Transaction> previousMonthTransactions
    - private List<Transaction> currentMonthTransactions
- ### Constructor:
    - TransactionAnalyzer(List<Transaction> previousMonthTransactions, List<Transaction> currentMonthTransactions)       
- ### Behaviour:
    - public void compareTwoTransactions()
    - public double totalAmountForCategory (Transaction.Category category, List<Transaction> transactions)
      
## class EmailNotification
- ### Constructor:
    - EmailNotification(CreditCardUser user, String emailContent)
- ### Behaviour:
    - public void sendEmail(String recipientEmail, String emailContent)
