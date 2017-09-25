+++
title = "Variables"
date = 2017-08-07T19:56:30+02:00
+++

## Uninitialized variables
Uninitialized variables have an initial value of null.
Even variables with numeric types are initially null, because numbers are objects.

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
