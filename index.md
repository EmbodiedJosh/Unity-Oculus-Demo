## "Build Your First VR App" Video Tutorial

[![](https://cdn.discordapp.com/attachments/626114024655945740/626464011193417730/oculsu-rift-unity-pro-1021x580.jpg)](https://youtu.be/tPHnLJ__Cd4)

<figure class="video_container">
  <video controls="true" allowfullscreen="true" poster="path/to/poster_image.png">
    <source src="path/to/video.mp4" type="video/mp4">
    <source src="path/to/video.ogg" type="video/ogg">
    <source src="path/to/video.webm" type="video/webm">
  </video>
</figure>



This following is my interpreation of recreating **[existing Oculus VR Documentation](https://developer.oculus.com/documentation/unity/unity-tutorial/?locale=en_US)**. I also created a **[video tutorial version](https://www.youtube.com/watch?v=tPHnLJ__Cd4&feature=youtu.be)** based off the original. The goal of both the video and the following documentation was to consolidate multiple pages and links of documentation into one.

### Build Your Simple Application 

In this tutorial we're going to create a simple game comprised of moving a ball within a play area. We'll create some walls so the ball doesn't roll out of the play area, in addition to attaching a controller script so we can move the ball around with our keyboard. At the end, we'll enable VR support so we can play our creation on Rift. 


### Step 1: Set Up Your Rift

Before you can make a game for Rift in Unity, you need to ensure your Rift is set up properly. Follow the instructions at [Oculus.com/setup](https://www.oculus.com/setup/) to get your Rift running in working order. Once this is completed, be sure that you're using Unity 5 to create your VR Game ([you can check compatibility and version requirements and recommendations  here](https://developer.oculus.com/documentation/unity/latest/concepts/unity-req/)).

[![](https://cdn.discordapp.com/attachments/626114024655945740/626476627001475072/84dae01801cd0ac8aa88caf657190e07.png)](https://www.oculus.com/setup/)

### Step 2: Build a Play Area and Add a Player 

1. Launch Unity Hub, and create "new". Once there, select 3D, and give it a name. We'll call it VR_Game. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626486430935416894/df98eb42f64973a31a4644de137c8821.png)](https://cdn.discordapp.com/attachments/626114024655945740/626486430935416894/df98eb42f64973a31a4644de137c8821.png)

2. First things first, we need to create a floor. Go to **Game Objects > 3D Object > Plane** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626488372906688516/fa05fe00e824d2e3f5cd86845238c2cd.png)](https://cdn.discordapp.com/attachments/626114024655945740/626488372906688516/fa05fe00e824d2e3f5cd86845238c2cd.png)

3. Then, do the same thing, but this time add a **sphere**. **Game Objects > 3D Object > Sphere** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626489828032118784/e13156e016600ba1baea8137c4dc4b87.png)](https://cdn.discordapp.com/attachments/626114024655945740/626489828032118784/e13156e016600ba1baea8137c4dc4b87.png)

4. If you notice, there's an array of arrows at the center of your sphere. This array changes depending on what tool is currently being highlighted. These tools are located towards the top, and have corresponding keyboard shortcuts. 

* **W = Move Tool** 
* **E = Rotate Tool** 
* **R = Scale Tool** 

Move the ball up to hover above the plane by **dragging up on the green arrow. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626492729970524190/3.png)](https://cdn.discordapp.com/attachments/626114024655945740/626492729970524190/3.png)

5. If we hit "play", we'll see that the sphere hovers in the air. This is because it's immune to Unity's physics engine: we can't move it, and it can't be moved. Turn off the game by pressing "play" again. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626495984481861634/c2bfa3b78065305f8d5f69c3e61f37ff.png)](https://cdn.discordapp.com/attachments/626114024655945740/626495984481861634/c2bfa3b78065305f8d5f69c3e61f37ff.png)

6. To bring it to life, we have to add a **RigidBody** component to our "Player", in this case, the sphere. 

* Click **Add Component**

[![](https://cdn.discordapp.com/attachments/626114024655945740/626497830617350144/5.png)](https://cdn.discordapp.com/attachments/626114024655945740/626497830617350144/5.png)

* Type in "RigidBody" and select it. Now, if you press play again, you'll notice the **ball drops to the ground.**


[![](https://cdn.discordapp.com/attachments/626114024655945740/626497830118359050/7.png)](https://cdn.discordapp.com/attachments/626114024655945740/626497830118359050/7.png)


[![](https://cdn.discordapp.com/attachments/626114024655945740/626501747103367179/e4e435b64b648f39c1acffb5064173da.png)](https://cdn.discordapp.com/attachments/626114024655945740/626501747103367179/e4e435b64b648f39c1acffb5064173da.png)

### Step 3: Add a control script to your Player 

1. Now we need to make our player be able to move and respond to input from our keyboard. We already started this process by adding RigidBody, but that's only half the battle. The second part of the equation is creating a **New Script**. 

* Go to the same section as before, and click **Add Component** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626497830617350144/5.png)](https://cdn.discordapp.com/attachments/626114024655945740/626497830617350144/5.png)

* Type in "New Script" and select it. We're going to name it **PlayerController** and then click "Create and Add"


[![](https://cdn.discordapp.com/attachments/626114024655945740/626540888339775508/8.png)](https://cdn.discordapp.com/attachments/626114024655945740/626540888339775508/8.png)

[![](https://cdn.discordapp.com/attachments/626114024655945740/626541578327949336/9.png)](https://cdn.discordapp.com/attachments/626114024655945740/626541578327949336/9.png)

2. Your new script will appear in your Assets Folder, right next to "Scenes". **Double click it to open it with the text editor Visual Studio**, which is the standard text editor that's installed with Unity. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626542214381699082/10.png)](https://cdn.discordapp.com/attachments/626114024655945740/626542214381699082/10.png)

 * You should see this screen, **with this starting code**.
 
 ```
 using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class temp : MonoBehaviour {
// Use this for initialization
    void Start () {
    }
// Update is called once per frame
    void Update () {
    }
}
```
 
 [![](https://cdn.discordapp.com/attachments/626114024655945740/626543047420936209/76d69e3ea4133dff5ec8fcef1f04b13a.png)](https://cdn.discordapp.com/attachments/626114024655945740/626543047420936209/76d69e3ea4133dff5ec8fcef1f04b13a.png)

3. Next we're going to **add a new function** to move our Player (the sphere). Copy and paste this in its entirety into Visual Studio (beginner) or enter in the function manually (advanced). 

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class PlayerController : MonoBehaviour {
public int speed = 0;
// Use this for initialization
   void Start () {
  }
// Update is called once per frame
   void Update () {
// get input data from keyboard or controller
     float moveHorizontal = Input.GetAxis("Horizontal");
     float moveVertical = Input.GetAxis("Vertical");
// update player position based on input
      Vector3 position = transform.position;
      position.x += moveHorizontal * speed * Time.deltaTime;
      position.z += moveVertical * speed * Time.deltaTime;
      transform.position = position;
      }
  }
  
  ```

* **Your final code in Visual Studio should look like this:** 

 [![](https://cdn.discordapp.com/attachments/626114024655945740/626545019020378113/182806c6f89e63c63947e05b89c23a9e.png)](https://cdn.discordapp.com/attachments/626114024655945740/626545019020378113/182806c6f89e63c63947e05b89c23a9e.png)
 
 
### Step 4: Set Speed and Update Play Area 

1. Congratulations! **Save and exit out of Visual Studio and hit "play" in Unity**, and discover that you're still unable to move using W-A-S-D. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626497830118359050/7.png)](https://cdn.discordapp.com/attachments/626114024655945740/626497830118359050/7.png)

2. Click on your "sphere" in the Hierarchy and notice you now have a "speed" section under the Inspector tab. It is currently set to "0". That's why you're not moving. **Set that a reasonable number (3)**, hit play again, and finally be able to move your Player using W-A-S-D. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626547334150488087/11.png)](https://cdn.discordapp.com/attachments/626114024655945740/626547334150488087/11.png)

3. As you may have noticed, you now have the power to run your Player off the edge of the plane and outside of your Play Area. To fix this, we're going to add borders along the edge so we don't fall off. Go to **Game Object > 3D Object > Cube** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626549443092676619/114f1bf426ae524689935170e35ca113.png)](https://cdn.discordapp.com/attachments/626114024655945740/626549443092676619/114f1bf426ae524689935170e35ca113.png)

* **Press R** to activate the scale tool. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626550314035707932/a72934ac36a4d908ce3d126b88ab06ad.png)](https://cdn.discordapp.com/attachments/626114024655945740/626550314035707932/a72934ac36a4d908ce3d126b88ab06ad.png)

* **Click and drag out on the X Axis (red)** to expand the cube into a rectangle. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626550316682444810/1d044b0733ac5b6b53e94837e5043602.png)](https://cdn.discordapp.com/attachments/626114024655945740/626550316682444810/1d044b0733ac5b6b53e94837e5043602.png)

* **Press W** to activate the move tool, and move your rectangle along the z (blue) and y (green) axis to line it up to the edge of the plane. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626550313389654017/03d5ae084d41d647368b0bc91d7da704.png)](https://cdn.discordapp.com/attachments/626114024655945740/626550313389654017/03d5ae084d41d647368b0bc91d7da704.png)

* To better line up your rectange, **press Alt + Left Mouse Click** inside the viewport, to move the camera. This allows you to get views like this: 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626550316451627008/7d62b3a0b8b92087af8fd5e78c6d8300.png)](https://cdn.discordapp.com/attachments/626114024655945740/626550316451627008/7d62b3a0b8b92087af8fd5e78c6d8300.png)

4. Great! You've now **Free Transformed** a rectangle in 3D space, and you're going to do it again. This time though, we're going to save some time. **Right click your cube and select "Duplicate"**. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626552071084179466/93e442acac55979285dedcc2d40ffbb9.png)](https://cdn.discordapp.com/attachments/626114024655945740/626552071084179466/93e442acac55979285dedcc2d40ffbb9.png)

5. **Free Transform Cube (1)** to the opposite side of the plane by moving it along the Z Axis (blue) using the Move Tool (w).  

[![](https://cdn.discordapp.com/attachments/626114024655945740/626552616926707712/2be7ae9b7ee0dc42e815ad3f3023c5cd.png)](https://cdn.discordapp.com/attachments/626114024655945740/626552616926707712/2be7ae9b7ee0dc42e815ad3f3023c5cd.png)

6. **Select both cubes, and duplicate them**. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626553482907746325/3faad105de59f47bf5dec1d5bb437a9d.png)](https://cdn.discordapp.com/attachments/626114024655945740/626553482907746325/3faad105de59f47bf5dec1d5bb437a9d.png)

7. **Press E with Cube(2) and Cube(3) selected to use the Rotate Tool** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626554339196010508/3d73f0e287eea45f4438ab902d31f897.png)](https://cdn.discordapp.com/attachments/626114024655945740/626554339196010508/3d73f0e287eea45f4438ab902d31f897.png)

* **Rotate on the Y Axis** (green) until they line up with the last two sides of the plane. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626554337228881930/eb0613c67e84847394c187b934e412ce.png)](https://cdn.discordapp.com/attachments/626114024655945740/626554337228881930/eb0613c67e84847394c187b934e412ce.png)

8. **Rotate the View Port** using Alt + Left Mouse Click to get a better view and look at your enclosed Play Area! 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626554796899303467/384b0c40daac7157623aa8ee1efc1978.png)](https://cdn.discordapp.com/attachments/626114024655945740/626554796899303467/384b0c40daac7157623aa8ee1efc1978.png)


9. But just because you can fly around in 3D space and see your enclosed Play Space, doesn't mean the Game Camera can. **Left Mouse Click on the camera icon** and use Free Transform and the preview window to get a better playing angle. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626556242416107551/12.png)](https://cdn.discordapp.com/attachments/626114024655945740/626556242416107551/12.png)


### Step 5: Modify your project for VR 

1. Now that we can play our game regularly, it's time to add in VR capability. Go to **Edit > Project Settings > Player > XR Settings** to see this screen and check the box that says **"Virtual Reality Supported"** 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626557848553390081/13.png)](https://cdn.discordapp.com/attachments/626114024655945740/626557848553390081/13.png)

2. Once clicked, it'll take some time to load, but then you will see this screen. Leave everything the way it is, but notice the tab **"Open VR"** and how there's no check-box by it. 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626558182646611970/d8bfd0c167b6499651c21e0c7f1ef769.png)](https://cdn.discordapp.com/attachments/626114024655945740/626558182646611970/d8bfd0c167b6499651c21e0c7f1ef769.png)

3. You need Open VR in order to run your game: it's what tells your Oculus Rift to turn on and see the game you've just made. **The only way to turn on this check-box is if you have Steam VR installed**. To install Steam VR, simply open Steam with your Oculus fully operational and already set up. Steam will then say it detects a VR headset, and ask if you want to download Steam VR. Say yes. The graphic will look similar to this image: 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626558811754332162/add98f7710fc5243d3310e79a55a9dc47aeb1c22.png)](https://cdn.discordapp.com/attachments/626114024655945740/626558811754332162/add98f7710fc5243d3310e79a55a9dc47aeb1c22.png)

* If you attempt to run your game without Steam VR, you will encounter this error: 

[![](https://cdn.discordapp.com/attachments/626114024655945740/626559295466504223/5e34a56d7d24dd9b9b72228c981d0623.png)](https://cdn.discordapp.com/attachments/626114024655945740/626559295466504223/5e34a56d7d24dd9b9b72228c981d0623.png)
* **To fix this error, you need simply install Steam VR.**


### That's it! 

Congratulations on making your first VR application. I can't wait to see what you make next! 


