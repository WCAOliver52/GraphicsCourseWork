# Animation

## Unreal 4 Animation Process

This task required importing the created models from Maya into Unreal 4 Engine and fixing the problems that come with importing the objects. Once the objects were imported, then using the sequencer in Unreal to create an animated video of the scene. 

### Exporting and Importing Objects to Unreal

Importing the created models from Maya was fairly easy to do, after understanding what to do after many attempts and practise files. However, exporting and importing the models is not as straight forward as it could be. There were many issues that occurred during the transfer of objects. Multiple methods of pipeline fixing were explored, and recommended processes are discussed in this section. The process consisted of this:

#### Exporting Objects from Maya

- Exporting from Maya involved first having an Unreal project file setup. This allowed the button of "send to Unreal" to be setup by connecting it to the project. This created an import file in the project which allowed easier and structured access to the models from the Unreal Project. By selecting the objects to be exported (which can consist of the model mesh and the rigging etc.) it can be sent to Unreal.

- Exporting the selected models from Maya by "send to Unreal", settings for the export will need to be addressed before finally exporting. These settings allowed for certain errors in Unreal to be fixed and ensure that the complete model with anything associated is transferred. The model was exported as a FBX file.

- When practicing exporting models, using the default export settings resulted in errors in Unreal. One error involved smoothing and smoothing groups; the models did not transfer with the smoothing transformation with the model. A fix for this was to activate the smoothing group and smooth mesh in the export settings. triangulate was a setting that could be used activated as well, but through research Unreal triangulates the model automatically. Therefore, this setting was not used to prevent any further issues. 

- If the model contained an animation, other settings needed to be activated. Along with the geometry settings from previous, the animation setting needed to be activated. Activating this allowed other settings to become available, most were set to default but the settings that should be activated is Bake Animation and Deform Models. These settings allowed for the animation created in Maya to be baked to the model, while allowing the model to move as the mesh can deform. One setting was found to impede the animation depending on how the animation was done. If the keyframes of the animation is connected to the mesh of the model, the recommendation would not have Constraints or Skeleton Definition settings activated. With these on, the imported animation would not work in Unreal. This is because these settings put the animation on a skeleton rig and not the model. This was found to work in Unreal when the keyframe animation were connected to the rig in Maya and not the mesh. This could mean that the rig created can be exported and applied to other models in Unreal rather than associated with the one model.

#### Importing too Unreal

- Importing the exported models to Unreal, involved add/import from the import folder created by Maya in the Unreal project. Importing these models required some settings to be activated depending on if the model has an animation or not but most of the time default worked. One of the issues discovered when practising importing models was the fact that Maya used different units than Unreal. The imported object was very small compared to the rest of the scene. This is because Maya scale units were set to 'cm' by default whereas Unreal used meters. To ensure proper scaling, during the import the scaling value was changed to 100 to accommodate. 

- One of the objects that did not get transferred over was the lighting from Maya. Unreal did not import the lighting objects created in Maya. This created a problem as the whole scene needed a light source. The lights had to be recreated as similar to the render's lighting. A directional light and sky sphere were used for the lighting in open day sky. The sky sphere had a pre-textured sky box of the sky and night sky. Assigning the sky sphere to follow the directional light created the impression of sunlight. This generated a similar look in sky light to the render. However, the other lights used in the render allowed certain aspects to be highlighted. Adding additional Unreal directional lights distorted the sky light in ways that Maya's lights did not. Additional directional lights were removed keeping only the sky light.

- When importing the diorama's models two main issues occurred: the separation of models and materials did not transfer. The separation of models occurred as the diorama model in Maya consisted of many polygon meshes, that were grouped together but were not joined as a combined mesh. This was to allow individual parts to be further modelled if need be. Exporting this to Unreal however, treated each polygon mesh as a separate model meaning it needed to be recombined in the Unreal project. This would be a massive set back as it would mean each part needed to be reassembled and there were thousands of individual parts. This was fixed by going back to Maya and using the combine tool to combine the meshes of the models. In the interest of time management, the island with the rocks, temple, fences, barrels and weapons were all combined to one mesh, except for the trees. This was because it was decided that the trees were going to be animated but the rest of the island would be static. Therefore, the island was imported as one model that can be scaled to the correct size while keeping the same positions of most of the models compared to the render. This meant the models did not need to be repositioned again, except for the trees. If there was more time involved, each model would be combined as their own asset. This could have allowed more interaction between the objects in the animation or for game purposes. 

