# Unicorn Night Light

## Idea
This project brings to life the following vision for a table-top night light

* Unicorn shaped shell
* Star shaped holes (through which the light will project)
* Moves up and down .... but *not* in circles (to avoid the user getting dizzy)
* Preferably rainbow colored

![Unicorn Nightlght Assembly](images/freecad_assembly.png)

## Research and Development

### Conceptual Design

A back of the envelope sketch of the vision! Doesn't need to be perfect, just needs to communicate what we want to accomplish. 

### Research

#### Printable Parts

First, I needed a mechanism that could convert angular movement to linear movement...but I didn't know the right word for it. So I googled. Turns out, the word is "crank". Then, because my CAD skills are pretty elementary, I searched by go-to resource (printables.com) for a model that would work as a starting point -- with some resizing and adjusting to accommodate the motor shaft.

#### Electrical and Mechanical

My hardware-adjacent and hobby background helped here. I hopped on amazon to find a low speed motor, appropriate transformers and adapters, and some LEDs and heat sinks. If you don't see the BOM when you're reading this, it will be up soon.

### Detailed Mechanical Design

##### CAD

I'm an engineer, but not *this* kind of engineer (professionally, at least). I did play with meshes in grad school, and CAD for mechanical design as an undergrad, but I was SUPER rusty when I started this project.

###### Tl;dr

* I used FreeCAD (https://www.freecad.org/), Blender  (https://www.blender.org/), and Tinkercad (https://www.tinkercad.com/)
* Blender for mesh coarsening (in order to import the unicorn head mesh into FreeCAD and Tinkercad)
* FreeCAD to create the primitives to hollow out the head
* Tinkercad for booleam operations (i.e., actually subtracting the hole from the shell; adding the star holes)
* FreeCAD to ensure mechanical fit of the crank parts and motor mount and extending the slider / attaching it to the outer unicorn head shell
* Tinkercad for final adjustments (adding a collar, subtracting the base, making the hole to attach the slider column to the unicorn shell)
* Blender to bisect the unicorn head in order to fit it on my printer (a Prusa Mini)

###### Play by Play
This turned out to be more complicated than I had originally envisioned.

CAD tools are expensive, especially the professional ones. My favorite tool for small projects because it's very easy to use is tinkercad (online-only tool from the makers of AutoCad).

For this project, that wouldn't work because the unicorn mesh was too big. After some research, I selected FreeCAD. Don't forget to leave a donation!

The big mesh was still causing problems, and free cads discretization didn't "just work". It's been a hot second, but I have used Blender for generating graphics for academic projects in the past. So I installed Blender, imported the mesh, used Blender's decimation tools, then went back to FreeCAD.  

After refining the mesh, I imported it back into FreeCad, then used primitives (cylinders, spheres, cones) to hollow out the unicorn head.

Next pain point was converting the unicorn shell to a solid in order to subtract the hole. FreeCAD recommends a max of 20k triangles; it was still too big (I tried to wait to let the CPU do it's thing, but it was hung)

But! Now I could import both parts into tinkercad and cut the hole out that way! So I decided to make the full shell in tinkercad, and return to FreeCAD (which I do want to learn) for the moving parts.

Back to free cad to adapt the crank parts!

I imported the crank parts separately and "assembled" them for sense of scale. The general plan was to fit them in then scale the unicorn if necessary to make more room. I decided I would add mounts for the PCBs and LEDs later once all of the moving parts were put together. (Or, just wedge them in for now and come back to that in the next rev).

I needed one last import into free cad to cut the base out of the unicorn when all measurements were finalized. I scaled the unicorn up slightly from the original, and added a "cup" at the bottom to wedge PCBs and wires into.

One more round trop from FreeCAD Tinkercad to get the hole at the bottom correctly sized; I had to add a collar (I just did this in tinkercad) to maintain the wall thickess.

Finally! I split the unicorn by plans and went to plate it ... totally forgetting that I needed to have the edges filled (with the cutout, it's just 2 nested meshes.)

This article was useful: https://blender.stackexchange.com/questions/338870/bisect-separate-move. Don't forget to select "Fill" when you're bisecting. 

I rearranged the resulting objects into 2 collections, and duplicated the new faces in each collection, then, I went back to object mode and joined all objects, and then back to merge the meshes by distance (this removed a few hundred vertices each time).

## Resources

### 3D Models

Crank Mechanism: https://www.printables.com/model/632627-crank-mechanism 

Unicorn Head: https://www.printables.com/model/1155402-unicorn-head

3D Printer: https://www.prusa3d.com/product/original-prusa-mini-semi-assembled-3d-printer-enclosure-bundle-5/

You don't actually need your own 3D printer; there is a growing number of public libraries, schools, and maker spaces where you can find them.

### Electrical Components

BOM coming soon

## License

Unless otherwise noted, the documentation, images, and written content in this project are licensed under the Attribution-NonCommercial-ShareAlike 4.0 International.

You are free to share and adapt this material for any non-commercial purpose, as long as you give appropriate credit.

## Disclaimer

This project is provided for educational and informational purposes only.

You assume all responsibility and risk for using the information, code, hardware designs, and instructions provided here. I make no guarantees regarding safety, reliability, or suitability for any purpose.

By attempting this project, you agree that I am not liable for any injury, damage, loss, or other issues that may occur as a result of building or using this project.

*Always follow proper safety practices when working with electronics, tools, and power sources.*
