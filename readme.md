# SQLite Database Connection with Python

This is a simple Python script demonstrating how to connect to a SQLite database, create a table, insert data into the table, and retrieve data from the table.


This script connects to a SQLite database, creates a `users` table, inserts data into the table, and retrieves data from the table.

## Code Example

```python
import sqlite3

# Connect to SQLite database
conn = sqlite3.connect('example.db')

# Create a cursor object to execute SQL commands
cursor = conn.cursor()

# Create a table
cursor.execute('''CREATE TABLE IF NOT EXISTS users (
                 id INTEGER PRIMARY KEY,
                 name TEXT NOT NULL,
                 age INTEGER
             )''')

# Insert data into the table
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ('John Doe', 30))
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ('Jane Smith', 25))

# Commit changes
conn.commit()

# Retrieve data from the table
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()

# Print retrieved data
for row in rows:
 print(row)

# Close the connection
conn.close()

```


## Prerequisites

- Python 3.x installed on your system
- Basic knowledge of Python programming

## Instructions

1. Clone or download the repository to your local machine.

2. Ensure you have the `sqlite3` module installed. It is included in Python's standard library, so no additional installation is required.

3. Run the `sqlite_python_example.py` script using Python. This script connects to a SQLite database, creates a `users` table, inserts data into the table, and retrieves data from the table.

4. The script will create a SQLite database file named `example.db` in the same directory where the script is located. You can modify the database name or path as per your requirements.

5. Review the code in the `sqlite_python_example.py` file to understand how the SQLite database connection and operations are implemented.

## Files Included

- `sqlite_python_example.py`: Python script demonstrating SQLite database connection, table creation, data insertion, and retrieval.
- `example.db`: SQLite database file created by the script to store data.

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or feature requests, feel free to open an issue or create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
