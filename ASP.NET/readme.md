# ASP.Net MVC

- [how to add a controller][add-control]
- how to add a view
- how to connect entity framework
- how to use linq properly
- how to link a view to a controller
- [where to create DBContext][create-dbc]

## Migrations
- [how to create a migration][create-mig]

[create-mig]:#how-to-create-a-migration
[create-dbc]:#where-to-create-dbcontext
[add-control]:#how-to-add-a-controller
[home]:#aspnet-mvc

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
