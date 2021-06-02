# Diana Tan

# Final Project
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1329.JPG" height=px>
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1330.JPG" height=px>
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1331.JPG" height=px>

### Background & Summary: 
I initially wanted to create a puzzle table made up of building blocks that connected to each other in lieu of creating a cargo bike trailer that had a lot of complexity. However, after our conversation in class where I went through my proposal and was told to simplify into something smaller, I actually went back to the drawing board and creating a "modular" version of a bike as well as connected cargo boxes- basically an amalgamation of the original concept but without magnets or large sizes. 

### Concepts Used: 
Rendering, AI Tracing, Rhino, Grasshopper, Cura, Finishing

### Components Created/Designed/Modified:
1. Carla Cargo Trailer Frame
2. Carla Cargo Trailer Hinges/Tow Bar
3. Carla Cargo Trailer Wheels
4. Custom Screws, Nuts, Washers for Assembly
5. Milk Crate
6. Voloroi Crate
7. Folding Bin
8. Custom Amazon Logo

# Process

## Concept: Last Mile Bike Delivery Options
I initially wanted to re-create the cargo bike trailer we were using at work and then find modular components to solve our problem of gettng packages protected and easily accessible but also viably swapped on a simple trailer. I had initially planned/started off to make larger crates that we can print for the actual trailer that can attach to each other but then I sent it to our lab at work and they said that the material cost for a larger crate was going to be 4k. So I set out to design and modify a smaller trailer with smaller crate and bopx options.

#### Actual Carla Cargo Trailer: 
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1244.JPG" height=px> 
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1245%20(1).JPG" height=px> 

#### Drawings:
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1334.JPG" height=px> 

## Rendering
I rendered the carla trailer by going to the Standard Settings -> Typing in _Shade -> Turning off the Grid Lines -> going to Panel and then selecting Render -> Going back to Shade view port and selecting the Blue Dot. Then I modified the shade settings by adding a color gradient (Orange + Blue) and changing the material to a Metal (Steel) in the color of Gold. Then I converted the setitngs into RayTrace where I got a clearer image. I rendered multiple components- the bike, the cargo boxes and the bike + cargo box. However, I opted to not render the screws, wheels or other componentry since I didn't feel like I needed to see a screw in Raytrace...

<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/64411442855__8CDF0821-CF88-4F55-9FA8-7E92B6443CB4.JPG" height=px>
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/Render_Carla.png" height=px>
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/Render_CarlaRaytraced.png" height=px>

