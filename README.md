
Code as per Scott Allen's OdeToFood
Few changes
For the startup CSTOR

Issue#1 Unable to find AddJsonFile
Solution: Add a dependency to the Nuget  "Microsoft.Extensions.Configuration.Json": "1.0.0"
Issue#2: Unable to find appsettings.json Null Reference Exception
Solution: Add a param of type IHostingEnvironment to teh CSTOR
SetBasePath
Your CSTOR should now look like this:
  public Startup(IHostingEnvironment env)
        {
            var builder = new ConfigurationBuilder()
                        .SetBasePath(env.ContentRootPath)
                        .AddJsonFile("appsettings.json");
             Configuration = builder.Build();
        }
