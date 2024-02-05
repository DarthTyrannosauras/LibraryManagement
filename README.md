# LibraryManagement
A WebApp for managing a library. Stack: SQL, Spring, React

## Users:
* **Customer**
A customer is someone who can borrow and return books to the library. There can be multiple customers.

* **Librarian**
A librarian is an admin of sorts for the library. There is only one librarian.

## Actions:
### Customers can do the following actions:
1. Borrow a book from the library.
2. Return a book that they have borrowed.
3. View all available books in the library.
4. Search for specific books by title or author.
5. View their own borrowed books.
6. Add new reviews about books, and view existing reviews about them.
7. Edit/delete their own reviews.
8. Get notified about their membership details, overdue book details, fines if any.
9. Pay fines owing.

### Librarians can perform the following actions:
1. Add a customer upon registration.
2. View  all registered users (customers).
3. Assign books to users.
4. Remove books from users' accounts.
5. Set up notifications for users - when a user has returned a book on time, when a user has gone overdue with a book etc.
5. Manage user account information such as address, phone number etc.
6. Approve/deny requests made by users to add books.
7. Set up notifications for users when certain events occur e.g. a book being returned, a fine being paid.
8. Monitor system health metrics.
9. If a book has bad reviews, the librarian can remove the book from the library and add a user-recommended book.
10. If a book is worn-out, the librarian can swap out the book for a new one.
11. The librarian can also search for books using ISBN numbers.

## Designing Entities:
The database will consist of three main tables - `customers`, `books` and `reviews`. Each table has its own entity class with getters and setters methods.

*  `customer` - This entity represents customers. It has attributes like `customer_id`, `name`, `email`, `password`, `date_of_birth`, `mobile_number`, `email`, `membership_end_date`.
* `book` - This entity represents books.  It has attributes like `title`, `author`, `ISBN`,  `publisher`, `year_published`, `book_condition`, `book_popularity`, `status`.
* `books_currently_borrowed` - This entity will contain the attributes regarding books borrowed currently, like `customer_id`, `book_id`, `borrowed_date`, `return_date`.
* `books_read` - This entity will contain the attributes regarding books read, like `customer_id`, `book_id`, `borrowed_date`, `return_date`.
* `reviews` - This entity will contain the attributes regarding  the review itself like `book_id`, `customer_id`, `rating`, `content`, `date_of_review`.


## System design:
The app will use JWT tokens for authentication and authorization. The frontend will make API calls to the backend server which will interact with a MySQL database using Hibernate ORM and handle these requests using RESTful principles.
