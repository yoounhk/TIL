# When Expression

The *when* expression replaces the switch statement in C-like languages. In the simplest form it looks like this

```kotlin
when (x) {
    1 -> print("x == 1")
    2 -> print("x == 2")
    else -> { // Note the block
        print("x is neither 1 nor 2")
    }
}
```

