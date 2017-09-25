+++
title = "Uninitialized variables"
+++

Uninitialized variables have an initial value of null because everyting in dart is an object.

``` dart
  void main() {
    var a;
    num b;
    int c;
    double d;
    bool e;

    print(a); // null
    print(b); // null
    print(c); // null
    print(d); // null
    print(e); // null
  }
```
