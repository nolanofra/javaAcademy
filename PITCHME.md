### Refactoring

Refactoring: a change made to the internal structure of software to make it 
easier to understand and cheaper to modify without changing its observable behavior

* Make the sofwtare easier to change and modify
* Performance optimization

---
### Why

* Improve design of your software
* Make software easier to understand
* Helps you find bugs


---
### When

* When you add a function
* When you need to fix a bug
* When you do a code review

---
### Problems

* Application coupled to database schema
* Change interfaces

---

### Feature envy

* a method that seems more interested in a class other than the one it is in



```
public class Phone {
   private final String unformattedNumber;
   public Phone(String unformattedNumber) {
      this.unformattedNumber = unformattedNumber;
   }
   public String getAreaCode() {
      return unformattedNumber.substring(0,3);
   }
   public String getPrefix() {
      return unformattedNumber.substring(3,6);
   }
   public String getNumber() {
      return unformattedNumber.substring(6,10);
   }
}
public class Customer…
   private Phone mobilePhone;
   public String getMobilePhoneNumber() {
      return "(" + 
         mobilePhone.getAreaCode() + ") " +
         mobilePhone.getPrefix() + "-" +
         mobilePhone.getNumber();
   }

```
```
public class Phone {
   private final String unformattedNumber;
   public Phone(String unformattedNumber) {
      this.unformattedNumber = unformattedNumber;
   }
   private String getAreaCode() {
      return unformattedNumber.substring(0,3);
   }
   private String getPrefix() {
      return unformattedNumber.substring(3,6);
   }
   private String getNumber() {
      return unformattedNumber.substring(6,10);
   }
   public String toFormattedString() {
      return "(" + getAreaCode() + ") " + getPrefix() + "-" + getNumber();
   }  
}
public class Customer…
   private Phone mobilePhone;
   public String getMobilePhoneNumber() {
      return mobilePhone.toFormattedString();
   }

```
