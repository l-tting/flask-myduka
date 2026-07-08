*Introduction to Github*
git config --global user.name "Your name"
git config --global user.email "Your email address"
git config --list

*git* - version control software / system that keeps track of changes in your code
*github* - cloud hosting platform / storage for git repositories

*repositories* - a folder in github

Github enables the following
1.have back up for my code
2.collaborate with other developers
3.showcase your work to clients / employers


*Pushing code to Github*
*pushing new code to github for the first time*
1.Initialize git to track my project file
**git init**

2.Add remote origin - connect your local folder to the repo in Github
**git remote add origin https://github.com/l-tting/flask-myduka.git**

3.Adding files to github -> choose files that you want to push to Github
**git add .**

4.Commit -> save a snapshot of your changes before pushing to github along with a relevant message
**git commit -m "My first commit"**

5. **git push origin master** or **git push origin main**


*master & main* -> branches (independent line of development)

MPESA
 -> send money
 -> lipa na mpesa : -> paybill
                    -> pochi la biashara
                    -> till
-> kcb mpesa
-> mshwari


*U* - untracked
*A* - added
*M* - modified





*updating existing code in github*
==> start from step 3 moving onwards



Open up a terminal and run the followinfg commands:
1. pip install flask
2. pip install psycopg2-binary



open sql shell: 
create a new database called flask_myduka;

create database flask_myduka;
\c flask_myduka

CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    buying_price NUMERIC(20, 2) NOT NULL CHECK (buying_price >= 0),
    selling_price NUMERIC(20, 2) NOT NULL CHECK (selling_price >= 0)
);

CREATE TABLE stock (
    id SERIAL PRIMARY KEY,
    pid INTEGER NOT NULL REFERENCES products(id) ON DELETE CASCADE,
    stock_quantity INTEGER NOT NULL CHECK (stock_quantity >= 0),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE sales (
    id SERIAL PRIMARY KEY,
    pid INTEGER NOT NULL REFERENCES products(id) ON DELETE CASCADE,
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    full_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    phone_number VARCHAR(100) NOT NULL,
    password VARCHAR(255) NOT NULL
);

insert into products(name,buying_price,selling_price)values('bread',50,60);


**INTRODUCTION TO PSYCOPG2**
->Psycopg2 is a driver or adapter that is used to connect Python to a Postgres database
->To establish this connection we use a function called *psycopg2.connect()* which 
takes some arguments:
1.host -> where is my database located? -> in your local device(localhost)
2.port -> where exactly in my device is the Postgres service running
3.user - default postgres username
4.password - password attached to the user for login
5.dbname -> name of the database you want to connect to





*localhost -> domain name for ip address 127.0.0.1*
