# Welcome

## Who we are?


---

# Duplicated Code

> When code fragments are repeated

```                                        
if (creditCard.Number.length() > 16) {      
  // do something because it's valid       
}                                          
...                                        
if (creditCard.Number.length() > 16) {     
  // do something else because it's valid  
}                                          
```

+++

# Duplicated Code

Extract method

```                                        
if (creditCard.Number.isValid()) {      
  // do something because it's valid       
}                                          
...                                        
if (creditCard.Number.isValid()) {     
  // do something else because it's valid  
}                                          
```

---

# Long method

> When methods are too long and do too many things

---

# Large class

> When a class solves too many problems or has too many fields/methods/lines of code

---

# Long parameter list

> When more than three parameters are found on a method

---

# Primitive obsession

> When an object can represent a concept better than a String or an Int

---

# Switch statements

> When too many switch and ifs are used instead of polymorphism