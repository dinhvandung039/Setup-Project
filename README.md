# Setup-Project

### set up depencency in mvc 5
```
protected void Application_Start()
{
    RegisterAutofac();
    AreaRegistration.RegisterAllAreas();
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
    RouteConfig.RegisterRoutes(RouteTable.Routes);
    BundleConfig.RegisterBundles(BundleTable.Bundles);
}

private void RegisterAutofac()
{
    var builder = new ContainerBuilder();

    // Register your MVC controllers. (MvcApplication is the name of
    // the class in Global.asax.)
    builder.RegisterControllers(typeof(MvcApplication).Assembly);

    builder.RegisterType<StudentService>().As<IStudentService>();
    builder.RegisterType<MyCodeFirstContext>().AsSelf().As<DbContext>().InstancePerLifetimeScope();

    // Set the dependency resolver to be Autofac.
    var container = builder.Build();
    DependencyResolver.SetResolver(new AutofacDependencyResolver(container));
}
```

### Extension for web development on visual studio

- toggle comment
- visual studio intellicode
- emmet
- add new file
- productivity power tools
