https://www.taniarascia.com/node-express-postgresql-heroku/

psql –version //kiem tra vesion postgresql
sudo -i -u postgres // chay postgresql
psql
/////////////////Tao username cho postgresql la postgres; password la 123456
ALTER USER postgres SUPERUSER;
ALTER USER postgres PASSWORD '123456';
ALTER ROLE postgres CREATEDB;
//////////////////Log out of the root user and log in to the newly created user.
\q //logout 
psql -d postgres -U username //login username la postgres
//////////////////Create a books_api database and connect to it.
CREATE DATABASE books_api; //create db
\c books_api //connect db
////////// Connect success “You are now connected to database "books_api" as user "postgres".”
////////// Create a books table with ID, author, and title.

CREATE TABLE books (
  ID SERIAL PRIMARY KEY,
  author VARCHAR(255) NOT NULL,
  title VARCHAR(255) NOT NULL
);
///////////// Insert one entry into the new table.

INSERT INTO books (author, title)
VALUES  ('J.K. Rowling', 'Harry Potter');
///////// select * from books;

mkdir name_project
cd name_project
////// Tao cac file sau ///////////////
touch .env package.json init.sql config.js index.js

////
npm i cors dotenv express pg
npm i -D nodemon
npm start