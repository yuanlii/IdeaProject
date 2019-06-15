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







