Local Imports
=============

Local imports work the same way as normal imports, its just it imports the
objects locally, not globally. It also uses the `limport` keyword. Example:

```neutron
limport "io::print";
print("hi");

func hi(){
  print("hi"); // refer to un-existent function print
}

hi(); // returns error
```

This is useful if you want to import something in a function but don't want to
pollute the global namespace:

```neutron
func hi(){
  limport "io::print";
  print("hi");
}

// no namespace pollution
hi(); // prints "hi"
```
