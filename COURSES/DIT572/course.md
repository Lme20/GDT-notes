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

## LEC4 - Proper text & input

### SDL2

- SDL2 directory provides a number functions that make calls to DLL files
- building in c# involves working with pointers and return values rather than raw data like in C++

displayText class

- functions: initialize, clearDisplay, display, showText (text), showText (arrays).
- creating a window in SDL:
  - process: create window, create renderer, set draw mode, set current colour of "pen".
- implement a "buffer" for coordination between middleware and the egnine
- the Game class may issue instrctuions to SDL
- maintain a list of drawing instructions in the renderer process
- SDL includes requirements for fonts and lblText, it uses a form of batch rendering
- textDetails: stores string, location,
- text is displayed through what's called a "surface"
- fonts are loader through a utility function
- Momoisation: optimisation technique that acts as a form of cache.
- Drawing text: uses the showText function, display function is called when the game loop determines a render is required
  - In turn, will call the update function and then the draw function
- InputFramework: class that handles incoming input via SDL
  - to represent key presses: use int codes, raw values populate key field of inputEvent with int codes
- 100 * deltaTime, FPS to 100
- Clear the Display & Render the Screen –> DisplayText
- Update the Game & Update all Game Objects –> buffering of draw calls in objects
- Get Input –> InputFramework
- Sleep –> our new game loop timing structure
-

## LEC 5 Sprites, textures and transforms

### Sprites

### Transform class

### Textures

### Graphics subsystem

- DispaySDL extends from DisplayText, acts within a loop for rendering
  - register sprites to draw them
- Graphics in SDL are handled as textures
- we use 2 buffers here, and then during our render stop (the display method) we’ll put each of those sprites, in turn, on the screen with the cached texture they are using.

### Loading texture

- When a texture is loaded, we use its height and width
  information to populate those fields in the transform.
  • This way though ensures that developers don’t need to
  look up size information themselves.
- they can handle sizing through scaling, which we’ll see
  in a bit
  • Also note that we’re still stuck using IntPtr, and using
  that as input to SDL utility functions.
- But also note that this doesn’t actually set a texture.
- it just gets width and height information

As part of this process we also handle our memoisation.

- If the texture is already buffered, just return that previous
  loaded one.
- This is an overloaded method – the previous loadTexture
  function makes use of it too

### Displaying each sprite

We now require every game object – that wants to be drawn on the screen – to
register its interest and provide its transform.
• And we store that in a list of transforms (_toDraw) that we’ll iterate over.
• We’ll also pre-warm the texture, loading it if necessary but not using it.
• Again we’re doing something here that we’ve seen before.
• Copying our sprite information on top of the screen, which needs us to say
which parts we intend to overwrite.
• sRect represents the size of the sprite.
• We grab the full sprite, starting at the top left (0,0)
• tRect represents the region of the display where we are putting it.
• The X and Y there represent ‘world co-ordinates’
• SDL_RenderCopyEx handles copying the texture into the render buffer.
• IntPtr.Zero marks the point around which we’ll rotate.
• And the flip settings determine... well, flipping

### surfices and textures

Mostly for Shard you just need to be aware of what the graphics subsystem is doing.

- Unless you want to get your hands inside and ferret around.
- A surface is the SDL term for the collection of pixels along with the metadata needed to render it.
  - Surfaces are handled in software, so they are CPU intensive to process.
  - Textures are context specific, hardware accelerated version of a surface.
    • They’re offloaded onto the GPU, which makes them much faster to work with.
    • They can take advantage of acceleration, because they get stored as close as possible to the memory inside the video
    card.
    • Certain operations, such as alpha blending, anti-aliasing and so on are best performed on a surface.
    • You can convert Textures and Surfaces forwards and backwards.

### Directions

We can only really decide on a direction when a transform rotates.

- So every time it rotates, we are going to calculate the X and Y values
  needed to go forward based on that rotation.
- All it needs is a little bit of trigonometry.
- Our rotation is stored in angles, so we’ll need to first convert it into
  radians.
- Then we get the Sine of the angle and the Cosine of the angle
- The X of ‘forward’ is the cosine, the ‘Y’ of forward is the sine.
- We’ll expose this as a property:
  - myObj.Transform.Forward will give access to this direction, and we can
    use that for our spaceship.
  - We can calculate backward by simply multiplying forward by -1.

```c#
if (up) {
    dir = this.Transform.Forward;
}
if (down) {
    dir = this.Transform.Forward;
    dir.multiply (-1);
}
if (dir != null) {
    Vector newDir =
            new Vector(dir.X, dir.Y);
    newDir.multiply(( float)speed *
        (float)Bootstrap.getDeltaTime());

    this.Transform.translate (newDir);
    }
}
```

### Left and right

```c#
public void translate (double nx, double ny) {
    x += nx;
    y += ny;
    centre.X = ( float)(x + ((this.Wid) / 2));
    centre.Y = ( float)(y + ((this.Ht) / 2));
}
```

Right is calculated as a right angle to the Y of Forward:
• right.X = -1 * forward.Y;
• right.Y = forward.X;
• Left is the -1 calculation of right.

### Game Object lifecycle management

