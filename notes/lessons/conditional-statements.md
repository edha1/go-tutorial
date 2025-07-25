# 🗯 Conditional Statements statements 


## ❓ If Statements 

*See if-statements.md in code-snippets for examples!* 

- Similar to a for loop, and we can **define statements** that can be executed before the condition. 
- If we declare variables in the statement, their **scope** is limited to the **if block**. 
- Can add **else** statements too. 

*Try Excercise 4 for practise!* 

## ❔ Switch Statements 

- Switch statements are cleaner ways of writing if statements. 
- They evaluate from top to bottom and stop when the case is met. 
- In Go, they differ from other languages in the fact that it will **only run the selected case** (an explicit break statement is not required), and the cases **do not need to be constants.** 

*See an example in switch-and-defer.md in code snippets!* 

## 🛑 Defer statements 

- Defer statements will only execute a bit of code when the **surrounding function has returned**. 
- It will evaluate the code before hand, but execute after the function has returned. 
- They can be **stacked**. The deferred calls are executed in a **last-in-first-out** order. 

*See an example in switch-and-defer.md in code snippets!* 