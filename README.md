# visiu

Those are just notes, not good ideas, only unusual. 

Code is markdown from start.
Classes have data and functions in separate structures.
No inheritance, only mixin.
Functional and OO.
Dependency injection by default.
printConstructor Method by default.
Monkeypatching.
Smalltalk style function signature. 

type name
data
functions

-/+(private or public)  varName type typeTag(s)

Types:   
- Singleton
- Implementation: needs to be wired.

```
User.visiu
# User Singleton
```visiu
{
  + name String::Name;
  + age Integer::Age;
  - extra String::Comment;
};

changeName: newName String::Name age: newAge Integer::Age => {
  this.name = newName;
  this.age = newAge;
  this.extra = "Age is ${newAge} and name is ${newName}"::Comment; // just "foo" would not work as tags are checked in compile time
}
\```
UserPrinterConsole.visiu

# UserPrinterConsole Implementation::UserPrinter

This will print a user on the console.

## Note

There can be other implementations for other output formats.

There is no data
```visiu

print: user User  => {
  System.print: user;
}
\```   

Wiring.visiu
```visiu
UserPrinter = UserPrinterConsole
\```

Entry.visiu
User u = User_name: "Jhon"::Name age: 45::Age;
UserPrinter_print: u;
\```
