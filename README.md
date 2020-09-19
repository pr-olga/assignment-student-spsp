# Assignment for Students :eyeglasses:

Build a simple php-Application that gets data from the DB (sample file is in this repo) and displays it.
Finished app must contain:
  1. start page where the articles are listed
  2. separated/single article pages 
Every article on the startpage must be clickable and lead to the separated/single article page.

## Requirements
- all code must be beautified (nice to have: linted), there are many extensions for VS Code, PHPStorm has it out of
  the box
- application must have a clear folder structure
- design is up to you but it has to be readable and accessible (pages for inspiration: dribbble and/or pinterest)
- any transition/animation effects are up to you
- you can add any functional feature to the app (but it is not obligatory)
- you can use any css preprocessor and any task runner (but it is not obligatory)
- attach the screenshot of Chrome Lighthouse analysis to the application (example is in this repo). All the params (perfomance, accessibility, best practices and seo) must show at least 85 points
- please provide a link to the GitHub/GitLab repo and not(!) zipped folder

:sparkles: Goog Luck! :sparkles:

### Hints
- you have to install apache, php and mysql locally. There are several ways to get it: (a) you can install XAMPP (works on all OSs and there are tons of tuts on the internet) or (b) on Linux (Ubuntu and co) you can use cli (probably the fastest way)  

    1. Check if apache installed (`apache2 -v`) or install it. Afterwards, call http://localhost in order to check the status
    ```bash
        sudo apt-get update -y #using the -y option will automatically accept the conditions of the source update
        sudo apt-get install apache2 -y #install apache
        sudo systemctl start apache2.service #start apache
    ```  
    2. Check if mysql is installed and runs (`sudo systemctl status mysql`) or install it
    ```bash
        sudo apt-get install mysql-server -y #install mysql
        sudo systemctl start mysql.service #start mysql
        
        # BEGIN ENTER MYSQL Console
        mysql -u root -p #enter the mysql
        GRANT ALL ON *.* TO 'root'@'localhost' IDENTIFIED BY 'yourpass' WITH GRANT OPTION; # set pass for root
        exit; #leave console
        # END ENTER MYSQL Console
        
        mysql -u root -p < [path/to/to/your/folder]/blog-spsp_db.sql #create db blog-spsp and table articles by importing the file form the repo
    ```

    3. Check if mysql is installed (`php -v`) or install it
    ```bash
        sudo apt-get install php libapache2-mod-php -y #install php
        sudo apt install php-mysqli -y #install mysqli in order to connect to db
        sudo systemctl restart apache2.service #restart apache
    ```
    
    4. Create a new folder named blog-spsp in /var/www/html to store your project files.
    5. Put the file info.php in this folder
    6. Call http://localhost/blog-spsp/info.php in order to see that everythig works (later you can delete it)
    7. Now you can establish connection to DB and start to develop

- for fast debugging put these lines at the beginning of the php-file. The errors will be displayed.
```php
    error_reporting(E_ALL);
    ini_set('display_errors', 1);
```
- If you use XAMPP, you will get phpMyAdmin (https://www.phpmyadmin.net/) installed. Whithout XAMMP you have to install it manually or use cli (probably the fastest way. However, you could get the overview from the attached plain sql in this simple example and, therefore, you do not need any clients) e.g.:
```bash
    mysql -uroot -p #enter mysql 
    use `blog-spsp`;
    select * from `articles`;
```
- Remember to keep the credentials secure (do not commit them).