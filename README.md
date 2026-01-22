# DigiShelf Virtual Library Simulation
- An online library simulation that models core library operations by managing book insertions, maintaining a catalog of titles, and tracking a customer database, allowing for the simulation of real-world library processes such as book lending, inventory management, and user interactions.

## Author Info

- Full Name: Ethan E. Lopez, Chantelle Chan, Asiyah Speight, Aidan Tran
- Student ID: 2425516, 2428795, 2357167, 2426311
- Chapman Email: etlopez@chapman.edu, aidtran@chapman.edu, aspeight@chapman.edu, chachan@chapman.edu
- Course Number And Section: CPSC-231-01
- Assignment Or Exercise Number: MP4: Build What You Want

## Usage

1. Compile the Java project files in your preferred IDE or via command line.
2. Run the BookShop main class to start the simulation.
3. Follow the on-screen menu to:
- Browse and add books to a cart
- Remove books from the cart
- Purchase books directly
- Manage customer information
To avoid known runtime exceptions related to Scanner objects, it is recommended to use Option 2 (Purchasing Directly) to run the program through a full transaction.

## Input Format

- User input is provided via console prompts.
- Options are selected using numeric or textual entries based on the menu.
- Book information, customer details, and cart operations are handled internally by the program but interact with the user through prompts.
- Dates and quantities must follow standard numeric or textual formats; for example, dates are managed via LocalDate in YYYY-MM-DD format.

## Implementation Details

- Written in Java, the program uses object-oriented principles with the following core classes:
1. Book – Represents individual book items and their metadata.
2. Customer – Tracks user information and cart contents.
3. Administrator – Handles book creation, catalog management, and administrative operations.
4. BookShop – Main driver class that orchestrates program flow and menu interactions.
- Input is managed using Java Scanner objects; some known issues exist with multiple Scanner instances causing NoSuchElementException in certain cart operations.
- The program uses LocalDate for date handling and calculates elapsed time between dates for inventory or transaction records.
- Itemized actions, including book addition, removal, and purchase, are logged via console output to simulate receipts and transaction tracking.
- The system is designed to demonstrate array/list manipulation, file-like operations (simulated in memory), and interactive console-based user experience.

## Known Errors / Runtime Issues

- Multiple scanner issues in "cart" methods
- Conceptually, our team followed the Scanner structure to the precise detail, however, 'no line found' exceptions still arise when removing books from the customer's carts and clearing them
- Adding books to the cart works, but you'll most likely find another issue that happens even when commenting out the firstRemove() and clearMyCart() methods... it doesn't allow you to purchase because another Scanner issue comes up
- Formatting of this specific exception will often appear as follows:

## Sample Exception Format

Exception in thread "main" java.util.NoSuchElementException: No line found
        at java.util.Scanner.nextLine(Scanner.java:1540)
        at Customer.firstRemove(Customer.java:116)
        at BookShop.main(BookShop.java:318)

- To Avoid Reaching The Above Exception, always choose Option 2 (Purchasing Directly) to run the program all the way through

## Sources

- Worked alongside a Computer Science student, David Sohn, who showed me how to identify a number in a String using (String).matches(".*\\d.*")
- Used geeksforgeeks.org for guidance using the LocalDate package
     https://www.geeksforgeeks.org/java-time-localdate-class-in-java/
- stackoverflow.com was used to find a method to calculate the time elapsed between 2 dates
     https://stackoverflow.com/questions/27005861/calculate-days-between-two-dates-in-java-8
- ChatGPT was used to error check and make corrections within the createBooksToAdd() method inside of the Administrator.java class. 
     Roughly 60-70% of that specific code was originally written by us
- Did some research on Scanner objects to see how we could implement them more neatly
     https://stackoverflow.com/questions/65503259/should-a-scanner-only-be-instantiated-only-once-if-thats-the-case-why-so / 
     https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Java-Scanner-User-Input-example-String-next-int-long-char / 
     https://www.geeksforgeeks.org/passing-scanner-object-as-a-parameter-in-java/
- Comments have been added to the following classes, according to the general understanding of what the class does
