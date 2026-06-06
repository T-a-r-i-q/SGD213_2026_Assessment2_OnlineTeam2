# Welcome to Project Brick Breaker!

This project is Sunbreak Interactive's implementation of the Client's (You) agreed upon technical specifications.
The following is a documentation brief outlining what we have done, what is implemented and how to take this template and modify it for constructing your own Mario Brothers-style levels.
This project implements the Simple 2D Platformer BE2 Unity package and will be building off of it for the project's skeleton.

## What You Need To Know

Here are some quick pointers and a high-level view of the components you will use to construct your levels. The components for constructing your levels will take two forms, the first will be in the forms of prefabs, these are objects with pre-defined characteristics we have assembled that you can simmply drag-and-drop from the Assets > Prefabs folder. The second will be the Tile Palette, a way of 'painting' your levels with a sprite sheet. The in's and out's will be explained below.

### The Player

The Player prefab is where you can change parameters for how your player controls, how high they jump, how fast they move, etc. When you add the prefab to your scene, that will be the player's initial spawn point. You can change the player's parameters at the bottom of the inspector in the Player (Script) component.

<img width="431" height="548" alt="image" src="https://github.com/user-attachments/assets/a25e0197-9d90-4387-ac2d-4d37566c3959" />

### Painting your Levels

#### The Setup
The first step when creating a new scene is adding a Tile Map. This can be done by using your toolbar GameObject > 2D Object > TileMap > Rectangular 
or by right clicking in your scene heirarchy and selecting 2D Object > TileMap > Rectangular.

<img width="833" height="717" alt="image" src="https://github.com/user-attachments/assets/5cdb1712-c73d-457d-8358-ec8cac117f0b" />

Next, we use the Tile Palette located under Window > 2D > Tile Palette and add a sprite sheet for painting.

<img width="544" height="483" alt="image" src="https://github.com/user-attachments/assets/d18314d3-43be-4899-b172-8cc44bc24456" />
<img width="460" height="432" alt="image" src="https://github.com/user-attachments/assets/9c33dfa6-5f23-48e6-9018-1834ee53679e" />

#### Adding your Own Art

Click and drag the Platforms collection from the sprites folder into the Tile Palette and set a new folder for your palette to be stored. You can edit or make your own tiles, the size is based around a 1x1 Unity unit, the pixel density you can change on the sprite import under Pixels Per Unit. This project is using a 16 bit Tile Map.

<img width="522" height="885" alt="image" src="https://github.com/user-attachments/assets/7be2c1b5-cf0e-4cab-b458-14da91f02d9c" />

#### Start Painting!

To start creating your world, simmply go to your Tile Palette with your imported Tile Map, click and drag over the cells you would like to sample, then click in your scene view to ass the sampled tile into your scene.

<img width="1672" height="484" alt="image" src="https://github.com/user-attachments/assets/8389df71-e450-4dd4-bdda-9fc5146c2306" />

To make the ground walkable, select the Tile Map layer from your object Hierarchy, click Add Component in the Inspector, then search for Tilemap Collider 2D

<img width="515" height="746" alt="image" src="https://github.com/user-attachments/assets/c4bba4a0-be59-4c36-88c1-6421bfee87db" />

Note as well, under the Tilemap Renderer's Addistional Settings is Sorting Layers, which can help to layer multiple Tile Maps, similar to Photoshop Layers, only in reverse, layers that are furthur down the heirarchy will render on-top of everything above it.

<img width="1640" height="735" alt="image" src="https://github.com/user-attachments/assets/d362ab94-b4a3-4611-9f61-92bbb5811974" />

You can add different layers by simply adding another TileMap to your Grid object in your Hierarchy, perfect for creating layering through backgrounds and foregrounds.

### Moving Platforms

Now we've started building a level, let's start adding some of the prefabs and explaining how they work. The following prefab assets can be found in the Assets > Prefabs folder, and are added into the scene by simmply clicking and dragging them in; the first is the Moving Platform prefab. Once this is in your scene, you can exapand the object within the Heirarchy to see a Container that holds the script, collision and the sprites used for the platform, and two 'Points' that are represented by a diamond and circle in the Scene view.

<img width="882" height="571" alt="image" src="https://github.com/user-attachments/assets/fbebebb5-22d0-4bdc-8854-72dc9f1b3d92" />

By default, this platform moves pretty slowly between two points, for customisation, you can move the two points to change where the platform will go between. If you would like to add another point, expand the Ponts tab under the Moving Platform scrips in the Container, click the plus and create a new empty game object under the Moving Platform object (NOT THE CONTAINER!). Move it where you want the platform to translate to, then click and drag it into the new Element line you've created in the Moving Platform script. The platform will now cycle between three points.

<img width="1589" height="622" alt="image" src="https://github.com/user-attachments/assets/54fbf7e4-fd5d-4a1b-ac70-6647b7a63ef8" />

To distinguish where your new point is, you can change the Icon for it in the Inspector.

<img width="1583" height="634" alt="image" src="https://github.com/user-attachments/assets/d2d228a9-06c4-4c48-b7b0-05f6d19f3fda" />

### Hazards

The spike hazards will immediately kill the player on collision. If you'd like to edit any collision hit-boxes, it is done through the Collider component on the object. In the demo given, these traps are using basic box colliders, however, if you would like more fidelity, you may opt to use a Polygon Collider which you can manipulate much more freely by using the Edit Collider tool in the Inspector. If you make this change, be sure to click the 'Is Trigger' tickbox in the new Collider, otherwise the spike won't be so hazardous!

<img width="1129" height="625" alt="image" src="https://github.com/user-attachments/assets/5a5caa39-1932-4436-8509-7aa670cd3578" />

#### Changing Sprites

Hazards in this demo take the form of spikes. To change sprites for any of these prefabs, use the Sprite Renderer component in the object's Inspector, click on the circle selection next to Sprite and select your own asset to change the sprite.

<img width="322" height="639" alt="image" src="https://github.com/user-attachments/assets/33776690-e891-4ec2-8f86-25706f14c6b3" />

### Enemies

Enemies are a combination of the Hazards and Moving Platform. Functionally, to change how they move, it is the same method as the moving platform. Instead of only moving the points individually, it is recommended to set both the EnemyContainer and the point you'd wish to move to x=0 and y=0, then move the two of them together. This way, you are able to see where the enemy will end up when it reaches its destination, rather than having to guess. Do note that the enemies do not respect collision with your environment, it will be up to your own finesse to make sure they look like they're walking, or floating, up to you.

<img width="1603" height="619" alt="image" src="https://github.com/user-attachments/assets/c5275f39-76f4-4304-8447-d3b5bf919a6d" />

Enemies are also able to be killed by jumping on them, just like Mario!

### Powerups

As an extension to the brief, a basic powerup system has been included through either free-standing powerups or an Item Box the player had hit from the bottom to spawn a powerup. Currently there are 4 powerups; Double Jump, Low Gravity, Speed Boost and an Extra Life. Which power you get is random and will expire after 10 seconds.

<img width="1175" height="580" alt="image" src="https://github.com/user-attachments/assets/6e05d787-b26c-4e10-9f1c-8589a8a18d55" />



