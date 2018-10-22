# In-Memory Ghosting Dictionary
Provides a dictionary implementation which stores a certain amount of previous values and provides a smart model for updating those values.

### Core features
* Should be threadsafe (uses ConcurrentDictionary)
* Provides easy methods to update values, get current values, and know if there is a change
* Can store a certain number of values
