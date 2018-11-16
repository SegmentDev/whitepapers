# In-Memory Fading Dictionary

### WIP 11/15/18


Provides a dictionary implementation which stores a certain amount of previous values and provides a smart model for updating those values.

### Core features
* Should be threadsafe (uses ConcurrentDictionary)
* Provides easy methods to update values, get current values, and know if there is a change
* Can store a certain number of values


```csharp
var dictionary = new FadingDictionary<string, decimal>(depth: 5);

dictionary.GetValue("GOOG:PXLAST"); // throws KeyError

dictionary.Push("GOOG:PXLAST", 990.23);

dictionary.GetCurrent("GOOG:PXLAST");
// - is equivalent to -
dictionary.GetValue("GOOG:PXLAST");
// - or -
dictionary.GetValue("GOOG:PXLAST", 0);

// returns 990.23

dictionary.Push("GOOG:PXLAST", 992.33);

dictionary.GetValue("GOOG:PXLAST"); // 992.33
dictionary.GetValue("GOOG:PXLAST", 1); // 990.23 
```

`Push()` should be smart enough to not add in a value if there has not been a change. Maybe we can set this explicitly, `Push(123, explicit:true);`

```csharp
var dictionary = new FadingDictionary<string, decimal>(depth: 5, returnNullInsteadOfExeption: true);

dictionary.GetValue("GOOG:PXLAST"); // null
```



