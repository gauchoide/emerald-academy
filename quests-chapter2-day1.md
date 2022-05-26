Quests - Chapter 2 - Day 1
------ 

For todays quest, please load up a new Flow playground by going to https://play.onflow.org just like we did in this lesson. You will use that for writing your code.

1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.

```
pub contract JacobTucker {

    pub let is: String

    init() {
        self.is = "the best"
    }
}
```

![JacobTucker Smart Contract](https://github.com/gauchoide/emerald-academy-bootcamp/blob/main/emerald-bootcamp-quests-c2d1-smart.jpg)


2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output

```
import JacobTucker from 0x03

pub fun main(): String {
    return JacobTucker.is
}
```

![JacobTucker Script](https://github.com/gauchoide/emerald-academy-bootcamp/blob/main/emerald-bootcamp-quests-c2d1-script.jpg)

