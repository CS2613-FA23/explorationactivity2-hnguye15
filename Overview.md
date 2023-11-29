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
Asynchronous programming was implemented by the language F# first then from there on, a lot more languages have started to adopt this programming style, especially C#, which was the first mainstream language that popularized the async/await keywords [[ref]](https://dev.to/maxarshinov/a-brief-history-of-asyncawait-264j).

As for the Promise object used alongside the module, according to risingstack.com, "the current JavaScript Promise specifications date back to 2012 and available from ES6 – however Promises were not invented by the JavaScript community. The term comes from Daniel P. Friedman from 1976 [[ref]](https://blog.risingstack.com/asynchronous-javascript/)."

## Reasons for Selection
At the start of this term, I had a small passion project that was brewing in my thoughts even during last Summer. So, I told myself "why not sit down and learn something new that you like?". From then on, I have been following a series of video on Youtube on how to make a web-based incremental game like Cookie Clicker as a base for my game ([link to the series](https://www.youtube.com/playlist?list=PLEyTwruuVAqlEvj8QxTFdVPc6_AwpgF2w)). The game is a combination of HTML and JavaScript: HTML for the front-end presentation, and JavaScript for the back-end handling of logics. I also planned to add CSS to the game for better graphics, but I digress. At first, I never had the intention of using this game for my first exploration activity in this class, but because of how much we learn about JavaScript in this class and the code of my game is also mainly written with JavaScript, I found that it was a perfect candidate for this opportunity to showcase my game.

As I continued further down the development line, I stumbled upon asynchronous programming (AP), namely, JavaScript's Async.js utility module. AP at first was very confusing for me with the async/await thing, but as I took more time familiarizing myself with the module and work with it, it started to become clearer to me. Although I felt like I only learned a small corner of the module, I am proud that it is something I can put into great use in the future for my other projects not just as games. For the development of my game, instead of sticking to a traditional clicker incremental game, I leaned towards more its idle sub-genre that involves a very lot of automations and multiple tasks running in the background. This is where the Async.js module shines the brightest! By using this module, I feel that coding my game is much easier and simpler while still able to maintain efficiency.

## The Learning Curve
Personally, all of the struggle working with this particular language really did pay off for me because I learn a lot from making mistakes and I cannot emphasize on this enough. At first, I would go blind into the language, then figure things out in bits and pieces. Debugging is a very common thing when you learn a new language because of how many errors you make because of difference in syntax, logic, and other resources like libraries and things alike. But, as you learn and make more mistakes, it slowly grows onto you. For example, at first, I literally had no idea how this Async.js utility module works. I basically went ahead and used it blindly until there were a lot of errors popping up that I had to resolve. So, I would say that looking at the bugs from your code and figuring them out yourself plays a huge role in learning, especially when there's nobody there to point them out for you because it's your code after all and nobody knows your code more than you do. As such, implementing the module and understanding it was quite a challenge, but was a very successful challenge. Now I mostly know how to program asynchronously and handle multiple tasks in the background to aid with the tasks in the foreground.

## Personal Experience
Overall, I would totally recommend this type of programming to everyone as it is a very useful one. I also bet that asynchronous programming is very widely used and very heavily implemented in many programs. It is something that everyone should at least have their experience with at least once as a programmer.

On a side note, I will probably be working more with this module in the future. Maybe, I will hopefully finish developing the game with many more features to come!
