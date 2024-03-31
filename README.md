# ASP.net MVC Areas
This is ASP.net MVC Areas try project

# What Are MVC Areas?
- Areas allow you to logically separate different parts of your application.
- Each area contains its own set of controllers, views, models, and routes.
- Useful for organizing large applications into smaller functional units.

# Creating an Area:
- Right-click on your ASP.NET MVC project in the Solution Explorer.
- Choose Add > Area….
- Enter the name of the area (e.g., “Admin” or “User”).
- This creates an area folder with the same structure as the default MVC folder structure.

# Defining Controllers and Views in the Area:
- Inside the area folder, you’ll find a Controllers folder and a Views folder.
- Create controllers and views specific to this area within these folders.
- For example, if you created an “Admin” area, create controllers like AdminController and views in the Views/Admin folder.

# Setting Up Routes for the Area:
- Open the AreaRegistration.cs file inside the area folder (e.g., Areas/Admin/AdminAreaRegistration.cs).
- Override the RegisterArea method to define routes for this area.
- Example:
```
public class AdminAreaRegistration : AreaRegistration
{
    public override string AreaName => "Admin";

    public override void RegisterArea(AreaRegistrationContext context)
    {
        context.MapRoute(
            "Admin_default",
            "Admin/{controller}/{action}/{id}",
            new { action = "Index", id = UrlParameter.Optional }
        );
    }
}
```

# Accessing the Area in URLs:
- URLs for the admin area will start with /Admin/Controller/Action.
- For example: /Admin/Users/Index.

# Shared Resources:
- You can share common resources (CSS, scripts, etc.) between areas by placing them in a shared folder (e.g., SharedResources).