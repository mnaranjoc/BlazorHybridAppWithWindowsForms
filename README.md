# Windows Forms Blazor app
https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/tutorials/wpf?view=aspnetcore-6.0

## Create a WPF Blazor project

 - Type: WPF Application
 - Name: WinFormsBlazor
 - Framework version: .NET 6.0

## Configure the project for Blazor

### Install Nuget Package

 - Use `NuGet Package Manager` to install: `Microsoft.AspNetCore.Components.WebView.WindowsForms`

### Change project SDK to Razor

 - In  **Solution Explorer**, right-click the project's name,  `WinFormsBlazor`  and select  **Edit Project File**  to open the project file (`WinFormsBlazor.csproj`).

At the top of the project file, change the SDK to  `Microsoft.NET.Sdk.Razor`:
```
<Project Sdk="Microsoft.NET.Sdk.Razor">
```

### Create imports file

- Add an  `_Imports.razor`  file to the root of the project with an  `@using` directive for `Microsoft.AspNetCore.Components.Web`
```
@using Microsoft.AspNetCore.Components.Web
```

### wwwroot/index.html
- Add a `wwwroot` folder to the project.
- Add an `index.html` file to the `wwwroot` folder with the following markup.
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>WinFormsBlazor</title>
    <base href="/" />
    <link href="css/app.css" rel="stylesheet" />
    <link href="WinFormsBlazor.styles.css" rel="stylesheet" />
</head>

<body>

    <div id="app">Loading...</div>

    <div id="blazor-error-ui">
        An unhandled error has occurred.
        <a href="" class="reload">Reload</a>
        <a class="dismiss">🗙</a>
    </div>

    <script src="_framework/blazor.webview.js"></script>

</body>

</html>
```

### Adding style
- Inside the `wwwroot` folder, create a `css` folder to hold stylesheets.
- Add an `app.css` stylesheet to the `wwwroot/css` folder with the following content.
```
html, body {
    font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
}

h1:focus {
    outline: none;
}

a, .btn-link {
    color: #0071c1;
}

.btn-primary {
    color: #fff;
    background-color: #1b6ec2;
    border-color: #1861ac;
}

.valid.modified:not([type=checkbox]) {
    outline: 1px solid #26b050;
}

.invalid {
    outline: 1px solid red;
}

.validation-message {
    color: red;
}

#blazor-error-ui {
    background: lightyellow;
    bottom: 0;
    box-shadow: 0 -1px 2px rgba(0, 0, 0, 0.2);
    display: none;
    left: 0;
    padding: 0.6rem 1.25rem 0.7rem 1.25rem;
    position: fixed;
    width: 100%;
    z-index: 1000;
}

#blazor-error-ui .dismiss {
    cursor: pointer;
    position: absolute;
    right: 0.75rem;
    top: 0.5rem;
}
```