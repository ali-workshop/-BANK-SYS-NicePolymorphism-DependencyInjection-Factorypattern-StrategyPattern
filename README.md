
#problem1





designing a part of an advanced banking system using OOP principles
Requirements:
Bank Account Interface (BankAccountInterface):
Define an interface BankAccountInterface with the following methods:
deposit(float $amount): Accepts a deposit amount.
withdraw(float $amount): Allows withdrawal and throws an exception if the balance is insufficient.
getBalance(): Returns the current balance.

Abstract Class BankAccount:
Create an abstract class BankAccount that implements BankAccountInterface.
Include properties for account ID, customer name, and balance.
Implement the deposit() and getBalance() methods.
Leave the withdraw() method abstract.

Concrete Account Classes:
Savings Account (SavingsAccount): Inherits from BankAccount.
Implement withdraw() with a rule that doesn't allow the balance to go below $50.
Checking Account (CheckingAccount): Inherits from BankAccount.
Implement withdraw() with no minimum balance, but charge a fee for every transaction.

Transaction Logger (Static Method):Create a static method in BankAccount named logTransaction which logs any transaction (deposit or withdrawal) with date,
account ID, transaction type, and amount.


Polymorphism:
Demonstrate polymorphism by creating a function that accepts BankAccountInterface and performs a series of deposits and withdrawals, regardless of the account type.




problem2:






Additional Background:
The banking system now needs to integrate a payment processing module capable of handling various payment methods, including Visa, PayPal, and Cash. This module should interact with the existing banking system to process transactions through different payment methods, demonstrating advanced OOP concepts such as Strategy Pattern, Dependency Injection, and Factory Pattern.
Additional Requirements:
Payment Method Interface (PaymentMethodInterface):
Define an interface PaymentMethodInterface with the method:
processPayment(float $amount): Processes the payment of the specified amount.
Concrete Payment Classes:
Visa Payment (VisaPayment): Implements PaymentMethodInterface.
Include properties for card number and CVV.
processPayment() should simulate card validation and payment processing.
PayPal Payment (PayPalPayment): Implements PaymentMethodInterface.
Include properties for PayPal email.
processPayment() should simulate PayPal account validation and payment.
Cash Payment (CashPayment): Implements PaymentMethodInterface.
processPayment() simply acknowledges cash payment.

Payment Processor Class (PaymentProcessor):
Create a class PaymentProcessor with a method executePayment that:Accepts a PaymentMethodInterface and an amount.
Calls processPayment method of the given payment method.

Payment Factory (PaymentFactory):
Implement a Factory Pattern with a class PaymentFactory.
Include a static method getPaymentMethod which takes a type (e.g., 'Visa', 'PayPal', 'Cash') and relevant details, and returns the corresponding PaymentMethodInterface object.

#TODO
Integrating with Bank Accounts:
Modify the BankAccount classes to include a method makePayment which takes a PaymentMethodInterface and an amount, and processes the payment from the account balance.


Advanced Polymorphism and Dependency Injection:
Demonstrate advanced polymorphism by using different payment methods interchangeably through the PaymentMethodInterface.
Use dependency injection in PaymentProcessor to handle various payment methods.
