# To Do List

#### _An application to get a user tasks up to date. - 06/2019_

#### _By **Uriel Gonzalez**_

## Description

In this application, I used what I learned in the C# and .NET Advanced Databases and Authentication lessons. I worked with SQL, user authentication, joined entities, CRUD methods and databases using migrations.Then I connected the backend application with a many-to-many relationship to the front end user interface created in Core MVC.

## Setup/Installation Requirements

1. Clone this repository:
    ```
    $ git clone https://github.com/Ugonz86/To-Do-List-Final.git
    ```
2. Open the application and restore it
    ```
    $ cd To-Do-List-Final/ToDoList
    ```
    ```
    $ dotnet restore
    ```
3. Log onto MySQL:
    ```
    $ mysql -u root -p epicodus
    ```
4. Create My SQL schema named to_do_list and tables with the following information:
    ```
    > CREATE TABLE `Categories` (`CategoryId` int(11) NOT NULL AUTO_INCREMENT, `Name` longtext, `UserId` varchar(255) DEFAULT         NULL, PRIMARY KEY (`CategoryId`)) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
    
    > CREATE TABLE `CategoryItem` (`CategoryItemId` int(11) NOT NULL AUTO_INCREMENT, `ItemId` int(11) NOT NULL, `CategoryId`         int(11) NOT NULL, PRIMARY KEY (`CategoryItemId`), KEY `IX_CategoryItem_CategoryId` (`CategoryId`), KEY                         `IX_CategoryItem_ItemId` (`ItemId`), CONSTRAINT `FK_CategoryItem_Categories_CategoryId` FOREIGN KEY (`CategoryId`)             REFERENCES `categories` (`CategoryId`) ON DELETE CASCADE, CONSTRAINT `FK_CategoryItem_Items_ItemId` FOREIGN KEY                 (`ItemId`) REFERENCES `items` (`ItemId`) ON DELETE CASCADE) ENGINE=InnoDB AUTO_INCREMENT=16 DEFAULT CHARSET=utf8mb4             COLLATE=utf8mb4_0900_ai_ci;
    
    > CREATE TABLE `Items` (`ItemId` int(11) NOT NULL AUTO_INCREMENT, `Description` longtext, `UserId` varchar(255) DEFAULT           NULL, `CategoryId` int(11) DEFAULT NULL, PRIMARY KEY (`ItemId`), KEY `IX_Items_UserId` (`UserId`)) ENGINE=InnoDB               AUTO_INCREMENT=20 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

## Known Bugs
* No known bugs at this time.

## Technologies Used
* C# / .NET Core
* ASP.NET Core MVC
* Entity Framework Core
* LINQ
* MySQL

## Support and contact details

_Please contact Uriel Gonzalez with questions and comments._

### License

*GNU GPLv3*

Copyright (c) 2019 **_Uriel Gonzalez_**
