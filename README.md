#Welcome to Project Brick Breaker!

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



### Hazards

### Powerups

### Enemies

### Changing Sprites
