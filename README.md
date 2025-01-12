This is my summary of Refactoring (second edition), by Martin Fowler.

I recommend you to buy and read the book to learn any concept directly from its author.

# Contents

- [Chapter 1. Refactoring: A first example](#chapter-1-refactoring-a-first-example)
- [Chapter 2. Principles in Refactoring](#chapter-2-principles-in-refactoring)
  - [When Shoud We Refactor?](#when-shoud-we-refactor)
  - [When Shoud We NOT Refactor?](#when-shoud-we-not-refactor)
  - [Problems With Refactoring](#problems-with-refactoring)
  - [Refactoring and Performance](#refactoring-and-performance)
- [Chapter 3. Bad Smells in Code](#chapter-3-bad-smells-in-code)
- [Chapter 4. Building Tests](#chapter-4-building-tests)
- [Chapter 5-12. Refactorings Catalog](#chapter-5-12-refactorings-catalog)

# Chapter 1. Refactoring: A first example

- When you have to add a feature to a program but the code is not structured in a concenient way, first refactor the program to make it easay to add the feature, then add the feature.
- Before you start refactoring, be sure you have a solid suite of tests. These tests must be self-checking.
- Refactoring changes the program in small steps, so if you make a mistake, it is easy to find where the bug is.
- Any fool can write code that a computer can understand. Good programmers write code that humans can understand.
- When programming, follow the camping rule: Always leave the code base healthier than when you found it.
- The true test of good code is how easy it is to change it.

# Chapter 2. Principles in Refactoring

- If someone says their code was broken for couple of days while they are refactoring, you can be pretty sure they were not refactoring.
- When you are refactoring, don't add any new feature. When you are adding a new feature, don't change the current code.
- Refactoring improves de design of the software.
- Refactoring makes software easier to understand.
- Refactoring helps to find bugs.
- Refactoring helps to program faster.

## When Shoud We Refactor?

- **Preparatory Refactoring**: Making it easier to add a feature.
- **Comprehension Refactoring**: Making code easier to understand.
- **Litter-Pickup Refactoring**: Minor code clean up when doing a task.
- **Planned and Opportunistec Refactoring**.
- **Long-Term Refactoring**: Better to do big refactors gradually.
- **Refactoring in a Code-Review**.

## When Shoud We NOT Refactor?

- Messy code that you don't need to modify it.
- When the code is easier to rewrite it than to refactor it.

## Problems With Refactoring

- **Slowing Down New Features**: A huge refactor for a so small feature.
- **Code Ownership**.
- **Branches**: The longer you work on an isolate branch, the harder the job of integrating it to mainline. Better to integrate as frequently as possible.
- **Testing**: Self-testing code is a requirement.
- **Legacy Code**: Usually without tests or not designed with testing in mind. It can't be safely refactored without risk.
- **Databases**.

## Refactoring and Performance
Refactoring helps to write fast software.
It slows the software in the short term while we are refactoring, but makes it easier to tune during optimization.

# Chapter 3. Bad Smells in Code

- **Mysterious Name**: When you can't think of a good name for something, it is often a sign of a deeper design malaise.
- **Duplicate Code**: If it is a real code duplication, better to unify it.
- **Long Function**: The longer a function is, the more difficult it is to understand.
- **Long Parameters List**: Can be confusing. If several parameters fit together, combine them into an object.
- **Global Data**: It can be modified from anywhere.
- **Mutable Data**: Limit the risks of unrestricted data updates.
- **Divergent Changes**: When a module is often changed in different ways for different reasons.
- **Shotgun Surgery**: When everytime you make a change, you have to make a lot of little edits to a lot of different places.
- **Feature Envy**: When a function in one module spends more time communicating wiht functions or data inside another module.
- **Data Clumps**: Bunches of data that hung around toghether really ought to find home together.
- **Primitive Obsession**: Create your own fundamenal types when they are usefull for your domain.
- **Repeated Switches**: When the same conditional switching logic pops up in different places.
- **Loops**: Pipeline operations help to see the involved operations.
- **Lazy Element**: A function or a class that doesn't do enough should be deleted.
- **Speculative Generality**: “Just in case” code to support anticipated future features that never get implemented should be removed.
- **Temporary Field**: Fiels that only get a value under certain circumstances are diffucult to understand.
- **Message Chains**: When a client requests another object, that object requests yet another one, and so on. The client is coupled to the navigation structure, if it changes, the client will change too.
- **Middle Man**: An object that doesn't do anything other than delegate.
- **Insider Trading**: When some classes or modules have overly close relationships, causing them to depend heavily on each other's internal details.
- **Large Class**: When a class contains too many fields/methods/lines, duplicated code cannot be far behind.
- **Alternative Classes with Different Interfaces**: When two or more classes are equivalent but with different interfaces.
- **Data Class**: These are classes that have fields, getting and setting methods for the fields, and nothing else. Such classes are dumb data holders and are often being manipulated in far too much detail by other classes.
- **Refused Bequest**: When a subclass uses only some methods or properties inherited from its parents, the hierarchy is wrong.
- **Comments**: When you feel the need to write a comment, first try to refactor the code so that any comment becomes superfluous.

# Chapter 4. Building Tests

- Make sure all tests are fully automatic and they check their own results.
- A suite of tests is a powerful bug detector that decapitates the time it takes to find bugs.
- Always make sure a test will fail when it should.
- Run tests frequently. Run those exercising the code your're working on at least every few minutes; run all tests at least daily.
- It is better to write and run incomplete tests than not to run complete tests.
- Think of boundary conditions under which things might go wrong and concentrate your tests there.
- Don't let the fear that testing can't catch all bugs stop you from writing test that catch most bugs.
- When you get a bug report, start by writing a unit test that exposes the bug.

# Chapter 5-12. Refactorings Catalog

The rest of the book is just a calatog of refactorings.
The books has a detailed description and examples, with some variants. All of them can be found here:
- https://refactoring.com/catalog/
- https://refactoring.guru/refactoring/catalog