# Render

## Modelling Process

This task was to create our designed dioramas and render a picture of the entire model. Using the software Maya, it was possible to model each separate object from scratch. Eight modelled objects needed to be created, each one was created in separate Maya project files to allow for version control on the local system. Having each model created in their own file allowed for experimentation, room for failure and optimisation of each model without it affecting the others. It was then all imported into one project file for the final render. 
The modelled objects were designed to be low poly objects. This design idea was to be done to create objects that did not have that many polygons. This was to allow for the future inclusion of each object with each other so that they will not crash the system by keeping the number of polygons low. The low poly count allowed the files to use less storage space to allow easier upload to GitLab. As well, the design was to account for the future work in the interaction part. These low poly objects were all put through the "Harden edges" tool to create more prominent edges.
The objects modelled were:

### Modelled Objects

**Temple:**
The Temple was the first model created for the coursework. It was the biggest model and took the longest to complete. The model was completed with multiple references showing the front, back, sides and floor plan of the temple. The references were images of both drawings and real-life images, they helped create the size, shape and distribution of objects within the temple (Appendix A shows references being used). The model itself used polygon shapes cube and cylinder as the main starting objects. The cube was used to build the temple steps, column bases, temple interior, and the roof. All these objects used the tools of scaling, edge loops and extruding (thickness and offset) to create these pieces of the temple. Each piece was sized and matched against the reference material. The cylinder was used to create the columns. This was done by scaling the cylinder up to reference material, increasing the number of edges around the cylinder, and selecting evenly spaced edges to then scale them out to create the bumpy effect of the column. Using the tool duplication special allowed to duplicate the columns a varying number of times and also transforming them as its duplicated meaning they were placed into their correct position as they were duplicated. This meant removing some of the columns, but overall, it saved time than duplicating them separately.

**Rocks:**
The Rocks did not use any reference material and was designed by experimentation and altering to get the best look. The platonic solid polyhedron object was used as the first object to model from. This object had its subdivisions lowered to get a more structured low poly look for the rock. This was done as more subdivisions made the object rounder. Then divisions were added to the faces so that the vertices of these divisions can be soft selected and pulled in directions to get more of a random naturalness. The object is also retopologised to create more faces so that the object can be sculped more using tools like lift surface to further create a natural look. This is then triangulated again and had its faces reduced so that finally the objected looked rock shaped but low poly rendered. Three of these rocks were created to spread round in the final scene.

**Low Poly Tree 1 and 2:**
The low poly trees did not use a reference material as it’s a natural object it will be different from anything structured. However, images of low poly trees were used to look at to ensure the model looked similar to the professionals. The models consisted of a cylinder that has its subdivisions lowered to create a move hexagonal object and its edges on the top and bottom of the faces removed. This object was then extruded using the top face multiple times to create these trunk lines and allowed the structure of the trunk to not be entirely straight up. One of the trees has branches which was just a face extruded out. The objects still need to be altered to look more natural, so modification tools were used like soft modification to modify the edges and vertices more naturally. The leaves were a platonic object, like in the rocks, or a cube. The leaves were modified by transforming the vertices randomly using the "transform" tool creating random extrusions of the object. To get the low poly look, this was then remeshed, retopologised, triangulate, and then reduced.

**Island:**
Like the other natural objects, the island did not have any reference material and was generated out of experimentation and design. Using the create polygon tool, vertices of a polygon face was created in the top-down view to create the top of the island. This is where the design of thinking where each object will go on this surface, which is why a drawing of the object was done for reference. This face was then extruded down and up with also using offset etc. to create the main body of the island. Using the same techniques learnt from previous models, creating the low poly look for the bottom of the island involved sculpting, randomly transforming, remeshing, retopologising, triangulate, and reduce. These tools and methods have proved to be a good way of creating a natural randomise look while also looking structured like a low poly object.

**Barrel:**
The barrel object was one of the simplest to make. There are many references online, but none were needed to be imported as the object was simple. The object requires a cylinder with its subdivision reduced to six. This hexagon object is scaled up and has 4 edge loops evenly added around the object. These were then extruded to create the metal rims of the barrel and also curve the top and bottom of the object to create a barrel shape. Then finally top face is extruded and offset to create a lid. 

**Fence:**
The fence object was created out of referencing other low poly fences and what they looked like. They consisted of quite worn-down wood, creating this natural but also structured look. They had wear and tear in them, chips and cuts in the wood, this is what was aimed to create. Using the primitives cylinder (for the posts) and cube (for the cube), they were put together to create the fence shape, but it is the deforming and chamfer that made it looked more natural. By selecting vertices these can be chamfered which creates a chip cut look in the object. Using the lattice deformer tool around the objects, it was possible to warp and modify the object to look like worn wood. These tools were applied to both the planks and posts of the object.

