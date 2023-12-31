In SQL, a one-to-one relationship refers to a relationship between two tables where each row in the first table is related to exactly one row in the second table, and vice versa. This relationship is typically established using a common key between the tables.

Here's a simple example with two tables: "users" and "user_profiles."

Create the "users" table:

sql
Copy code
CREATE TABLE users (
    user_id INT PRIMARY KEY,
    username VARCHAR(50),
    email VARCHAR(100),
    -- Other user-related columns
);
Create the "user_profiles" table:

sql
Copy code
CREATE TABLE user_profiles (
    profile_id INT PRIMARY KEY,
    user_id INT UNIQUE,
    full_name VARCHAR(100),
    bio TEXT,
    -- Other profile-related columns
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);
In this example:

The "users" table stores basic information about each user, such as user_id, username, and email.

The "user_profiles" table stores additional details specific to each user's profile, like full_name and bio. The user_id column in this table is both a primary key and a foreign key referencing the "users" table.

This setup ensures that each user in the "users" table has a corresponding record in the "user_profiles" table, and each record in the "user_profiles" table is linked to exactly one user in the "users" table. It's a one-to-one relationship because each user has one profile, and each profile is associated with one user.






