By defining props on a component, it can then receive data. 
There are a few javascript data types: string, number, boolean, array, object, date, function, symbols.
The array syntax method can be very useful when prototyping. It is considered best practice to use the Object syntax.

When defining props ask yourself these questions?
what data type should this prop expect? You can have type take in an array of types...type: [Number, String]
Is this prop critical? Add the key of required equal to true. This takes care of what if someone forgets a critical prop?
Do we need to pass every prop everytime? Can we provide a default state for most use cases?......


