# News Blog System

## Database Schema
![ER Diagram](diagrams/er-diagram.png)

## System Workflow
![Swimlane Diagram](diagrams/swimlane-diagram.png)

## Database Setup
```sql
CREATE DATABASE news_blog_system;
USE news_blog_system;

CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    age INT,
    contact_number VARCHAR(20),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE news (
    news_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    body TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    user_id INT,
    username VARCHAR(50),
    FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
);

INSERT INTO users (username, email, age, contact_number) VALUES
('rafik_sultan','rafik21@gmail.com',21,'01710000001'),
('amrit_sagor','sagor1@gmail.com',24,'01710000002'),
('jon_gravellion','jongravelli@gmail.com',22,'01710000003'),
('munadi_laskar','munadii@gmail.com',20,'01710000004'),
('rami_khouri','prottoy@gmail.com',23,'01710000005'),
('prottoy_roy','rahim@gmail.com',25,'01710000006'),
('salman_shah','salmankaan@gmail.com',21,'01710000007'),
('pollob_paul','pollobpaul@gmail.com',26,'01710000008'),
('nadia_hossain','nadia@gmail.com',22,'017INSERT INTO users (username, email, age, contact_number)

INSERT INTO news (title, body, user_id, username) VALUES
('Technology Advancements in 2024', 'Recent breakthroughs in AI and machine learning are transforming industries...', 1, 'rafik_sultan'),
('The Future of Remote Work', 'How hybrid work models are becoming the new standard...', 1, 'rafik_sultan'),
('Sustainable Energy Solutions', 'Innovations in renewable energy are accelerating...', 1, 'rafik_sultan'),

('Healthy Eating Habits', 'Nutrition tips for maintaining a balanced diet...', 2, 'amrit_sagor'),
('Mental Health Awareness', 'The importance of mental well-being in modern society...', 2, 'amrit_sagor'),
('Fitness Trends 2024', 'New workout routines gaining popularity...', 2, 'amrit_sagor'),

('Stock Market Update', 'Current trends and predictions for investors...', 3, 'jon_gravelli'),
('Cryptocurrency News', 'Latest developments in the crypto space...', 3, 'jon_gravelli'),
('Personal Finance Tips', 'How to manage your money effectively...', 3, 'jon_gravelli'),

('Travel Destinations 2024', 'Top places to visit this year...', 4, 'munadi_laskar'),
('Digital Marketing Strategies', 'Effective online marketing techniques...', 4, 'munadi_laskar'),
('Social Media Trends', 'What is popular on social platforms...', 4, 'munadi_laskar'),

('AI in Healthcare', 'How artificial intelligence is revolutionizing medicine...', 5, 'rami_khouri'),
('Climate Change Impact', 'Addressing global environmental challenges...', 5, 'rami_khouri'),
('Space Exploration News', 'Latest missions and discoveries...', 5, 'rami_khouri'),

('Recipe Collection', 'Delicious and easy-to-make recipes...', 6, 'prottoy_roy'),
('Home Gardening Tips', 'Growing your own vegetables...', 6, 'prottoy_roy'),
('DIY Home Projects', 'Creative ideas for home improvement...', 6, 'prottoy_roy'),

('Car Maintenance Guide', 'Keeping your vehicle in top condition', 7, 'salman_shah'),
('Electric Vehicles Review', 'Comparing the latest EV models...', 7, 'salman_shah'),
('Road Trip Planning', 'Tips for the perfect road adventure...', 7, 'salman_shah'),

('Book Recommendations', 'Must-read books of the year...', 8, 'pollob_paul'),
('Writing Techniques', 'Improving your writing skills...', 8, 'pollob_paul'),
('Publishing Industry News', 'Trends in book publishing...', 8, 'pollob_paul'),

('Mobile App Development', 'Latest frameworks and tools...', 9, 'nadia_hossain'),
('Cybersecurity Tips', 'Protecting your digital presence...', 9, 'nadia_hossain'),
('Programming Languages', 'Choosing the right language for your project...', 9, 'nadia_hossain'),

('Art Exhibition Reviews', 'Current art shows worth visiting...', 10, 'nadia_hossain'),
('Photography Techniques', 'Improving your photography skills...', 10, 'nadia_hossain'),
('Film Industry Updates', 'News from Hollywood and beyond...', 10, 'nadia_hossain');

