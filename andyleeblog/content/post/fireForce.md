
+++
date = "2023-12-22"
title = "Game Development: Fire Force"
slug = "Game Development: Fire Force"
categories = [ "Post"]
tags = [ "Unity", "Particle System" ]
katex = true
+++
# introduction
Hey there, visitors! Get ready to feel the heat because I'm about to introduce you to a game that's set to turn up the temperature in the world of gaming: "Fire Force"!

In this blog post, I'm diving headfirst into the fiery world of "Fire Force." 

From its inception to its release, I'm here to give you an exclusive behind-the-scenes look at what makes "Fire Force" tick. So, buckle up and get ready to join us on this epic journey through the flames as we explore every aspect of this scorching hot game.

# Graphics and Art Style
For our game's graphics, I sourced all our assets from the `Unity Asset Store`. 

Additionally, the artwork in the game was created using `Dolle`, an AI-powered art creation tool. 

Since my focus when developing the game was to acquire skills for the Unity Engine, all the art and graphics were obtained from `external resources`.

So when you're exploring our game, it's all thanks to the Unity Asset Store and Dolle's remarkable art

# Level Design and Environments
In `Level 1`, players are introduced to the basics of firefighting as they navigate through a relatively `straightforward environment`. They'll encounter manageable fires to extinguish, simple obstacles to overcome, and a few civilians to rescue. This initial level serves as a tutorial, allowing players to familiarize themselves with the game mechanics and controls.

Once players have mastered the fundamentals, they'll advance to Level 2, where the real challenges begin. Here, they'll find themselves facing more intense fires, more obstacles, and a greater number of civilians in need of rescue. The environment becomes more complex, with narrow corridors, collapsing structures, and hidden pathways adding to the difficulty.

**Level 1 Design**
![alt](/img/game-ff/level1.PNG)

In `Level 2`, players must rely on their skills and quick thinking to effectively manage limited resources and navigate through increasingly dangerous situations. It's a test of their firefighting prowess and problem-solving abilities, pushing them to their limits as they strive to save lives and extinguish raging infernos.

With each level presenting new challenges and obstacles, players will need to adapt their strategies and approach, ensuring that every firefight is tackled with precision and efficiency. Level 2 serves as a thrilling escalation in difficulty, providing a rewarding experience for players who are up for the challenge.

**Level 2 Design**
![alt](/img/game-ff/level2.PNG) 

# System and Technology

**Door fracturing Technology**

to make it more realistic, we've implemented a `door fracture system` that activates when players attempt to break doors to extinguish fires or rescue citizens. 
To achieve this, I've implemented a method to render individual door pieces and subsequently create rigid bodies for each fragment. 

**Creating individual door fragment a rigid body** 
```c++
  void Main()
    {
        //Create rigid body borders for all 3D door pixels.  
        if(once == true)
        {
            for(int x = 0; x <  doorPerPixel; x++)
            {
                for (int y = 0; y < doorPerPixel; y++)
                {
                    for(int z = 0; z < doorPerPixel; z++)
                    {
                        CreateCube(new Vector3(x, y, z));
                    }
                }
            }
        }
    }
```

```c++
void CreateCube(Vector3 coordinates)
    {
        GameObject cube = GameObject.CreatePrimitive(PrimitiveType.Cube);
        Renderer rd = cube.GetComponent<Renderer>();
        rd.material = GetComponent<Renderer>().material;

        cube.transform.localScale = transform.localScale / doorPerPixel;

        Vector3 firstCube = transform.position - transform.localScale / 2 + cube.transform.localScale / 2;
        cube.transform.position = firstCube + Vector3.Scale(coordinates, cube.transform.localScale);
        Rigidbody rb = cube.AddComponent<Rigidbody>();
       
    }
```
Door Mesh
![alt](/img/game-ff/doorfracture.PNG) 
Door fragments
![alt](/img/game-ff/door_parts.PNG) 
Breaking the Door
![alt](/img/game-ff/door_broken.PNG) 

**Particle System**

