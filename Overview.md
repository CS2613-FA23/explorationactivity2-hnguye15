# Package/Library Overview
## Package/Library
For this Exploration Activity 2, I will be using Pixi.js module to build Exploration Activity 1 from scratch while keeping some of its core functionality. I will also be giving it a more polished UI, adding textures, animations, an a tiny bit of lore. 

## Pixi.js
### Purpose
Pixi.js is a module primarily used for UI, graphics, and animations. According to their website, "PixiJS is a rendering system that uses WebGL (or optionally Canvas) to display images and other 2D visual content. It provides a full scene graph (a hierarchy of objects to render), and provides interaction support to enable handling click and touch events [[ref]](https://pixijs.com/guides/basics/what-pixijs-is)." For this program, the module is mainly used to handle multiple displays, events, and animations.

### Usage/Functionality
With Pixi.js, you can automatically set up an HTML <canvas> element that is ready to be configured. In this element, the user can create a root container that contains everything that needs displayed. This container is an object called "Stage" [[ref]](https://medium.com/@dancripps/pixi-js-usage-and-application-5cc8e2c58a2a). The syntax to create this root container is as simple as:

    //Create a Pixi Application
    const app = new PIXI.Application({width: 200, height: 200});

    //Add the canvas to HTML document
    document.body.appendChild(app.view);

This creates a 200x200px black square canvas element. You can also style this element using CSS:

    app.renderer.view.style.position = "absolute";
    app.renderer.view.style.display = "block";
    app.renderer.autoResize = true;
    app.renderer.resize(window.innerWidth, window.innerHeight);

This is not done yet as you can also load sprites for animations and more interactivity. These "sprites" are just basically images of which attributes you can modify. According to Medium.com, there are currently 3 ways to create sprites [[ref]](https://medium.com/@dancripps/pixi-js-usage-and-application-5cc8e2c58a2a):
- From a single image file.
- From a sub-image on a tileset.
- From a texture atlas

Due to Pixi rendering its images on the GPU with WebGL, the images need to be formated so that they are compatible for the GPU. A formated image is called a texture, and this texture needs to be converted into a WebGL texture [[ref]](https://medium.com/@dancripps/pixi-js-usage-and-application-5cc8e2c58a2a). The following is the syntax:

    let texture = PIXI.utils.TextureCache["images/anySpriteImage.png"];
    let sprite = new PIXI.Sprite(texture);

After conversion of the image, the image should then be loaded by a loader function:

    PIXI.loader
        .add("images/anyImage.png")
        .load(setup);

    function setup() {
        let sprite = new PIXI.Sprite(
            PIXI.loader.resources["images/anyImage.png"].texture
        );
    }

#### Example
This example creates a blue background with a rabbit spinning in the middle [[ref]](https://pixijs.com/examples/sprite/basic). Cute, isn't it?

    import * as PIXI from 'pixi.js';

    const app = new PIXI.Application({ background: '#1099bb', resizeTo: window });

    document.body.appendChild(app.view);

    // create a new Sprite from an image path
    const bunny = PIXI.Sprite.from('https://pixijs.com/assets/bunny.png');
    
    // center the sprite's anchor point
    bunny.anchor.set(0.5);
    
    // move the sprite to the center of the screen
    bunny.x = app.screen.width / 2;
    bunny.y = app.screen.height / 2;

    app.stage.addChild(bunny);
    
    // Listen for animate update
    app.ticker.add((delta) =>
    {
        // just for fun, let's rotate mr rabbit a little
        // delta is 1 if running at 100% performance
        // creates frame-independent transformation
        bunny.rotation += 0.1 * delta;
    });
    
## Origin
According to Honeypot.io, Pixi.js is a free open-source 2D engine used to make animated websites and HTML5 games.It can be used on all modern browsers - on both desktop and mobile. It was launched in February 2013 by Matt Groves and is free under MIT license. Since then it has steadily expanded its features and has been picked up in projects by companies such as like Disney, PBS Kids, BBC, McDonalds and others. Many games companies in Berlin and Hamburg have also started to use Pixi within their tech stack. Version 3 was released in April 2015 [[ref]](https://blog.honeypot.io/pixi.js-is-the-german-gaming-industrys-newest-friend/).

## Reasons for Selection
As I developed my game further from Exploration Activity 1, I came across this useful module called Pixi.js. My game looked like it was barebones, so I told myself "why not?". As Pixi.js was made specifically for 2D games, especially web-based games, it was a perfect match for my game that does not require much other than pointing and clicking elements. Thanks to its libraries, I was able to utilize useful objects, methods, and functions to make my game look more aesthetically pleasing with a splash of lore to it. On top of that, it is a fast rendering module that uses GPU to process "sprites".

## The Learning Curve
Personally, I went into this module blind, but that was kind of a mistake. The reason is that I was struggling to set the module up for operation, struggling to find the correct methods/functions for my specific cases. However, I find that syntax of the module are very easy to understand and that helped me familiarize myself with the module fairly quickly. The things that took so much time for me to work on are writing the displays of multiple containers and elements within as I was being hyper-specific about the layout of the game. However, the implementation of the logic behind those elements are very quick and easy.

## Personal Experience
Overall, I would totally recommend Pixi.js to anyone who is looking for making an interactive website or even a web-based game that I am currently working on. I found that however tedious some of the implementations of it were, I still very much enjoyed the process of making something so much fun. It is something that everyone should at least have their experience with at least once as a programmer.

On a side note, I will probably be working more with this module in the future. Maybe, I will hopefully finish developing the game with many more features to come!
