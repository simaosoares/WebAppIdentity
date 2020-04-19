# WebAppIdentity

Sample Web Application featuring ASP.NET Core 3 Authentication with Identity

Table of contents:

* [Creating a basic Razor Pages Web app](#creating-a-basic-razor-pages-web-app)
* [Creating the Web app with authentication](#creating-the-web-app-with-authentication)
* [References](#references)

## Creating a basic Razor Pages Web app

Create a Razor Pages web app with ASP.NET Core

```
dotnet new webapp -o WebAppIdentity
```

Test the application with:
```
dotnet run
```

More information can be found at the following location [Create a Razor Pages web app with ASP.NET Core].

## Creating the Web app with authentication

Create an ASP.NET Core Web Application project with Individual User Accounts.

```
dotnet new webapp --auth Individual -o WebAppIdentity
```

> The generated project provides ASP.NET Core Identity as a [Razor Class Library]. The Identity Razor Class Library exposes endpoints with the Identity area. For example:

```
/Identity/Account/Login
/Identity/Account/Logout
/Identity/Account/Manage
```


Apply the migrations:

```
dotnet ef database update
```

Test the application with:
```
dotnet run
```

Identity is enabled by calling UseAuthentication. UseAuthentication adds authentication middleware to the request pipeline.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    //...
    app.UseAuthentication();
    //...
}
```


> The template-generated app does not use authorization. `app.UseAuthorization` is included to ensure it's added in the correct order should the app add authorization. UseRouting, UseAuthentication, UseAuthorization, and UseEndpoints must be called in the order shown in the preceding code.


More information can be found at the following location [Create a Web app with authentication].

## References

* [Create a Razor Pages web app with ASP.NET Core]
* [Create a Web app with authentication]
* [Razor Class Library]

[Create a Razor Pages web app with ASP.NET Core]: https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/?view=aspnetcore-3.1
[Create a Web app with authentication]: https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-3.1
[Razor Class Library]: https://docs.microsoft.com/en-us/aspnet/core/razor-pages/ui-class?view=aspnetcore-3.1&tabs=visual-studio