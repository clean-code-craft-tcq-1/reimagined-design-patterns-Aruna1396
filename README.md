# reimagined-design-patterns

Give a summary description of Four design patterns that you choose from the following design patterns: **Adapter,  Builder, Composite, Decorator, Observer, Interpreter, State, Mediator, Memento, Prototype, Proxy**. In your summaries say:

- what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
- how the pattern works, what the basic idea of the pattern is
- what the main advantage and what the main disadvantage is of using this pattern
- Write a short summary for each of the four patterns, about half a page for each pattern (rather less than more). 

> Do not add diagrams, and do not try to give a complete description of the patterns as found in the books. Rather think of how you would explain the essential ideas of these patterns in a few sentences to a colleague while drinking coffee.


## Adapter Pattern

### Summary
Adapter is structural design pattern to collaborate independent, incompatible/unrelated interfaces. 
In a nutshell, it wraps/ converts the interface of a class/component into a suitable interface which is expected by a client/other class

### Intent
    "Real world is full of adapter patterns". From power plug adapters to language translaters, all have the basic intent to make one thing compatible with another without altering existing product/functionality

### Usage
This pattern is used in cases where
 - you want to integrate a new interface/class/function which is not compatible with the existing functionality
 - you want to reuse several existing subclasses that lack some common functionality that can’t be added to the superclass

### Example
One good example that I read about is for Media & Audio Players.

There is a Media player interface of class Audio Player which is having functional support for mp3. There is another library/interface AdvancedMediaPlayer interface say from 3rd party which supports formats mpv4, vlc. 
If we need to integrate into our Audio Player class, we use an adapter called Media Player adapter to implement Media Player interface & use AdvancedMediaPlayer objects to play required format
Added advantage is that AudioPlayer uses the adapter class MediaAdapter passing it the desired audio type without knowing the actual class which can play the desired format. 

### Advantages & Disadvantages
Pros:
- Single Responsibility Principle: You can separate the interface or data conversion code from the primary business logic of the program.
- Open/Closed Principle: You can introduce new types of interfaces/functionality into the program without breaking the existing code
- Re-Usability & Flexibility

Cons: The overall complexity of the code increases because you need to introduce a set of new interfaces and classes. 
Its better not to use adapter pattern when we dont actually have the need for them to keep the code simpler.


## Mediator Pattern

### Summary
It is a widely used behavioural pattern which aims at reducing direct communication between multiple objects/components by making them communicate through the mediator object.
This reduces chaotic dependencies between multiple communicating objects & many-to-many relationships thereby removing tight couplings

### Usage
This can be used when there are complex set of components/objects which are dependent on others.

### Example

Real World Scenario: Air Traffic Control System is best example of Mediator Pattern. 
Various flights do not interact directly but only with traffic controller which acts a mediator as all communication between flights goes through it

### Advantages & Disadvantages
Pros:
 - Promotes loose couplings between different objects/components as it reduces tight coupling
 - Makes the code reusable
 - Supports Open & Closed Principle
 - Flexibility - Plug in and Plug out the components at ease

Cons:
 - Since all communications are handled by a single mediator, it might become a God Object (knows too much and does too much)

## Decorator Pattern

### Summary
This structural pattern allows us to add additional functionalities dynamically without altering the existing/core functionality
The original object is wrapped by abstract wrapper interface. Then core object & decorator object will inherit from this interface, and we can keep adding more decorators as per functionality

### Example
Real World Scenario: 
Lets take an example of pizza, where the base topping remains the same and based on the customer requests & pricing additional toppings can be added.

Similarly, if we have some alert mechanism which will alert the users via mail and there is a need for other types like FB notification, SMS, Calls, we could use this decorator pattern for the addons

### Advantages & Disadvantages
Pros:
 - Supports Open-Close Principle: Ability to add more functionality dynamically without altering existing code
 - Easy plug in and plug out at run-time
 - Flexibility

Cons:
 - Usage of multiple decorators can make the maintainability difficult.
