jersey-doc-annotation
=====================

Add some documentation to your jersey application, to create beautiful documentation using
[jersey-doc-generator](https://github.com/Deisss/jersey-doc-generator) project.

This project add few annotation you can use on every class/method:
  * **ApiDoc**: add some documentation
  * **ApiAuthor**: set the author
  * **ApiVersion**: set the version
  * **ApiDeprecated**: sign as deprecated
  * **ApiUnimplemented**: sign as not ready


Usage
-----
We will describe here a basic (full) available usage:

    @Path("api")
    @ApiDoc("The entry point")
    @ApiAuthor("Deisss")
    @ApiVersion("0.1")
    public class RootResource {

      @Path("version")
      @ApiUnimplemented
      public void getVersion() {}

      @Path("oldversion")
      @ApiDoc("DO NOT USE ANYMORE, SWITCH TO GETVERSION")
      @ApiDeprecated
      public void getOldVersionWay() {}
    }


The **ApiDoc**, **ApiAuthor**, **ApiVersion** can recieve string as parameter, while **ApiUnimplemented** and 
**ApiDeprecated** are used just like this.

__Don't forget all of them can be used both on class and/or method.__

__Don't forget also, that, they don't provide any behaviour, as they are used only for documentation purpose.__


Compile
-------
The project use maven to compile, on the root folder:

    mvn clean compile package

Will create a package in "./target" folder, you can now include this jar in your project.

As this project is quite simple, you can avoid maven: in this case just compile all java files into .class one,
and then create a jar. That's all ! No dependencies !


Have fun !
