# AbpHelper

AbpHelper is a tool that help you with developing Abp vNext applications.

**Make sure backup your source files before using it!**

# Getting Started

1. Install AbpHelper CLI tool

    `dotnet tool install EasyAbp.AbpHelper -g`

    > If you prefer GUI, there is also a tool with a fancy UI: [AbpHelper.GUI](https://github.com/EasyAbp/AbpHelper.GUI)

1. If you have previously installed it, update it with the following command:

    `dotnet tool update EasyAbp.AbpHelper -g`

1. Use [ABP CLI](https://docs.abp.io/en/abp/latest/CLI) to create a test application

    `abp new MyToDo`

1. Create an entity

    ``` csharp
    public class Todo : FullAuditedEntity<Guid>
    {
        public string Content { get; set; }
        public bool Done { get; set; }
    }

    ```

1. Run AbpHelper

    `abphelper generate crud Todo -d C:\MyTodo`

    * `generate crud` is a sub command to generate CRUD files
    * `Todo` specified the entity name we created earlier
    * `-d` specified the **root** directory of the ABP project, which is created by the ABP CLI

    AbpHelper will generate all the CRUD stuff , even include adding migration and database updating!

1. Just rebuild your application and run it
1. Login with the admin user, then grant "Todo" permissions to the user
1. Now you can see the "Todo" feature, with all the CRUD stuff!

    ![running_demo](doc/images/2020-02-10-14-09-22.png)

# Usage

* Run `abphelper -h` to see the general help
* Similarly, you can use `-h` or `--help` option to see detailed usage of each of the following command

## Commands

* generate

  Generate files for ABP projects. See 'abphelper generate --help' for details

  * crud

    Generate a set of CRUD related files according to the specified entity

    [Demo GIF](doc/images/crud.gif)

  * service

    Generate service interface and class files according to the specified name

    [Demo GIF](doc/images/service.gif)

  * methods

    Generate service method(s) according to the specified name(s)

    [Demo GIF](doc/images/methods.gif)

  * localization

    Generate localization item(s) according to the specified name(s)

    [Demo GIF](doc/images/localization.gif)

# Extensibility

TODO: Describe how to custom the generating steps, and custom templates.

# Roadmap

- [ ] More CLI parameters
- [x] Support ABP module solutions
- [ ] Support MogoDB generation
- [ ] Support Angular UI generation