- The second issue consisted of the materials exported with the model did not transfer the colour or the textures over to unreal. New but different materials were created in the Unreal Engine and automatically assigned to the faces and objects of the imported models. This problem occurred as Maya's Arnold aiStandardSurface (which was used for all the materials in the render) cannot be transferred over to Unreal. Therefore, the materials needed to be created again. Since new materials were already assigned to the separate faces of the model, it was easy to alter them to finally have the correct texture and/or colour. It was a massive help (and highly recommended) to name the materials in Maya identifiable unique names. This allowed the new generated materials to be identified to what surface and object it was assigned to, as it does not say which face each material is applied to. By having the models UV mapped previously, when assigning the textures and materials, it was easy for Unreal to place where the created materials should be on the model. Which made it easier to fix the materials, as it just needed to add the texture back or update the colour value. To fix the materials, they were edited in Unreal's version of a hypershade graph network. It involved using nodes such as: "Texture Sample" to assign the imported texture images back to the base colour, "Vector Parameter" which involves using a RGB colour code vector to assign the colour to the base colour when no texture was assigned to the model faces, and "Scalar Parameter" to assign a single floating-point value which was used to alter the roughness and metallic parameters of the material. In future work, if transferring a model from Maya to Unreal, Blinn or Lambert materials should be used on the model to allow quick import of the assets as they can be compiled by Unreal.

### Animation Maya + Unreal

The animation was going to be consisting of trees blowing in the wind, the sun going through a day night cycle and the camera moving around the island. These were created by completing multiple steps using Unreal's sequencer. These steps consisted of:

#### Creating Tree Animation in Maya

The animation of the trees was done in Maya and not in Unreal. The mesh of the whole model had to bend and twist, which moving the model in Unreal would not generate the same effect. The process of the making the animation involves:

- Separating the trees from the Greek Island model allowed the static floating island to be exported to Unreal, while work can be done on a separate Maya project with just the trees as the model. It also allowed for version control having multiple files of the same tree project trying out new methods.

- There were two different tree models that had to be animated separately. This allowed for the effect of wind affecting differently weighted objects and made it easier to work with. Having each tree in separate project files allowed for room for mistakes and experimentation without affecting the other models. 

- To create the animation a rig was created within the tree. A simple sequence of joints going through the middle of the trunk, not the leaves though. These were then "bind skin" and "paint skin weights" to ensure the rig affected the model's mesh as the rig moved. 

- The whole tree has to move, so moving each joint separately seemed like it would take a long time and wouldn’t produce a good result. Another tool called "ikHandle" allowed for the joining of two joints far from each other. The second joint was joined to the last joint (as the base of the trunk should stay still as its rooted to the ground, only if the first joint was not used), this tool meant that the rig setup inside the tree moves like a springy puppet when moving the ikhandle. 

- Having the leaves back on the tree, the mesh and ikhandle was selected. The first keyframe was the tree in its original position. The animation bar was set for 120 frames so a lot of movement can happen without it seeming too fast, at 24fps. The next keyframe was a little further along the timeline where the ikhandle was then moved about wobbling the entire tree. This was then repeated with each new keyframe. When the timeline was close to the end, the first keyframe was copied and pasted to the end so that a repeating loop can occur without any stuttering.  

- Testing the animation, the model will sometimes twist in unexpected ways causing it to warp through its geometry. To fix this using Maya's graph editor, it was possible to slow or flatten some of the in between keyframe movements.

- These animations where then exported with the model explained in the exporting objects section above.

#### Using the Sequencer in Unreal

Unreal has an animation bar of its own, the sequencer. One sequencer contained all the animation states for:

- The trees: the objects of the two trees were imported into the sequencer and then adding their animation track created in Maya. These trees where then duplicated and placed around the scene, with their animations referenced to them. The animations were also extended to the 34 seconds mark and put on cycle in their post-infinity, so the trees continuously blew around as the video went on.

- The sun: the sun was the directional light placed in the scene. The animation of a day cycle was done by transforming the rotation of the directional light in the sequencer. As the directional light was rotated, keyframe were added at points in the sequencer. This allowed the appearance of a day cycle. However, the sky sphere did not update with the directional light, so the texture of the sky did not move with it. This was attempted to be fixed by using a blueprint to update the sky sphere, but it only worked when the game was running and not in the animation. Therefore, the movement of the directional light was only done.

- The camera: the camera was a cine camera actor that can be seen through its viewport. This allowed to see what it was looking at as it moved. When moving the camera, keyframes were added at its transformation coordinates so when the final animation was done the camera moved smoothly through to each keyframe.

## References

These references below are the materials and knowledge used to complete this section.

###Animation Knowledge###

Maher, L (2021) Maya to Unreal VFX Animation Workflow. Available at: https://www.youtube.com/watch?v=x2ailjOAq90&list=LL&index=8&t=511s [Accessed: 15/11/21]

CBros (2018) Low Poly Tree - Rigging in Maya.  Available at: https://www.youtube.com/watch?v=7glJl2N5-Jc&list=LL&index=4 [Accessed: 15/11/21]

