# Interaction

The interaction task involved working with OpenGL and respected libraries. This was to import the created diorama and then apply materials and animations through the OpenGL code.

##Importing Objects##

Importing the objects required the Maya model to be exported as .obj files. These files can then be imported to OpenGL through placing them it in the pipeline directory and initialising them in code. 

Importing the entire combined Greek Island model resulted in an error of “vector subscript out of range”. This could mean several things wrong but to combat this meant returning to Maya and exporting objects in a different way. Using other versions of the Greek Island Maya file, it was possible to get all the models separate from one another. They were all selected together (except for the trees), triangulated and created a UV map for each of them. The selected models were exported as an OBJ file and then imported to OpenGL. The model was able to render within the application.

The trees were exported separately into their own OBJ file so that they could be animated later in the program, similar process like this was done in the Unreal project before. The trees were put through the same process as before with UV mapping and triangulation. The positions were taken from the tree’s positions on the Greek Island so they should also transfer. Creating another mesh in the program and another draw, the OBJ file was able to render at the same positions as the Maya project. 

##Interaction##

To create a simple interaction, camera movement was done by using the WASD keys, the arrow keys and zooming of the camera with the PageUp and PageDown keys. This allowed the movement of moving in and out, rotating the object and panning the camera.
