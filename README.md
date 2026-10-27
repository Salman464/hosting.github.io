# Pizza Directory (PHP + MySQL)

A small PHP and MySQL app for listing pizzas and their ingredients. It is a learning project covering PHP forms, validation, MySQL queries and reusable page templates.

## Features

- **Browse** all pizzas as cards, with their ingredients, ordered by creation time (`index.php`).
- **Add a pizza** with an email, title and comma-separated ingredients (`add.php`). Input is validated before saving: the email must be valid, the title letters only, and ingredients a comma-separated list.
- **View details** for a single pizza, including who created it and when (`details.php`).

## Structure

```
index.php             Lists all pizzas
add.php               Add-a-pizza form with validation
details.php           Single pizza page
Templates/            Shared header.php and footer.php
config/db_connect.php MySQL connection
```

The pages use Materialize CSS classes for layout.

## Setup

1. Install PHP and MySQL, or use XAMPP/MAMP.
2. Create a database and a `pizza` table:

   ```sql
   CREATE TABLE pizza (
     id INT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     email VARCHAR(255) NOT NULL,
     ingredients TEXT NOT NULL,
     created TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

3. Edit `config/db_connect.php` with your own database host, user, password and name.
4. Serve the folder with PHP, for example:

   ```
   php -S localhost:8000
   ```

5. Open http://localhost:8000.

## Notes

This is a practice project, not production code. Before using anything like it for real, switch the queries to prepared statements and keep database credentials out of the repository.
