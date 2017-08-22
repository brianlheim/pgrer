# C++ programmer errors

1. Used a reference type with the object pointed to by an iterator, then invalidated the iterator,
then tried to use the reference. Basically this:

```cpp
my::container container;
/* ... */
my::container::iterator it = container.begin();
/* ... */
{
    my::object& ref = *it;
    ++it;
    std::cout << ref << std::endl; // WRONG: access to invalid reference.
}
```

2. Forgot to const everything I could.

3. Forgot to const& function parameters where appropriate.

4. Forgot semicolon.
