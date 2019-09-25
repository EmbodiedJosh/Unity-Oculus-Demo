## "Build Your First VR App" Video Tutorial

[![](https://cdn.discordapp.com/attachments/626114024655945740/626464011193417730/oculsu-rift-unity-pro-1021x580.jpg)](https://youtu.be/tPHnLJ__Cd4)



The above video tutorial and subsequent text was created for the purpose of consolidating and converting multiple Unity+Oculus development documentation pages into a video tutorial with only one subsequent page of documentation. The following is the technical writing documentation of how I would write "Tutorial: build your first VR app" for the Oculus Rift. 

At the bottom is a summary of my experience follwing the existing documentation (and a list of the documentation I used), along with the problems I encountered (and overcame) along the way. 

### Build Your Simple Application 

In this tutorial we're going to create a simple game comprised of moving a ball within a play area. We'll create some walls so the ball doesn't roll out of the play area, in addition to attaching a controller script so we can move the ball around with our keyboard. At the end, we'll enable VR support so we can play our creation on Rift. 


### Step 1: Set Up Your Rift

Before you can make a game for Rift in Unity, you need to ensure your Rift is set up properly. Follow the instructions at [Oculus.com/setup](https://www.oculus.com/setup/) to get your Rift running in working order. Once this is completed, be sure that you're using Unity 5 to create your VR Game ([you can check compatibility and version requirements and recommendations  here](https://developer.oculus.com/documentation/unity/latest/concepts/unity-req/)).

[![](https://cdn.discordapp.com/attachments/626114024655945740/626476627001475072/84dae01801cd0ac8aa88caf657190e07.png)](https://www.oculus.com/setup/)

### Step 2: Build a Play Area and Add a Player 

1. Launch Unity Hub, and create "new". Once there, select 3D, and give it a name. We'll call it VR Game. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626486430935416894/df98eb42f64973a31a4644de137c8821.png)]
(https://cdn.discordapp.com/attachments/626114024655945740/626486430935416894/df98eb42f64973a31a4644de137c8821.png)

2. First things first, we need to create a floor. Go to **Game Objects > 3D Object > Plane** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626488372906688516/fa05fe00e824d2e3f5cd86845238c2cd.png)]
(https://cdn.discordapp.com/attachments/626114024655945740/626488372906688516/fa05fe00e824d2e3f5cd86845238c2cd.png)

3. Then, do the same thing, but this time add a **sphere**. **Game Objects > 3D Object > Sphere** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626489828032118784/e13156e016600ba1baea8137c4dc4b87.png)]
(https://cdn.discordapp.com/attachments/626114024655945740/626489828032118784/e13156e016600ba1baea8137c4dc4b87.png)

4. If you notice, there's an array of arrows at the center of your sphere. This array changes depending on what tool is currently being highlighted. These tools are located towards the top, and have corresponding keyboard shortcuts. 

* **W = Move Tool** 
* **E = Rotate Tool** 
* **R = Scale Tool** 

Move the ball up to hover above the plane by dragging up on the green arrow. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626492729970524190/3.png)]
(https://cdn.discordapp.com/attachments/626114024655945740/626492729970524190/3.png)

