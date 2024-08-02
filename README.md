# Obsidian_vault
My Personal notes vault integrated with Github

Automating the notes publishing from Obsidian Vault to my personal Github repo.

Initial Configuration:
- Install the Github Publisher plugin
- Add the github details like username, repository and personal access token
- Create the notes with key share = true in the frontmatter
- Open the command palette to upload the active file
- Voila!! Your notes have been pushed to your repo.

Pro Tip: Refer the notes on Obsidian for better UI experience

-- Create the database
CREATE DATABASE Stock;

-- Use the database
USE Stock;

-- Create the assets table
CREATE TABLE assets (
    asset_id INT AUTO_INCREMENT PRIMARY KEY,
    company_name VARCHAR(255) NOT NULL,
    stock_price DECIMAL(10, 2) NOT NULL,
    no_of_stocks_bought INT NOT NULL,
    user_id INT NOT NULL,
    current_price DECIMAL(10, 2) NOT NULL,
    purchase_date DATE NOT NULL
);

-- Insert 20 entries into the assets table
INSERT INTO assets (company_name, stock_price, no_of_stocks_bought, user_id, current_price, purchase_date) VALUES
('Apple', 150.00, 10, 1, 155.00, '2024-01-15'),
('Microsoft', 200.00, 5, 2, 210.00, '2024-02-20'),
('Google', 1800.00, 2, 3, 1850.00, '2024-03-10'),
('Amazon', 3500.00, 1, 4, 3550.00, '2024-04-05'),
('Tesla', 700.00, 8, 5, 720.00, '2024-05-22'),
('Facebook', 250.00, 7, 6, 260.00, '2024-06-17'),
('Netflix', 500.00, 6, 7, 510.00, '2024-07-01'),
('Adobe', 600.00, 4, 8, 610.00, '2024-01-25'),
('Intel', 55.00, 20, 9, 60.00, '2024-02-14'),
('AMD', 85.00, 15, 10, 90.00, '2024-03-09'),
('NVIDIA', 550.00, 3, 11, 560.00, '2024-04-28'),
('Oracle', 75.00, 12, 12, 80.00, '2024-05-14'),
('Cisco', 45.00, 18, 13, 50.00, '2024-06-19'),
('Salesforce', 250.00, 6, 14, 255.00, '2024-07-03'),
('IBM', 140.00, 9, 15, 145.00, '2024-01-19'),
('Snap', 60.00, 14, 16, 65.00, '2024-02-25'),
('Uber', 40.00, 16, 17, 45.00, '2024-03-15'),
('Lyft', 35.00, 17, 18, 40.00, '2024-04-11'),
('Spotify', 150.00, 8, 19, 155.00, '2024-05-30'),
('Square', 240.00, 5, 20, 245.00, '2024-06-25');
