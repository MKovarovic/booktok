Project Theme: "Book Review Platform"
Your task is to create a mini Book Review Platform where users can log in, add books, and leave reviews. The platform should have:

Backend (Spring Boot) — RESTful endpoints with CRUD operations and secure login.
Frontend (HTML/Thymeleaf) — Basic UI that interacts with backend endpoints.
Advanced concepts — Secure user login (Spring Security) and JPA with relationships.
🛠️ Part 1: Backend Setup
1. Create the data model
User (id, username, password, email)
Book (id, title, author, description)
Review (id, book_id, user_id, reviewText, rating)
👉 Define OneToMany relationship:

User → Reviews (One user can leave many reviews).
Book → Reviews (One book can have many reviews).
2. Implement REST Endpoints
Create the following REST endpoints:

POST /api/register
Accepts JSON { "username": "user", "password": "password", "email": "user@email.com" }
Registers the user securely (password hashed).

POST /api/login
Takes JSON credentials and returns a token (JWT or session).

POST /api/books (requires login)
Accepts JSON { "title": "Book Title", "author": "Author Name", "description": "Brief Description" }
Adds a book to the database.

GET /api/books
Returns a list of books in JSON.

POST /api/review/{bookId} (requires login)
Accepts { "reviewText": "Great book!", "rating": 5 }
Links review to the current user and book.

GET /api/reviews/{bookId}
Returns all reviews for the given book.

3. Secure the backend
Use Spring Security to protect the endpoints:
Only logged-in users can add books/reviews.
Use bcrypt for password hashing.
4. Write Unit Tests
Test user registration, login, and book/review creation with Spring Boot Tests.
🖥️ Part 2: Frontend Setup
1. Build a basic HTML UI with Thymeleaf
Create:

Login page — Username, password, login button.
Book list page — Lists all books.
Book details page — Shows book details and reviews, and has a "Leave review" form.
2. Use HTML snippets (fragments)
Create a reusable header.html for navigation.
Create a footer.html with copyright info.
Reuse the snippets across all pages using Thymeleaf.
🎁 Bonus (Optional) — If Time Allows
Add search/filter for books.
Implement star ratings for reviews.
Style with Bootstrap or CSS for a polished look.
📌 Deliverables Checklist
✅ Fully working Spring Boot backend with REST API
✅ Secure login (Spring Security, hashed passwords)
✅ Thymeleaf frontend with reusable snippets
✅ Database setup (H2, PostgreSQL, etc.)
✅ Unit tests for backend logic
✅ A short README with instructions on how to run the project
