# ASP.Net MVC

- [how to add a controller][add-control]
- how to add a view
- how to connect entity framework
- how to use linq properly
- how to link a view to a controller
- [where to create DBContext][create-dbc]
- [how to change database name][db-name]
- [how to add the connection string][add-cstring]
- [how to get the Data Source of a SQL Server][get-dsource]

## Migrations
- [how to create a migration][create-mig]

[add-cstring]:#how-to-add-the-connection-string
[db-name]:#how-to-change-database-name
[create-mig]:#how-to-create-a-migration
[create-dbc]:#where-to-create-dbcontext
[add-control]:#how-to-add-a-controller
[home]:#aspnet-mvc
[get-dsource]:#how-to-get-the-data-source-of-a-sql-server



### how to get the data source of a sql server 
<details>
<summary>
View Content
</summary>

1. Go to **SQL Server Object Explorer** 

2. Then go to SQL Server > localdb , right click on localdb and go to properties 

3. In the bottom right corner of the Visual Studio editor the information should display. Then you should scroll to up to 
find the connection string . It would look something like this 

Column | Value
--|-
Connection String | Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=master;Integrated Security=True;Connect Timeout=30;Encrypt=False;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False
Default Database Location | C:\Users\jaxth\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\mssqllocaldb
Is Clustered | False 
... | ...


</details>

[go back :house:][home]


### how to add the connection string 
<details>
<summary>
View Content
</summary>

In the **Web.config** you should be able to see a connection string in that file. If you don't see one
then you add it like this .

```csharp
//make sure you add this below configSections
 <connectionStrings>
    //name = database name            //Data Source = SQL Server
    <add name="WA4DB" connectionString="Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=WA4DB;Integrated Security=True;" 
         providerName="System.Data.SqlClient" />
  </connectionStrings>
```


</details>

[go back :house:][home]


### how to change database name
<details>
<summary>
View Content
</summary>

1. In your context file add the base extension to the constructor with name  of the database you want it to
be called like this

```csharp
namespace WebApplication4.Access_Data
{
    public class WA4DBContext : DbContext
    {
        
        // this is where you add the name of the database to the 
        // constructor
        public WA4DBContext() : base("WA4DB"){

            
       }

        public DbSet<Anime> Anime { get; set; }
        public DbSet<Genre> Genres { get; set; }
        public DbSet<User> Users { get; set; }
        public DbSet<Subscription> Subscriptions { get; set; }
    }
}
```

2. Now, in the Web.config you have to add the **connectionString** anywhere below the **configSections** tags.
make sure you add the name of the database to the name attribute ("name='WAD4B'"). Also in the **connectionString**
make sure you also change the name in the *Initial Catalog* (Initial Catalog=WA4DB)

```csharp
//In Web.config
<configSections>
        <!-- For more information on Entity Framework configuration, visit http://go.microsoft.com/fwlink/?LinkID=237468 -->
        <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
    </configSections>
  <connectionStrings>
  //in the add tag make sure you add the name of the database
    <add name="WA4DB" connectionString="Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=WA4DB;Integrated Security=True;" 
         providerName="System.Data.SqlClient" />
  </connectionStrings>

```

3. Now, just enable the migrations in the package manager console 

```
enable-migrations 

add-migration Initial

update-database

```

4. You should see the database in the  **SQL Server Object Explorer** when looking through the SQL Server **>** LocalDB **>** databases.
If you don't see it then that means you did not assign connection string to the right **Data Source** or something else.


</details>

[go back :house:][home]

### how to create a migration
<details>
<summary>
View Content
</summary>

In the package manager console type this

```
enable-migrations
add-migration <insert db name>
update-database
```
</details>

[go back :house:][home]


### where to create DBContext
<details>
<summary>
View Content
</summary>


1. In the **Solutions Explorer** tab, right click  the name of you project and choose Add > New Folder

2. Name the folder **Access Data**, right click on that folder Add > Class. And then name your DBContext file



</details>

[go back :house:][home]




### how to add a controller

<details>
<summary>
View Content
</summary>

**reference**
- [Controller](https://www.tutorialsteacher.com/mvc/mvc-controller)

1. Right click on the controllers folder and go to  Add > Controller

2. In the controller window,  you can assign your controller to whatever feature you
and then click add



</details>

[go back :house:][home]
