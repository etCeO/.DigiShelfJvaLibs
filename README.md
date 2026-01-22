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

- Multiple Scanner issues arise in the “cart” methods (firstRemove() and clearMyCart()), leading to NoSuchElementException.
- Adding books to the cart works, but certain removal or clearing operations may fail due to these Scanner issues.
- Recommended workaround: use Option 2 (Purchasing Directly) to complete transactions without triggering Scanner exceptions.

## Sample exception format:

Exception in thread "main" java.util.NoSuchElementException: No line found
        at java.util.Scanner.nextLine(Scanner.java:1540)
        at Customer.firstRemove(Customer.java:116)
        at BookShop.main(BookShop.java:318)

## Sources

- Collaborated with CS student David Sohn to identify numbers in strings using (String).matches(".*\\d.*").
- GeeksforGeeks articles for guidance on the LocalDate package:
https://www.geeksforgeeks.org/java-time-localdate-class-in-java/
- StackOverflow for calculating elapsed time between two dates in Java 8:
https://stackoverflow.com/questions/27005861/calculate-days-between-two-dates-in-java-8
- ChatGPT assistance for error checking and corrections in createBooksToAdd() (approx. 60–70% of code originally authored by team).
- Research on Java Scanner objects for best practices in single-instance usage and parameter passing:
1. StackOverflow – Scanner instantiation
2. TheServerSide – Scanner user input examples
3. GeeksforGeeks – passing Scanner objects as parameters
