# BasicJava

Java中的static关键字解析
=================================
一.static关键字的用途

在《Java编程思想》P86页有这样一段话：

　　“static方法就是没有this的方法。在static方法内部不能调用非静态方法，反过来是可以的。而且可以在没有创建任何对象的前提下，仅仅通过类本身来调用static
  方法。这实际上正是static方法的主要用途。”
  
    这段话虽然只是说明了static方法的特殊之处，但是可以看出static关键字的基本作用，简而言之，就是
         
                                     方便在没有创建对象的情况下来进行调用（方法/变量）。

　　很显然，被static关键字修饰的方法或者变量不需要依赖于对象来进行访问，只要类被加载了，就可以通过类名去进行访问。static可以用来修饰类的成员方法、类的
  成员变量，另外可以编写static代码块来优化程序性能。
  
  1）static方法

　　static方法一般称作静态方法，由于静态方法不依赖于任何对象就可以进行访问，因此对于静态方法来说，是没有this的，因为它不依附于任何对象，既然都没有对象，
  就谈不上this了。并且由于这个特性，在静态方法中不能访问类的非静态成员变量和非静态成员方法，因为非静态成员方法/变量都是必须依赖具体的对象才能够被调用。

　　但是要注意的是，虽然在静态方法中不能访问非静态成员方法和非静态成员变量，但是在非静态成员方法中是可以访问静态成员方法/变量的。举个简单的例子：

class MyObject {
  private static String str1 = "staticProperty";
  private String str2 = "Property";
  
  public MyObject() {
  }
  
  public void print1() {
    System.out.println(str1);
    System.out.println(str2);
    print2();
  }
  
  public static void print2() {
    System.out.println(str1);
    System.out.println(str2);
    print1(); 
  }
}


二.static关键字的误区
三.常见的笔试面试题