## Adobe Illustrator Design & Import (Logo)
I wanted to add the Amazon logo to some of the crates to show the applicability in delivery and design. In order to do so, I pulled the Amazon logo from Google (https://en.logodownload.org/amazon-logo/) and then I went into Adobe Illustrator, made it black and white and ran a Image Trace to get the vector image. I then did a simplify and group curves to import into Rhino as layers on the crates.

## Rhino Modifications (Reference Files at Bottom of Doc)
I had to create multiple Rhino files for each individual component.

### Carla Trailer
The Carla Trailer was by far the most complex part that I had to modify. The CAD file was readily available online but when imported into Rhino, created a component that was not printable due to the number of parts, the complexity of each component and the non-manifold nature of each component. Basically, for example, the wheels, were a series of "string" instead of a mesh. In Rhino, I converted this into a Mesh through Exploding, deleted the extraneous components that were too small to print and then separated the trailer into multiple prints that I then redesigned. This turned into the Frame, the Wheels (completely new design), the Handlebars and the Fork.

#### Carla Frame via Grasshopper
I separated the Frame from the rest of the components but then found that the frame mesh was too thin to actually print. Offsetting the frame in Rhino manually would also then change the tolerances of the other components. Instead, I found and modified a Grasshopper file from Weaverbird to Thicken the Mesh. Then I tested the different thickening variables until I can find the right balance between being "too" thick of a mesh but also too thin of a mesh that would be unprintable. I also modified the original Weaverbird Grasshopper plugin since it had a toggle function (Separate App) that was no longer available so I ended up deleting the toggle.

<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/Grasshopper_ThickenMesh_Carla.png" height=px> 

### Carla Screws, Handlebars & Frame
After going to the hardware store, I found that there were no mm screws that would theoretically be small enough for the trailer model and also have the right length (~60 mm) for the wheel axle. As a result, I created by own screws in Rhino through modifying a screw file on Thingiverse. I also learned to import, size and design the screw, washers and nuts together so that they would fit together.

For the handlebars and frame, I ended up cutting them out of the CAD file, removing any complexity, combining the Mesh and then resizing them in a way that was printable.

<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/ScrewRhino.png" height=px> 
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1325.JPG" height=px>

### Carla Wheels
I used my own wheels from thingiverse as opposed to trying to modify the Carla CAD wheels because of the complexity of the number of spokes in the CAD file. I basically used the Distance function in Rhino to calculate the size and then scaled the wheels down. I also put both the wheel and the rims together and used a Flex PLA material to get the wheel to print and have slight tolerances when putting the file together.

### Amazon Crates
I designed my own crates using a beer crate file on Thingiverse and then sizing it down to the size of the bed. I then imported the AI logo into the crate file. I also desigend 3 crates together in Rhino to ensure they would fit together. Then I tried to do a boolean difference on the bottom crate to make sure that the crates would stack on top. I also put th Amazon logo into 1 of the crates using the extrude function in Rhino. After importing this into Cura, I actually realized that the crates were too thin after they were scaled down so I ended up scaling up individual walls to the crates so that they would print.

### Gyroid Box & Folding Box
I used an existing Thingiverse file for the Gyroid Box and the Folding Box that I then resized, shaped and transformed in Rhino. Similar to the crates, I sized to the tolerances of the trailer and inserted the Amazon Logo.

## Calipers
In order to fit the components of the crates, I first actually printed the trailer frame before anything else. I then used calipers to measure the exact dimensions of the tolerances of the frame, the wheel well and the frame bed size. I measured the width of the cargo trailer as 49.49mm and the length as 120.60 mm. Height of 12.77 mm

https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1302.JPG

## Printing
Wheels: https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1303.JPG
Frame: https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1332.JPG
Separating the Frame/Wheels: https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1304.JPG



##Assembly
https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1327.JPG
https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1328.JPG

##Thingiverse Files
Carla Trailer:
https://grabcad.com/library/carla-cargo-crowd-1
Milk Crate:
https://www.thingiverse.com/thing:4638637/files
4 Shelf Bin:
https://www.thingiverse.com/thing:1489606/files
Nuts and Screws:
https://www.thingiverse.com/thing:193647/files


##Rendering

##Measuring with Calipers

I measured the width of the cargo trailer as 49.49mm and the length as 120.60 mm. Height of 12.77 mm



## Final Project Proposal
Create a proposal pitch for your final project. Your pitch should include a concept, including concept sketches, intended use case, context, a rendering, a breakdown of tasks (e.g. CAD modelling, 3d printing, casting, finishing), a timeline with contingency plans, a Bill of Materials with sourcing schedule
Your proposal can be for any digitally fabricated object. Your plan must include several of the techniques we learned in class, e.g. Rhino, Grasshopper, Slicing, Printing, Casting, Rendering, etc.
Document your proposal on a webpage linked to from your main webpage. You will present your proposal in class next week using your documentation. 
You are encouraged to work together but all work submitted must be your own. Please list your collaborators and peer-teachers in your documentation acknowledgements. If you use external sources (e.g. for images) please attribute them.

## Concept (The "UnLego")
In researching my final project and trying to piece together prototype pieces for a bike that I can put together in 2 weeks to show my concept, I actually discovered I had another problem- the inherent lack of prototyping pieces that adults can use that would reasonably translate into a final product. The only way I can make a table or bike or a version of a vehicle would be to print and design each piece, which does not allow me to experiemnt or build or play around with the final result physically. I tried to look at lego pieces but nothing in real life are actually lego pieces.

My concept is to make building blocks that would translate into real life measurements for designers and tinkerers to actually be able to build out their ideas. I would like to build basically, life-size legos in 1 inched increments that can be snapped together to make basically made-to-measure real life furniture, equipment and things. Similar to legos, I do not want to use glue- I want to use magnetic inserts on each corner of the block to get each side to connect.
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/IMG_1178.JPG" height=px>

## Use Case
I want to make modular furniture/pieces from my 3D printer (and potentially supplemented from my glowforge) that can be either used as a shelf wrap around a weird fireplace column in my house, a stool or a table for my Glowforge. Due to the fact that this will sit in my house, it will need to be 1) able to support some weight, 2) be aesthetically pleasing. I plan on using wood chips inlayed into resin to look like less of a resin table. I also may want to experiment with "holes" to reduce the weight needed.

MY low bar goal is to make a miniatiarized table that can be snapped together with magnets as a proof of concept. My SUPER low bar is to just make the blocks but not assemble them into products.

My medium bar goal is to make a small (low number of blocks) item like a small shelf.

My high bar goal is to make a table for my glowforge.

## Rendering
I have not completed the rendering yet but I'm envisioning that it will look similar to this:
<img src="https://github.com/autarky-hash/autarky-hash.github.io/blob/main/puzzletable.png" height=px> (From Artsy)

## Break Down of Tasks
1. Order Materials
2. Start Building 1st Cube in Rhino
3. Turn Cube into Mold
4. Print and Cast 1st Cube in a 25% resolution to test the cube.
5. Iterate on Cube
6. Mold, Print and Cast Cube again
7. Vary the cube in Grasshopper
8. Create other versions of the cube (Middle, End pieces, Corners)
9. Create a large mold
10. Mass casting blocks
11. Assemble blocks

## Timeline with Contingency Plan
1. Materials by 5/27
2. Build 1st cube in Rhino by 5/27
3. Start first casting and testing 5/28
4. ITerate on other cubes and build 2nd mold by 5/29
5. Start Mass Casting 5/30 [Contingency: Start Smaller Mold Just in Case]
6. Assembly 6/2 

## Bill of Materials
1. Oomoo
2. Epoxy Resin
3. Smoothing Paper
4. Wood Chips
5. Live Earth Magnets (Bulk)
6. PLA Filament
7. Cups
8. Stirrers
9. Resin Pigment (Optional)
10. Dowels (Contingency)
11. Screws (Contingency)

