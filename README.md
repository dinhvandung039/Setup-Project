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

### Keyboard shortcut

- Ctrl M + G => Go to view
- Ctrl M + V => Add View

- json file

"editor.renderIndentGuides": false,
"workbench.iconTheme": "material-icon-theme",
"[html]": {
  "editor.defaultFormatter": "HookyQR.beautify"
},
"terminal.integrated.rendererType": "dom",
"liveServer.settings.donotShowInfoMsg": true,
"liveServer.settings.donotVerifyTags": true,
"gitlens.views.repositories.files.layout": "tree",
"editor.suggestSelection": "first",
"editor.tabSize": 2,
"[javascript]": {
  "editor.defaultFormatter": "esbenp.prettier-vscode"
},
"terminal.integrated.shell.windows": "C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\powershell.exe",
"editor.fontFamily": "'Consolas', 'Courier New', monospace",
"emmet.includeLanguages": {
  "javascript": "javascriptreact",
  "razor": "html"
},
"editor.multiCursorModifier": "ctrlCmd",
"editor.cursorSmoothCaretAnimation": true,
"editor.quickSuggestionsDelay": 3,
"prettier.useTabs": true,
"prettier.singleQuote": true,
// Editor Tweak
"files.eol": "\n",
"editor.renderWhitespace": "none",
// Eslint
// Prettier
"prettier.printWidth": 100,
"prettier.trailingComma": "all",
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
"editor.scrollBeyondLastColumn": 6,
"files.autoSaveDelay": 0,
"extensions.ignoreRecommendations": true,
"zenMode.hideStatusBar": false,
"zenMode.hideActivityBar": false,
"zenMode.hideTabs": false,
"zenMode.restore": true,
"git.ignoreMissingGitWarning": true,
"editor.dragAndDrop": true,
"javascript.updateImportsOnFileMove.enabled": "always",
"editor.formatOnSave": true,
"editor.formatOnPaste": true,
"editor.formatOnType": true,
"cSpell.words": [
  "Xunit"
],
"editor.wordWrapColumn": 90,
"cSpell.allowCompoundWords": true,
"[blade]": {
  "editor.defaultFormatter": "onecentlin.laravel-blade",
  "editor.formatOnSave": true
},
"php-cs-fixer.executablePath": "${extensionPath}\\php-cs-fixer.phar",
"[php]": {
  "editor.defaultFormatter": "junstyle.php-cs-fixer",
  "editor.formatOnSave": true
},
"php-cs-fixer.rules": "@PSR2",
"php-cs-fixer.allowRisky": true,
"php-cs-fixer.autoFixBySemicolon": true,
"php-cs-fixer.onsave": true,
"editor.detectIndentation": false,
"php-cs-fixer.config": "<?php return PhpCsFixer\\Config::create()->setIndent(str_pad('', 2));"

- extensions: 
+ auto import
+ auto rename tag
+ babel js
+ beautify
+ bracket pair colorizer 2
+ code spell checker
+ Debugger for chrome
+ dotenv
+ eslint
+ git history
+ gitlens
+ HTML to CSS autocompletion
+ indent-rainbow
+ js6
+ laravel blade snippets
+ laravel extra intellisense
+ laravel goto view
+ laravel goto controller
+ laravel snippets
+ live server
+ markdownlint
+ material icon theme
+ path intellisense
+ php cs fixer
+ php extension pack
+ php intelephese
+ php intellisense
+ pretter
+ reactjs code snippets
+ visual studio intellicode

 //var authorizeConfig = Configuration.GetSection("Authentication");

            //services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
            //  .AddJwtBearer(options =>
            //  {
            //      options.SaveToken = true;
            //      options.RequireHttpsMetadata = false;
            //      options.TokenValidationParameters =
            //           new TokenValidationParameters
            //           {
            //               ValidIssuer = authorizeConfig.GetValue<string>("Issuer"),
            //               ValidAudience = authorizeConfig.GetValue<string>("Audience"),
            //               IssuerSigningKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(authorizeConfig.GetValue<string>("Secret"))),
            //           };
            //  });
