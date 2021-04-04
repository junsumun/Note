# Java Note

### Class vs Interface

Class:
- A class desribes the attributes and behaviors of an object.
- A class may contain abstract methods, concrete methods.
- Members of a class can be public, private, protected or default.

Interface:
- An interface contains behaviors that a class implements.
- An interface contains only abstract methods.
- All the members of the interface are public by default.
- Java does not support "multiple inheritance". However, it can be achieved with interfaces. ex implement interface1, interface2


Sort API:

```java
class Product implements Comparable<Product> {
  public String name;
  public int sales;
  public int price;
  
  public Product(String name, String sales, String price) {
    this.name = name;
    this.sales = Integer.parseInt(sales);
    this.price = Integer.parseInt(price);
  }
  
  public int compareTo(Product o) {
    int compare = o.sales - this.sales;
    
    if (compare == 0) {
      return this.price - o.price;
    }
    
    return compare;
  }
  
}


import java.io.*;
import java.util.*;

class MyCode {
	public static void main (String[] args) {
  
    
    List<String> list = new ArrayList<>();
    list.add("Selfie Stick,98,29");
    list.add("iPhone Case,90,15");
    list.add("Fire TV Stick,48,49");
    list.add("Wyze Cam,48,25");
    list.add("Water Filter,56,49");
    list.add("Blue Light Blocking Glasses,90,16");
    list.add("Ice Maker,47,119");
    list.add("Video Doorbell,47,199");
    list.add("AA Batteries,64,12");
    list.add("Disinfecting Wipes,37,12");
    list.add("Baseball Cards,73,16");
    list.add("Winter Gloves,32,112");
    list.add("Microphone,44,22");
    list.add("Pet Kennel,5,24");
    list.add("Jenga Classic Game,100,7");
    list.add("Ink Cartridges,88,45");
    list.add("Instant Pot,98,59");
    list.add("Hoze Nozzle,74,26");
    list.add("Gift Card,45,25");
    list.add("Keyboard,82,19");
        
		System.out.println("Hello Java");
    List<Product> products = new ArrayList<>();
    for (int i=0; i < list.size(); i++){
      String data[] = list.get(i).split(",");
      products.add(new Product(data[0], data[1], data[2]));
    }        
    
    Collections.sort(products);
  
    // Collections.sort(products, (o1, o2) -> {
    //   if (o1.sales == o2.sales) {
    //     return o1.price < o2.price ? 1: -1;
    //   }
    //   return o1.sales > o2.sales ? -1: 1;
    // });
    
    for (int i=0; i < products.size(); i++) {
      System.out.println(i + " "+ products.get(i).name);
    }
	}
}
```
