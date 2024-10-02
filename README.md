Library Management Web Application

A local library needed a web application to streamline their operations. This system helps librarians track books, manage members, monitor transactions, and oversee the rental of books. The system is designed for ease of use, assuming the app will only be accessed by the librarian (no need for sessions or roles).
Features
General Overview:

The Library Management System provides the following functionalities:

    Book Management: Track available books, add new books, edit details, and manage stock.
    Member Management: Register library members, update their information, and monitor their outstanding debts.
    Transaction Management: Issue books to members, manage book returns, and calculate rental fees.
    Search Books: Easily search for books by title or author.
    Fee Management: Charge rental fees and ensure no member's debt exceeds KES 500.

Installation
Requirements:

    Frappe Framework: This app is built using the Frappe Framework. Ensure you have Frappe installed.
    Bench: Make sure you have a working Bench environment.

Steps:

    Clone the Repository:

    bash

git clone https://github.com/your-username/library-management.git
cd library-management

Install the Application:

vbnet

bench get-app library_management /path/to/library-management
bench install-app library_management

Start Bench:

sql

    bench start

    Navigate to the App: Open your browser and navigate to http://localhost:8000.

Modules
1. Books Module

The Books module allows the librarian to maintain and manage books and their stock.

    Fields:
        Title
        Author
        Stock
        Rent Fee
        Image
        

    Features:
        Add, update, and delete books.
        Search for books by title or author (via the search_books method).

    Screenshots:
    images/creating newbooks.png

2. Members Module

The Members module allows for the management of library members.

    Fields:
        Name
        Email
        Phone Number
        Outstanding Debt (Automatically updated)

    Features:
        Add, update, and delete members.
        Track outstanding debts and ensure no member exceeds KES 500 in debt.

    Screenshots:
    images/member.png
    

3. Transactions Module

The Transactions module handles book lending and returning, as well as the associated rental fees.

    Fields:
        Book ID
        Member ID
        Issue Date
        Return Date
        Fee (Automatically calculated)

    Features:
        Issue a book to a member.
        Track book returns and calculate rental fees.
        Automatically update stock and member debt upon returns.

    Screenshimages/trasactionform.pngots:
    
Use Cases
1. CRUD Operations for Books and Members

Librarians can perform all CRUD (Create, Read, Update, Delete) operations for books and members.

    To add a book, navigate to the Books module and click on "New Book". Enter the required fields and save.

    To register a member, navigate to the Members module and click on "New Member". Enter the member's details and save.

2. Issue a Book to a Member

    Navigate to the Transactions module.
    Select the member and the book they want to borrow.
    Set the issue date and save the transaction. The system will reduce the book's stock accordingly.

3. Book Return and Rent Fee Calculation

    When a member returns a book, navigate to the Transactions module.
    Locate the transaction, set the return date, and the system will automatically calculate the rent fee based on the days the book was held.

4. Ensure Member Debt Doesn't Exceed KES 500

    The system automatically updates member debts after a return. If a member's debt exceeds KES 500, the system will prevent issuing new books to that member.

5. Search for a Book by Name or Author

    Using the search feature, librarians can look up books by title or author.

6. Charge Rent Fees

    Fees are charged based on the duration the book is borrowed. The longer a book is held, the higher the fee, which is calculated upon return.
