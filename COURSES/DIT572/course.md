# GAME ENGINE ARCHITECTURE

## LEC 1 - INTRO

### Singletons - OOP pattern

3 main elements:

- Class contains a private static variable, which it will fill with an instance of itself
- It implements only private constructors, so it cannot be instantiated by any class except the one in which it is defined.
- It exposes a public static method that permits every object to ask for the object when they need it.

## LEC 2 - OOP

### Abstract classes and interfaces

### Inheritance

### Polymorphism

### Encapsulation

## LEC 3 - ARCHITECTURE

### MVC architecture

### Facade design pattern 

- All subsystems use the same common API
    - Inside the implementation of each class, we make sure this functions appropriately.

Inputs:
Drawing in input is a standard part of our game loop.

- inputListener: interface that all objects must implement in order to register their
interest in events
- inputSystem: responsible for maintaining a list of those objects that want to know
when input events trigger.
- inputEvent: which acts as an abstraction for whatever internal data structures an input layer
may use

### Observer design pattern

- InputSystem is implemented using this patterm
- connections are made in runtime

### Listener and events

- extends the inputSystem class, gives it access to the listener objects 
- it converts the data representation of the console into the
internal InputEvent of our game engine
- it doesn’t do any ‘input handling’ of its own (setters and getters only)
- 


### Game development philosophy


### Game objects

- Game objects: anything that the game includes, GameObject class is just a structural element, no state or methods. 



### Game loops

- fixed time step game loop (millisPerFrame is our frame rate.)
- 