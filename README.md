# IdeaProject
This is learning documents for Scala.
[Course link](https://www.coursera.org/learn/progfun1/lecture/UzicG/tools-setup-for-mac-os-x)


## Set up IntelliJ IDEA
* [tutorial](https://www.coursera.org/learn/progfun1/supplement/VuJFf/intellij-idea-tutorial)

1. Download IntelliJ IDEA Community Edition
IntelliJ IDEA Community Edition is an open-source version of IntelliJ IDEA, a premier IDE for Java, Scala and other JVM-based programming languages. You can download it from the official website.

2. Install the Scala plugin
Go to the bottom right of the Welcome Screen and choose Configure → Plugins → Browse JetBrains Plugins. If such Welcome Screen doesn't appear, go to Preferences (Settings) → Plugins.

3. Setup the JDK
From the welcome screen, go to Configure → Project defaults → Project structure and add the JDK. 

4. Creating a project
The easiest way to create a project is to use the Project Wizard. To use it, click Create New Project on the Welcome Screen, then select Scala, and finally SBT Project.

5. Creating a Scala worksheet
Simply use the Create New action(action: right click on the project navigation bar on the left) from context menu or from a Scala package (anything under the `scala` folder).

* To evaluate worksheets, use the corresponding toolbar icon (the play button), or press Alt+Ctrl+W (Alt+Cmd+W on OS X).
* AFTER creating Scale worksheet:
  * 设置SDK (Software Development Toolkit) -> 之后再重启project/scr/main/scala - ”new scala worksheet"   # when "new scala worksheet option" is not available
  * [reference](https://stackoverflow.com/questions/36867112/how-to-get-the-option-to-create-a-new-scala-worksheet-in-intellij)
 
* Problem fixing:
scala worksheet - "internal error: null"
=> solution: try installing the latest version of Scala and SDK
  * JDK - Java Development Kit
  
6. Creating a Scala class
Much akin to worksheets, Scala classes are created via context menu action Create New.
(action: right click to run the app)

![build scala class](https://github.com/yuanlii/IdeaProject/blob/master/img/create_new_scala_class(object).png)

* warning appears in Example.scala -> benighted; just ignore

7. Opening an SBT project
* All the handout files (assignments) are SBT projects. If you want to hack on them using Intellij, you need to import the project first.
* remember: in order to import the project, you will need to import the sbt file first

To open an SBT project in IntelliJ IDEA, go to the Welcome Screen, click Import Project, and select SBT build file that you wish to open. IntelliJ IDEA will then create a new project and import the selected file to it.

8. Synchronizing SBT and IntelliJ IDEA projects
IntelliJ IDEA SBT support synchronizes the project with your build file, so when you change Scala version you're going to use, or add a library, your project is updated accordingly. For the next time, you can avoid this step by checking off the option ''Use auto-import" in Step 7.

add this line to the .sbt(build.sbt) file:
```
libraryDependencies += "org.scalatest" %% "scalatest" % "3.0.5" % "test"
```
this is to add scalatest, which is a test framework for scala #enabled it
get the latest version of scalatest from [website](http://www.scalatest.org/install)

![import framework](https://github.com/yuanlii/IdeaProject/blob/master/img/import_framework.png)

* problem fixing:
if frameworks not imported correctly, tried stop the module and import it again.
process: close project --> import project --> open build.sbt
[ref](https://stackoverflow.com/questions/24937328/intellij-idea-cannot-import-sbt-project)


----
IDE for Scala:
* Intellij IDEA
* Eclipse

.sbt file:
The build definition goes in a file called build.sbt, located in the project’s base directory. 

sbt reference:
https://www.scala-sbt.org/0.13/docs/Hello.html
-> comprehensive guide for building definition in sbt

sbt(Simple Build Tool) is a general purpose build tool written in Scala. 
- It borrows good ideas from other successful build tools like Ant, Maven, and Gradle.

## Install sbt on your machine
$ brew install sbt

$ sbt about #view the basic information about sbt

sbt terminology consists of two terms -- tasks and settings. 
- tasks: whenever you want to perform any action you execute a task
#view all the tasks applicable to a project:
```
$ sbt tasks  
```
- settings

---
## Create an sbt Scala project

[reference](https://github.com/shekhargulati/52-technologies-in-2016/blob/master/02-sbt/README.md)
build a simple task management app -- tasky for TODO management
```
$ mkdir tasky
$ cd tasky
```
inside tasky directory, create a new file -- build.sbt to house the build script
```
name := "tasky"
version := "0.1.0"
```
Now, run the sbt command:
```
$ sbt
> help  
# view all the tasks available
# This is the sbt shell
```
* By default, sbt follows Maven project layout;
* SBT commands are executed inside the SBT shell. 
```
scala> println("Oh, hai!")                                          
# This is the Scala REPL, type some Scala code
Oh, hai!
```

### sbt says Hello
create a new Scala file HelloSbt.scala inside src/main/scala and place the following contents in it:
```Scala
object HelloSbt extends App {
  println("Sbt says Hello!!")
}

```

Now you can run the code from inside the sbt shell by first compiling the code using compile

* Compiling your Code
```
> compile
```
The compile task will compile the source code of the assignment which is located in the directory src/main/scala.

* Testing your Code
contains unit tests for the project. In order to run these tests in sbt, you can use the test command.
```
> test
```
* Running your Code
and then running it using the run task
```
> run
```

### Set Scala version
Update the build.sbt with the scalaVersion setting.
```
name := "tasky"
version := "0.1.0"
scalaVersion := "2.11.6"
```
sbt will not pick any change in the build.sbt until you run the reload task.
```
> reload
```

Now if you compile the project using compile task you will see that project is compiled using scala 2.11.6 version:
```
> compile
```

sbt uses Apache Ivy dependency manager to perform automatic dependency management:
```
libraryDependencies += "org.scalatest" % "scalatest_2.11" % "2.2.6" % "test"
```

* appendix:
- [Apache Maven](https://maven.apache.org/) - Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information.

### Running the Scala Interpreter inside SBT (REPL)

you can start the Scala interpreter inside sbt using the `console` task. 

In order to quit the interpreter and get back to sbt, type <Ctrl+D>.

--- 
## TODO:
1. learn more about sbt by building TODO app from scratch
2. finish the basic part in coursera in terms of running Scala using SBT