**Sword:**
The sword and shield were the more technical models developed requiring more research to complete. There were references for the sword that were used to create the size and style of the sword. The plane primitive was used to develop the blade first by extending it and creating points like using the tool "collapse". The plane was extruded out and offset to create the first side of the blade which the mirror tool then created the other side of the blade to create a 3D object of this 2D plane. Through a lot of manipulation with extruding, edge loop, fill hole and scaling the faces and edges the handle was created for the sword.

**Shield:**
The shield is another model created in a similar way to the sword, by using the plane primitive. This plane was edge looped to create more faces and the vertices moved to create the classic shield crest shape. The object was extruded out and mirrored, like the sword, however once tool was used that created the curve of the shield. The deform tool nonlinear bend was able to curve the entire model to create a curved look for the shield.


### Materials and Textures

All the objects created in their separate files had their object names created and grouped together in the outlier. This was to allow for the modelling and scenes to be organised and easier to follow. This is no different when it came to designing the materials for each object. Every object modelled used an Arnold aiStandardSurface material in their objects. These materials were uniquely named and applied to relevant faces of the object to get more complex looking objects. 

The arnold materials were experimented with extensively to get the best look out of the models. The arnold material had many parameters to get the look of a particular material but the parameters used mostly for this render were:

- Base: changing the colours to fit the model, but it also allowed for the material to diffuse roughness (creates a rougher look, used on the leaves and bark etc.) and/or create metalness (used for the metal parts of the objects, used for sword and barrel rims etc.).

- Specular: changing the values of these parameters made the material more or less reflective. This was good for objects like the metal of the sword or the glossy surface of a marble temple. 

- Coat: changing the values of these parameters allowed the metal objects look more metal, but also has the possibility of putting png images on top of base colour materials.

To test these materials, each file used their own lighting to view them in the arnold viewer renderer. Using low settings for the render, the model can be viewed rendered with light in real time as your modifying the object or lights (Appendix B showing practise with lighting and materials). This allowed for a lot of experimentation and design with the lighting and material parameters. 

The materials looked good but too simply, the barrel was just a block of brown etc. The way to get more life into the models is by using textures. Texturing was not part of the course; therefore, free textures were found online. These were applied to the materials. Some of the textures came with extra files such as ambient occlusion, diffuse, normal maps and displacement textures. These were researched into what they were and how to apply them. This led to using the hypergraph to apply the textures to the arnold material. Nodes such as multiply, displacement shader and aiNormalMap to connect these textures to the models. 

Some of the texture looked too big, such as grass on the island the size of trees. To combat this, each model was UV mapped automatically to allow manipulation model against the textures. The UV net was expanded to create smaller textures etc. However, it sometimes created repeating patterns ruining the illusion of these nice materials. Understanding that the UV map has to have a custom designed texture so that the model can wrap around it, but this was not done. What could be improved and understood more is the materials, texturing and UV maps to create better looking models.

### Setting Up Scene 

Once all the models and materials were created, and it looked decent enough, it was time to import each object into one project. 

**Objects:**

To ensure that the models worked with each other, with the materials/lighting working as well, a project file was worked on to test importing the objects and creating a rendered picture (Appendix C shows this). Once experience with importing and moving the created models was done the final piece can begin. 

Importing each object was easy but certain problems arose that needed to be fixed:

- The object imported were all different sizes, such as the sword being bigger than the island etc. These objects needed to be scaled up or down depending on the scene design. The scene was drawn, by hand, beforehand so that there was a reference of where each object was to be placed.

- Rather than importing the object over and over, each object that needed multiple (such as barrels and trees) were duplicated and placed around the scene in varying sizes. 

- The island model did not accommodate the temple model well. Placing the model on top of the island showed this temple glitching through the landscape or floating above low ground. To combat this, and to make the ground seem more natural than a flat surface, sculpting tools were used to bring the surface up or down to mould with the temple being on top. This was applied to the rest of the island to give the impression of hills etc.

- The temple model was not proportionate compared to the rest of the objects on the island. This was a mistake in design as the island was not big enough to fit a large enough temple. To combat this, objects getting closer to the temple on the island was scaled down to give the impression of distance, like seen in paintings.

**Lighting:**
The lighting was the best bit of the arnold render as it can create very beautiful scenes. Multiple of the arnold lights were experimented with but the two lights used were the area light and the physical sky light. The area light type had parameters such as: exposure, colour temperature, and spread. These parameter values were changed to create spotlight effect (changing the spread), the warm sun or cold night feel (colour temperature), and the amount of light coming from the light source. It was advised not to touch the intensity of the light, only the exposure, to increase light. 

