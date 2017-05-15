# **Handling routes in ASP.NET Core**
Creat Model and Controller First.
1. **Convention-based routing**
```
app.UseMvc(routes =>
{
    // Route Sample A
    routes.MapRoute(
      name: "RouteSampleA",
      template: "MyOwnGet",
      defaults: new {
        controller = "Items",
        action = "Get"
      }
    );
    
    // Route Sample B
    routes.MapRoute(
      name: "RouteSampleB",
      template: "MyOwnPost",
      defaults: new {
        controller = "Items",
        action = "Post"
      }
    );
});
```

2. **Attribute-based routing**


featuring it either at the controller level:
```
[Route("api/[controller]")]
public class ItemsController : Controller
```
And also featuring it at the action method level:
```
[HttpGet("GetLatest")]
public JsonResult GetLatest()
```

3. **Three choices to route them all**
>Long story short, ASP.NET Core is giving us three different choices for handling routes:
enforcing the standard RESTful conventions, reverting back to the good old conventionbased
routing, or decorating the controller files with the attribute-based routing.

>It's also worth noticing that attribute-based routes, if/when defined, would override any
matching convention-based pattern. Both of them if/when defined, would override the
default RESTful conventions created by the built-in `UseMvc()` method.
