# **Handling routes in ASP.NET Core**
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