In our game, we've implemented the power of particle systems to bring elements like fire and water to life in stunning detail. 
With dynamic particle effects, the flickering flames of a raging inferno dance realistically, immersing players in the heat of the moment. 
Meanwhile, cascading water droplets sparkle and splash, creating a sense of fluidity and motion that's truly mesmerizing. 
Whether you're battling flames or dousing fires, the particle systems in our game add a whole new level of realism and excitement to the experience. 
Get ready to be blown away by the immersive effects of fire and water like never before!

![alt](/img/game-ff/fire.PNG) 


# Gameplay and Controls

**How To Play**

Overall, our game employs standard 3D game controls that are intuitive and easy to grasp. Here's a breakdown of how to navigate through the fiery challenges of "Fire Force":

**Character Movement: WASD Keys**
```
W: Move Forward
S: Move Backward
A: Rotate Left
D: Rotate Right
Water Spray Movement: Arrow Keys on the keyboard
```

Use the arrow keys to direct the flow of your water spray. Each arrow key corresponds to a different direction, allowing you to precisely target flames and control the spread of fire.

**Water Hose On and Off: T Key**

Toggle the T key to activate or deactivate your water hose. This conserves water usage, as your water supply is limited and requires refilling once depleted.

**Weapon System: Tab Key**

In "Fire Force," you have access to a various tools, including a water hose and an axe.
Press the Tab key to switch between the water hose and the axe, depending on the situation at hand.
Utilize the water hose to douse flames and prevent further destruction.
Switch to the axe when faced with obstacles such as locked doors, allowing you to break through and progress.

**X-Ray System: C Key**

Gain a tactical advantage with the C key, which activates the X-ray system.
By pressing C, you can peer through walls, providing invaluable insights into the layout of each level and the locations of trapped civilians.

**Rescue/Heal: H Key**

Every firefighter knows that saving lives is paramount. Press the H key to initiate rescue and healing operations.
Upon approaching injured civilians, use the H key to administer aid. Once healed, civilians will autonomously navigate their way out of the building using `AI navmesh` technology, ensuring their safe escape from harm's way.

```
With these controls, you're ready to take on the infernos of "Fire Force". 
So, gear up, stay vigilant, and let's extinguish those flames together!
```

# Personal Reflections

Reflecting on my journey developing this game has been an incredible learning experience on multiple fronts.
Firstly, exploring `particle systems` has been eye-opening.
Witnessing how these effects can breathe life into elements like fire and water has been nothing short of mesmerizing. 
Learning to manipulate particle systems to create dynamic and realistic visuals has expanded my understanding of game development immensely.

Secondly, diving into the `Unity Game Engine` has been both challenging and rewarding. 
Exploring its vast `array of components`, from `physics systems` to `audio management`, has provided me with a comprehensive understanding of how to bring a game to life. 
Navigating `Unity's interface` and learning to leverage its features efficiently has been a valuable skill set that I'll carry forward in future projects.

The implementation of the `Door Fracture System` was a particularly intriguing aspect of development. 
Crafting a system that simulates the breaking and fracturing of doors added a layer of realism and immersion to the gameplay experience. 
It was a fascinating challenge to design and implement the mechanics behind this system, and seeing it come to life in the game was incredibly satisfying.

`Character movement and animation` were also key areas of focus during development. 
Learning to program fluid and responsive character movement was essential for creating an engaging gameplay experience. 
Additionally, mastering character animation techniques helped to breathe life into the game world, making the characters feel more dynamic and lifelike.

Overall, this journey has been filled with moments of discovery, challenge, and growth. 
Each aspect of development, from particle systems to character animation, has provided valuable insights and expanded my skill set as a game developer. 
I look forward to applying these newfound skills and knowledge to future projects, continuing to push the boundaries of what's possible in game development.

![alt](/img/game-ff/intro.PNG) 


## Game Download
Ready to start playing? Click the link below to clone the repository and begin your exciting adventure! 
Explore new worlds, extinguish fires, and become a hero. Your journey begins now! Download here:
> https://github.com/AndyLeeGT/FireForce




