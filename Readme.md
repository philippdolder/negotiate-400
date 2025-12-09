It works just fine after disabling prerender.

But after changing to run from a subfolder it stops working. 
The call to http://localhost:5187/subfolder/_blazor/negotiate?negotiateVersion=1
returns HTTP 400 - A valid antiforgery token was not provided with the request. Add an antiforgery token, or disable antiforgery validation for this endpoint.

The Command "dotnet new blazor -o Ui --interactivity Server --empty --all-interactive --use-program-main" was run to create the basic ui. Before doing the incremental changes split into separate commits.

Replacing `app.MapStaticAssets()` with `app.UseStaticFiles()` works around the issue, but doesn't solve it, as I want to use the functionality from `MapStaticAssets()`.