Six lights were used in total for the render, five area lights and one physical light. The physical light acted as the sunshine for the daylight render but even though this light lit up the enter scene, bits of the scene could be enhanced to highlight areas. This is what the area lights were used for. Three lights highlighted the interior of the temple to display that the temple is alive with human activity (Appendix D shows the night-time render of these lights). An exterior spotlight light focuses on the sword and shield location highlighting their importance (Appendix D shows this more). This spotlight was included in the day render as it both highlighted the objects but also imitated cloud cover with sunshine through. The last area light was shone through the pillars of the temple, from the direction of the sunlight physical sky, to create a beam of sunshine through the temple.

### Rendering

As discussed before when setting up the lights, arnold render viewer was used with low render settings for real time rendering while adjusting the scene. For the final render the settings were increased in quality to generate a good final image. These settings were:

- Pre-set pixel density of HD_1080 to generate a 1080p sized image.

- The renderer was switched from CPU to GPU to allow for faster rendering, but it also allowed for higher samples to be taken. The quick rendering was set to 3, however for the final output image Camera AA samples was set to 10 which meant 100 samples of light bouncing in the scene. This generated a much crisper image.

- With a crisper image there was still noise generated. Therefore, a feature of a Nvidia card and Maya allows an imager to process the image more. The imager used was "Denoiser Optix". This removed any noise or specs from the image, so the completed image was beautifully rendered.

## References

These references below are the materials and knowledge used to complete this section.

###Textures###

Dirt, Rocks, Bark, Fence_Wood, Shield_Wood from

Poly Haven (2021) Poly Haven The Public 3D Asset Library. Available at: https://polyhaven.com/ [Accessed: 01/11/21]

Marble from

Hasan, S (2017) Colour of the month White – July. Available at: https://suna-hasan-8f2n.squarespace.com/blog/2017/5/30/www.sunaandtoast.com  [Accessed: 01/11/21]

Leather from

Wild Textures (2021) Brown Leather Textures. Available at: https://www.wildtextures.com/free-textures/brown-leather-texture/ [Accessed: 01/11/21]

Iron from

Yingyang (2017) Texture background Free Photo. Available at: https://www.freepik.com/free-photo/texture-background_1167413.htm#page=1&query=iron%20texture&position=0&from_view=keyword [Accessed: 01/11/21]

Dirt Path from

Seamless-pixels (2013) High Resolution Textures. Available at: https://seamless-pixels.blogspot.com/2013/01/seamless-sand-dirt-ground-texture.html [Accessed: 02/11/21]

Grass from 

3dJungle (2021) Grass Seamless Texture. Available at: https://3djungle.net/textures/grass/1417/ [Accessed: 02/11/21]

###Modelling Knowledge###

Digital Dreambox (2021) Model A Low Poly Fence In Maya. Available at: https://www.youtube.com/watch?v=ATJs7MUCBRE&t=214s [Accessed: 28/10/21]

Digital Dreambox (2021) Model A Low Poly Shield In Maya | Basic Medium Shield. Available at: https://www.youtube.com/watch?v=qQwvo26pktI [Accessed: 28/10/21]

Digital Dreambox (2021) Model A Low Poly Sword In Maya | Basic Short Sword. Available at: https://www.youtube.com/watch?v=cL6-3XAL37o&t=294s [Accessed: 28/10/21]

Digital Dreambox (2021) Model A Low Poly Floating Island In Maya | Rocky Platform. Available at: https://www.youtube.com/watch?v=K7HruLyS-jE&t=386s [Accessed: 28/10/21]

Digital Dreambox (2021) Model Low Poly Rocks In Maya | Simple Rocks and Stones. Available at: https://www.youtube.com/watch?v=8LUTku3AN50&list=LL&index=17&t=402s [Accessed: 28/10/21]

Digital Dreambox (2021) Model A Low Poly Tree In Maya | A Simple Tree. Available at: https://www.youtube.com/watch?v=5u7nPb-0wl4&list=LL&index=18&t=527s [Accessed: 28/10/21]

Moore, T (2017) 3D Basics in Maya - Modeling a Greek Temple. Available at: https://www.youtube.com/watch?v=RqYmpVpsInY&list=LL&index=33&t=1500s [Accessed: 28/10/21]

### Lighting Knowledge###

Le Blanc, B (2019) Lighting in Arnold for Maya | Lighting Tutorial. Available at: https://www.youtube.com/watch?v=iUfCRXbL9ZM&list=LL&index=22&t=7s [Accessed: 30/10/21]


