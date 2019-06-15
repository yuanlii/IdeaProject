# IdeaProject
This is learning documents for Scala.


## Set up IntelliJ IDEA
* [tutorial](https://www.coursera.org/learn/progfun1/supplement/VuJFf/intellij-idea-tutorial)

AFTER creating Scale worksheet:
设置SDK (Software Development Toolkit) 
-> 之后再重启project/scr/main/scala - ”new scala worksheet"   # when "new scala worksheet option" is not available

* [reference](https://stackoverflow.com/questions/36867112/how-to-get-the-option-to-create-a-new-scala-worksheet-in-intellij)

---
### Problem fixing 
* scala worksheet - "internal error: null"
=> solution: try installing the latest version of Scala and SDK

JDK - Java Development Kit

---
close project --> import project --> open build.sbt
build.sbt:
- scalatest: test framework for scala #enabled it 

* warning appears in Example.scala
-> benighted; just ignore
objc[72615]: Class JavaLaunchHelper is implemented in both /Library/Java/JavaVirtualMachines/jdk1.8.0_144.jdk/Contents/Home/bin/java (0x10db904c0) and /Library/Java/JavaVirtualMachines/jdk1.8.0_144.jdk/Contents/Home/jre/lib/libinstrument.dylib (0x10ebb74e0). One of the two will be used. Which one is undefined.
[ref](https://stackoverflow.com/questions/24937328/intellij-idea-cannot-import-sbt-project)





