# Examples from Java 9 ++ modules

![Logging-Sins-793x397](https://user-images.githubusercontent.com/20374208/58885740-674c4900-86eb-11e9-9448-b0af3d8b52c0.png)


- **Categories**
  - **Simple module**
  - **Optional**
  - **Transitive**
  - **Cyclic**
  - **Qualified**

Highly based on  [ java-9-new-features-in-simple-way-jshell-jpms-and-more ](https://www.udemy.com/java-9-new-features-in-simple-way-jshell-jpms-and-more/) and [Jenkov Tutorials](http://tutorials.jenkov.com/java/modules.html)

### 1. Simple module

  Compile :
> javac --module-source-path simple_module -d out1 -m moduleA

  Run :
> java --module-path out1 -m moduleA/pack1.Main


### 2. Optional 

  Compile :
> javac --module-source-path optional_module -d out2 -m moduleA,moduleB

  Run :
> java --module-path out2 -m moduleB/pack2.Main


### 3. Transitive 
 
  **Be careful not spaces are allowed between (moduleA,moduleB,moduleC)**
  
  Compile :
> javac --module-source-path transitive_module -d out3 -m moduleA,moduleB,moduleC


  Run :
> java --module-path out3 -m moduleC/pack3.Main


### 4. Cyclic 

![chrome_2019-06-05_11-26-54](https://user-images.githubusercontent.com/20374208/58941624-d3c75680-8784-11e9-8dd3-6d4982f6be4e.png)

``` JAVA
 module moduleA{
  
  requires moduleB;
  
 }
```

``` JAVA
 module moduleB{
  
  requires modeuleA;
  
 }
```

  Compile :
> javac  --module-source-path src -d out -m moduleA,moduleB

This will produce the following error :

``` JAVA
error: cyclic dependence involving moduleA requires moduleA;
```

![chrome_2019-06-05_11-26-05](https://user-images.githubusercontent.com/20374208/58941549-b6928800-8784-11e9-856f-8914ac6f3779.png)

### 5. Qualified 

//TODO

  Compile :
>

  Run :
> 



