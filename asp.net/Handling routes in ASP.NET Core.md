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
