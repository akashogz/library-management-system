# Library Management System

A console-based Library Management System developed in Java. The application maintains a collection of books and allows a user to view available titles, borrow books, and return them. The project demonstrates core Object-Oriented Programming (OOP) concepts such as encapsulation, class design, and separation of responsibilities.

## Table of Contents

1. [Objectives](#objectives)
2. [Features](#features)
3. [Technologies Used](#technologies-used)
4. [Project Structure](#project-structure)
5. [Prerequisites](#prerequisites)
6. [Installation and Execution](#installation-and-execution)
7. [Usage](#usage)
8. [Sample Output](#sample-output)
9. [Design Overview](#design-overview)
10. [Limitations](#limitations)
11. [Future Enhancements](#future-enhancements)
12. [License](#license)

## Objectives

- Apply Object-Oriented Programming principles in a practical application.
- Model real-world entities (books and a library) as Java classes.
- Manage a dynamic collection of objects using the `ArrayList` data structure.
- Build an interactive, menu-driven console interface with input handling and validation.

## Features

- **Add books:** Register books (title and author) in the library collection.
- **View available books:** Display all books that are currently not borrowed.
- **Borrow a book:** Borrow an available book by specifying its title and author.
- **Return a book:** Return a previously borrowed book to the library.
- **Case-insensitive matching:** Titles, authors, and commands are matched regardless of letter case.
- **Input validation:** Invalid menu choices and unavailable books are handled with clear messages.
- **Graceful exit:** The user can terminate the program at any time using the `exit` command.

## Technologies Used

| Component        | Details                                   |
|------------------|-------------------------------------------|
| Language         | Java                                      |
| Paradigm         | Object-Oriented Programming               |
| Data structure   | `ArrayList<Book>`                         |
| Input handling   | `java.util.Scanner` (console)             |

## Project Structure

```
Library-Management-System/
|-- Book.java                     # Book entity (title, author, borrowed status)
|-- Library.java                  # Library logic (add, display, borrow, return)
|-- LibraryManagementSystem.java  # Entry point and console user interface
|-- LICENSE
|-- README.md
```

| File                           | Responsibility                                                                                      |
|--------------------------------|-----------------------------------------------------------------------------------------------------|
| `Book.java`                    | Represents a single book. Stores the title, author, and borrowed status, and provides methods to borrow and return the book. |
| `Library.java`                 | Manages the collection of books. Implements adding books, listing available books, borrowing, and returning. |
| `LibraryManagementSystem.java` | Contains the `main` method. Handles user interaction through a console menu loop.                  |

## Prerequisites

- Java Development Kit (JDK) 8 or later
- A terminal or command prompt, or a Java IDE such as IntelliJ IDEA, Eclipse, or VS Code

To verify that Java is installed, run:

```bash
java -version
javac -version
```

## Installation and Execution

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd Library-Management-System
   ```

2. Compile the source files:

   ```bash
   javac Book.java Library.java LibraryManagementSystem.java
   ```

3. Run the application:

   ```bash
   java LibraryManagementSystem
   ```

Alternatively, open the project folder in an IDE and run the `LibraryManagementSystem` class.

## Usage

When the program starts, it displays the list of available books and prompts for an action:

| Command  | Description                                                              |
|----------|--------------------------------------------------------------------------|
| `borrow` | Prompts for a book title and author, then borrows the book if available. |
| `return` | Prompts for a book title and author, then returns the book if it was borrowed. |
| `exit`   | Terminates the program.                                                  |

Any other input results in an "Invalid option" message, after which the menu is displayed again.

The library is pre-loaded with the following books:

- Verity by Colleen Hoover
- The Secret by Rhonda Byrne
- Grit by Angela Duckworth

## Sample Output

```
Available Books:
Verity by Colleen Hoover
The Secret by Rhonda Byrne
Grit by Angela Duckworth

Do you want to borrow or return a book?
Type 'borrow' to borrow a book, 'return' to return a book, or 'exit' to quit.
borrow
Enter the title of the book you want to borrow: The Secret
Enter the author of the book you want to borrow: Rhonda Byrne
Book is successfully borrowed: The Secret
You have successfully borrowed 'The Secret' by Rhonda Byrne.

Available Books:
Verity by Colleen Hoover
Grit by Angela Duckworth
```

## Design Overview

- **Encapsulation:** The fields of `Book` and `Library` are private and accessed only through public methods.
- **Separation of concerns:** `Book` models a single item, `Library` manages the collection and business logic, and `LibraryManagementSystem` handles user interaction.
- **Control flow:** The main program runs a loop that displays available books, reads a command, and delegates the operation to the `Library` object until the user chooses to exit.

## Limitations

- Data is stored in memory only; all changes are lost when the program terminates.
- The initial book collection is hard-coded in the `main` method.
- There is no user authentication or record of who borrowed a book.
- Books must be identified by both exact title and author (case-insensitive).

## Future Enhancements

- Search for books by title or author.
- Due dates and fine calculation for overdue books.
- User accounts and borrowing history.
- Persistent storage using file handling or a database (for example, JDBC with MySQL or SQLite).
- A graphical user interface using Java Swing or JavaFX.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
