This project is a SQL-based Instagram Clone that demonstrates how social media platforms store and manage data such as users, photos, comments, likes, tags, and follows.

It includes database schema design, data insertion, and analytical SQL queries that simulate real-world Instagram-like functionalities.

📂 Project Structure

Database Creation & Tables

users → Stores user details

photos → Stores uploaded photos

comments → Stores user comments on photos

likes → Stores likes made by users on photos

tags → Stores hashtags

photo_tags → Connects photos with hashtags

follows → Stores follower–followee relationships


Data Insertion
Pre-loaded with sample users, photos, tags, likes, and follows.

Queries
Analytical queries to answer questions like:

How many photos does the average user post?

What are the top 5 most used hashtags?

Which users have liked every single photo?

Who won the photo contest with the most likes?

On which days do most users register?

🛠️ Technologies Used

MySQL (or any SQL database)

Sample dataset (generated dummy data)

▶️ How to Run

1. Clone this repository:

git clone https://github.com/your-username/Instagram-Clone-Project.git
cd Instagram-Clone-Project


2. Open MySQL and run the script:

SOURCE instagram_clone.sql;


3. Explore the database using queries provided in the file.

📊 Example Queries

✅ Find average number of photos per user:

SELECT COUNT() / (SELECT COUNT() FROM users) 
AS avg_photos_per_user
FROM photos;

✅ Top 5 hashtags:

SELECT tags.tag_name, COUNT(*) AS usage_count
FROM photo_tags
JOIN tags ON photo_tags.tag_id = tags.id
GROUP BY tags.tag_name
ORDER BY usage_count DESC
LIMIT 5;

✅ Users who liked all photos:

SELECT users.id, users.username
FROM users
JOIN likes ON users.id = likes.user_id
GROUP BY users.id
HAVING COUNT(likes.photo_id) = (SELECT COUNT(*) FROM photos);

🚀 Features

📌 Complete database schema for Instagram-like application

📌 Sample dummy data insertion

📌 Complex SQL queries for analytics and insights

📌 Good practice for SQL interview preparation

📖 Learning Outcomes

By working with this project, you’ll practice:

Designing relational databases

Writing JOIN queries

Using aggregate functions (COUNT, GROUP BY, HAVING)

Applying constraints & relationships

Running real-world analytical queries

🤝 Contributing

Contributions are welcome! If you’d like to improve the queries or add new features, feel free to fork and submit a pull request.

📜 License

This project is for educational purposes only and is not affiliated with Instagram.
