# Creating a SQL Server Database Project Using Visual Studio 2022

Welcome to this guide on setting up a SQL Server Database Project using Visual Studio 2022. In this tutorial, we'll explore the SQL Server Database Project template provided by Visual Studio, covering the following key aspects:

1. Introduction to the SQL Server Database Project.
2. Creating a new SQL Server Database Project.
3. Importing a database schema from various sources such as an existing database, a .sql script file, or a Data-tier application (.bacpac) into the project.
4. Publishing the project to create a new database in SQL Server.

## Why SQL Server Database Project?

While there are numerous tools in the market for comparing databases, many of them come with a hefty price tag. However, this guide focuses on the SQL Server Database Project available in Visual Studio, which is not only powerful but also free of charge.

## Prerequisites

Ensure you have the following installed on your system:

- Visual Studio 2022
- Microsoft SQL Server 2022 Developer Edition (64-bit)

## Getting Started

### Create a New SQL Server Database Project

1. Open Visual Studio and click on "Create new project."

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/e14c8495-ec8f-443a-bec0-6811b6c4d3a4)


2. Follow the prompts to select the location, project name, and click "Create."

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/1c233bb3-b780-47dd-96eb-9a4e88b46f7f)


 # Importing Database Schema and Publishing with SQL Server Database Project

In this section, we will explore how to import a database schema into your SQL Server Database Project from an existing database using Visual Studio. Additionally, we will cover the process of publishing the project to create a new database in SQL Server.

## Importing Database Schema

1. Right-click on the project and select "Import." Three options will be presented: Data-Tier Application (.dacpac), Database, Script (.sql). Choose the "Database" option for importing from an MS SQL database.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/42ea6dd3-e05b-45ca-add7-54beffcfe15e)

2. A screen will appear to provide a connection string. Set up your connection string and click "Start" to initiate the import process.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/c45829c7-f982-4080-8e19-1bc3f51fd5e0)


3. The progress window will display as the import proceeds.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/4a42ec42-ddb4-4c30-8a4d-e8d957450a96)

   
   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/425635c0-665e-4a70-96fd-70097452dd80)

4. After completion, your project will contain tables, views, and stored procedures from the imported database (e.g., Northwind database).

  ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/915e2327-b67a-4c0f-8977-a347254e6df4)


## Publishing to Create a New Database in SQL Server

1. Right-click on the project and select the "Publish" option. Provide connection details, including server name, authentication type, and credentials.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/e3256836-37a2-4390-898d-ab8222dc577d)

2. Specify whether you want to publish as a new database by choosing the default database or selecting a specific database.

3. Click "Publish" to create the new database in SQL Server.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/05bf4fb1-18b3-4517-98e1-604c38797e92)


Explore more advanced options and settings for publishing with additional rules and configurations. Congratulations, you have successfully created and published a SQL Server Database Project! Now you can seamlessly manage your database development within your solution.

## Automatic Publishing Configuration

Simplify the deployment process of your SQL Server Database Project by configuring automatic publishing. Follow these steps:

1. Right-click on your project and select "Properties." Navigate to the "Build Events" section.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/da384715-a890-4b30-8b58-bb22af2719b7)


2. In the build events, insert the following command:
   ```bash
   "C:\Program Files\Microsoft SQL Server\160\DAC\bin\sqlpackage.exe" /Action:Publish /SourceFile:"<<project name>>.dacpac" /Profile:<<project name>>.publish.xml
   ```
   Note: Replace `<<project name>>` with your actual project name.

3. To create a publish profile, use the following steps:

   - While publishing, click on "Advanced..."
   - Generate a profile file and save it (e.g., `<<project name>>.publish.xml`).
   - Manually place this publish profile file in the project's `bin` folder.

   ![image](https://github.com/UjjwalSud/SQL-Server-Database-Project/assets/6552252/ec768da9-8ddf-4a5f-8533-59a120832314)


Now, every time you build the project, the database will be automatically updated using the specified publish profile. This streamlines the development process, ensuring that changes are seamlessly applied to the target database.

## Downloading sqlpackage.exe

To obtain the `sqlpackage.exe` tool, follow these steps:

1. Visit the official Microsoft download page for `sqlpackage.exe` using the following link: [Download sqlpackage.exe](https://learn.microsoft.com/en-us/sql/tools/sqlpackage/sqlpackage-download?view=sql-server-ver16).

2. On the download page, choose the appropriate version of `sqlpackage.exe` based on your SQL Server environment and requirements.

3. Click on the provided link to start the download process.

By following these steps, you can easily acquire the `sqlpackage.exe` tool and proceed with configuring automatic publishing for your SQL Server Database Project.

## Downloading Northwind database

To obtain the `Northwind` database, follow these steps:

1. Visit the [Microsoft SQL Server Samples GitHub repository](https://github.com/Microsoft/sql-server-samples).

2. Navigate to the "databases" folder.

3. Look for the "northwind-pubs" folder.

4. Click on the "northwind-pubs.bak" file.

5. On the file page, click the "Download" button.

6. Once downloaded, you can restore the database using Microsoft SQL Server Management Studio (SSMS) or any other SQL Server tools.

Note: Make sure you have a compatible version of SQL Server installed to restore and use the Northwind database.
