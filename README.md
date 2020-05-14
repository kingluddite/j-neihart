# Review MySQL
## Instructions
### Clone to your computer
* **note** The `$` below means "Type this in the Terminal". When writing the following Terminal commands, ignore the `$` and type the rest. You will see people represent the Terminal on sites like Stackoverflow with the `$`. Repeat. You don't need to type the `$`. (Don't confuse this `$` with the `$` from jQuery)

`$ git clone `

### Pull down all branches
* Each of the lessons will be contained inside their own branches. You need to pull down these remote branches to your local machine
* Use the following two commands to pull remote branches down to your local machine

* `$ git fetch --all`
* `$ git pull --all`
* `$ git branch -a` (will show you remote branches)

### Checkout branches locally
* To focus more on the code we will just checkout a branch to work on the next lesson
* You have access to the repo after the Catchup so you can play around with the code (the best way to learn how to code is.... to code)
* To checkout a branch just type any of the following to checkout that particular branch
* To see all your branches you can type `$ git branch`, (you won't see a list of the branches until you check each one out individually)
* To break out of the list of branches type `q` for quit


`$ git checkout master`



## Mac/PC?

## What is MySQL?
* What is a relational Database?
    - [WordPress Database Diagram (ER Diagram)](https://codex.wordpress.org/Database_Description)

## WorkBench
* IDE for writing SQL

## Drop a Database
```
-- Drops the animals_db if it exists currently --
DROP DATABASE IF EXISTS animals_db;
```

## Create a Database
```
-- Creates the "animals_db" database --
CREATE DATABASE animals_db;
```

## We need to select the Database we want to manipulate
```
-- Makes it so all of the following code will affect animals_db --
USE animals_db;
```

## How do we create a table?

```
-- Creates the table "people" within animals_db --
CREATE TABLE people (
  -- Makes a string column called "name" which cannot contain null --
  name VARCHAR(30) NOT NULL,
  -- Makes a boolean column called "has_pet" which cannot contain null --
  has_pet BOOLEAN NOT NULL,
  -- Makes a sting column called "pet_name" --
  pet_name VARCHAR(30),
  -- Makes an numeric column called "pet_age" --
  pet_age INTEGER(
```

* Here is a variation of the people table
    - What is AUTO_INCREMENT?
    - What is a PRIMARY KEY?
        + What is a FOREIGN KEY?

```
-- Creates the table "people" within animals_db --
CREATE TABLE people (
  -- Creates a numeric column called "id" which will automatically increment its default value as we create new rows --
  id INTEGER(11) AUTO_INCREMENT NOT NULL,
  -- Makes a string column called "name" which cannot contain null --
  name VARCHAR(30) NOT NULL,
  -- Makes a boolean column called "has_pet" which cannot contain null --
  has_pet BOOLEAN NOT NULL,
  -- Makes a sting column called "pet_name" --
  pet_name VARCHAR(30),
  -- Makes an numeric column called "pet_age" --
  pet_age INTEGER(10),
  -- Sets id as this table's primary key which means all data contained within it will be unique --
  PRIMARY KEY (id)
);
```

## Default values
```
CREATE TABLE programming_languages(
  -- Creates a numeric column called "id" which will automatically increment its default value as we create new rows. --
  id INTEGER(11) AUTO_INCREMENT NOT NULL,
  language VARCHAR(20),
  rating INTEGER(11),
  -- Creates a boolean column called "mastered" which will automatically fill --
  -- with true when a new row is made and the value isn't otherwise defined. --
  mastered BOOLEAN DEFAULT true,
  PRIMARY KEY (id)
);
```


## What is CRUD?

### How do we get data into our Database (The C in CRUD ---- CREATE)
* What is AUTO_INCREMENT?

```
-- Creates new rows containing data in all named columns --
INSERT INTO people (name, has_pet, pet_name, pet_age)
VALUES ("Ahmed", TRUE, "Rockington", 100);

INSERT INTO people (name, has_pet, pet_name, pet_age)
VALUES ("Ahmed", TRUE, "Rockington", 100);

INSERT INTO people (name, has_pet, pet_name, pet_age)
VALUES ("Jacob", TRUE, "Misty", 10);

INSERT INTO people (name, has_pet)
VALUES ("Peter", false);
```

### How do we update data in a table? (The U in CRUD ---- UPDATE)
```
-- Updates the row where the column name is peter --
UPDATE people
SET has_pet = true, pet_name = "Franklin", pet_age = 2
WHERE name = "Peter";
```

### How do we select all people in our table (The R in CRUD ---- READ)
```
SELECT * FROM people;
```

