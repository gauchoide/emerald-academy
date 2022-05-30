Quests - Chapeter 2 - Day 3
------

1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

```
pub fun main() { 
    var people: [String] = ["Erick", "Luca", "Natz"]
    log(people)

}
```

2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!
    

```
pub fun main() {
    var SocialNetworks: {String: UInt64} = {"Facebook": 5, "Instagram": 4, "Twitter": 2, "YouTube": 1, "Reddit": 6, "LinkedIn": 3}
}
```

3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).

We will force-unwrap when the function return value is not specified as an optional type to avoid the mismateched types.

```
pub fun main(): String {        // notice the return value is NOT an optional type
    let greeting: {String: String} = {"Hi": "Hola", "Bye": "Chau"}
    return greeting["Hi"]!      // we added the force-unwrap operator to avoid mismatch
}
```

4. Using this picture below, explain...
  1. What the error message means
  ```
    mismatched types. expected `String`, got `String?` 
  ```
    The return value of the dictionary in the function is an optional, and thus it can be a `String` or `nil`.
  2. Why we're getting this error
    We are getting two types (`string` or `nil`) for the return value while specifiying it would be `String`. 
  3. How to fix it
    As the return value is optional, we need to force-unwrap `thing[0x03]`, like:
  ```
  pub fun main(): String {
      let thing: {Address: String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
      return thing[0x03]!   // we are force-unwrapping the optional
  }
  ```

Or specify the return value can be optional:


```
pub fun main(): String? {  // we specify the return value is an optional type
    let thing: {Address: String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
    return thing[0x03]
}
```


