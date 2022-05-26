
Quests - Chapter 2 - Day 2
------

1. Explain why we wouldn't call changeGreeting in a script.

`changeGreeting` is actually changing the string variable, and being a change (modify) operation can't be executed as a Script (read-only).

2. What does the AuthAccount mean in the prepare phase of the transaction?

`AuthAccount` allows access to the information/data in the user account, as the user stores their assets (NFT for ex.) in their account, this allows our transactions to access the assets.

3. What is the difference between the prepare phase and the execute phase in the transaction?

The prepare phase is to actually get access to the data or information while execute phase should be used for the changing of it. 

4. Add two new things inside your contract:
    - A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
    - A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber


```
pub contract HelloWorld {

    pub var greeting: String

    pub var myNumber: Int

    pub fun changeGreeting(newGreeting: String) {
        self.greeting = newGreeting
    }

    pub fun updateMyNumber(newNumber: Int) {
        self.myNumber = newNumber
    }

    init() {

        self.greeting = "Hello, world!"
        self.myNumber = 0

    }
}
```


6. Add a script that reads myNumber from the contract


```
import HelloWorld from 0x01


pub fun main(): Int {
    return HelloWorld.myNumber
}

```


7. Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.

```
import HelloWorld from 0x01

transaction(myNewNumber: Int) {
    prepare(signer: AuthAccount) {}

    execute {
      HelloWorld.updateMyNumber(newNumber: myNewNumber)
  }
}
```
