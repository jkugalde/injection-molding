# 3D printed FDM injection molds

## Summary

This is a guide for designing and making 3d FDM printed molds for parts made of resin or other materials that do not require or produce heat, such as bicomponent polymer compounds like silicone or polyurethane rubber.

I have been using this method to make soft robots and complex parts for protoypes that are highly deformable, injecting the material using a standard syringe.

My most recent injection project was the smart bracelet shown in Figure 1. It is a flexible case for a PCB that gathers data from sensors and communicates with an app using Bluetooth. There are embedded wires inside the wristband that connects electrodes in an end with the PCB.

<img src="/imgs/brac.png" width="850">

		Figure 1: Smart bracelet a) Bracelet b) One of the mould parts.

### Resources

For designing an manufacturing, you will need at least:

<font size= "2">

* A computer with a CAD software, like Autodesk Fusion 360.
* An FDM 3D printer.
* PLA filament.
* Sand paper (optional).
* An assortment of bolts and nuts
* 3x10 mm steel pins (optional)

</font>

And for the injection:

<font size= "2">

* Nitrile or latex gloves
* Syringes
* Paper towels
* Demoulding spray
* A plastic vase
* Mixing stick

</font>

Some other components may be required, but it will depend on what you are making. It is also desirable to have a vacuum chamber and a controllable temperature chamber. The vacuum chamber is for removing air from the mixture, the heat chamber is for accelerating the curing process.

[HERE](https://www.youtube.com/watch?v=_muUXPfTgq8) is a nice video of a DIY vacuum chamber.

## Physics and other considerations

We are injecting a viscous mixed fluid inside an enclosure using a syringe, so you need to take in consideration the following issues (shown in Figure 2):

* The enclosure must have an opening (or openings) to allow the air to move outside the mold and let room for the fluid. These openings (air vents) are also used to evacuate air that may be trapped inside the fluid, usually in the form of bubbles. Bubbles are the main source of flaws in this injection process.
* The best way to fill the mold is from the bottom to the top. This will help to prevent the generation of air pockets.
* If the injection happens from the bottom of the mold, the syringe must remain in this place to prevent the fluid from pouring down. As this is not desirable, it is ideal to produce a runner from the top surface of the mold to lead the material to the bottom. 
* On top of the main cavity, or in critical places of the mold, it is usually advisable to use risers to prevent voids if there is leakage of material.
* The height of the injection runner must be at the same level than the upper surface of the opening (riser or air vent), as hydrostatic pressure could push material out of the mold.
* Air vents and runners must be cleanable, so they are usually located in the partition lines of the mold. Otherwise, you will need a long, thin and rigid object (like a needle) to clear the holes.
* To prevent air pockets, there should be no horizontal features in the cavity. If there are sub cavities, an air vent must be considered.

<img src="/imgs/sphmold.png" width="850">

		Figure 2: Half section view of a sphere mold a) Simple mold, injection on the bottom, air vent on the top b) Same mold with runner and riser, injected from the top c) Adding a sub cavity to the injected piece, a new air vent is needed.

And finally, the piece must be "removable" from the mold considering the opening direction, this is, there should be no geometrical features with an angle greater or equal than 90°, as Figure 3 shows. The angle could be greater than 90° depending on the elasticity of the injected material.

<img src="/imgs/prtn.png" width="550">

		Figure 3: Half section view of a "trapezoidal" mold piece. The piece can be removed by opening the mold in the direction of the blue arrows, but not in the direction of the red ones. The piece will be trapped in the inferior part of the mould in this case (unless it is soft).

## Design

There are two ways of doing this. You can directly draw the mold parts (the negatives, which are usually two parts), or draw the positive and substract it from another body to generate a cavity. Lets assume that we are doing the latter with the part of Figure 4.

If the part does not have inner channels that pass across the body, the usual process is to draw it and subtract it from a larger body. This larger body must have an offset in all directions to include all the mold features, wich we will see later. In Fusion360 you will superpose the piece and the larger body and then use the tool COMBINE in the Modify section. Now, there is a void inside the larger body and you can cut it in all the necessary pieces to make the piece removable from the mold.

<img src="/imgs/fig4.png" width="850">

		Figure 4: Part for injection a) ISO view and front view b) Superposed larger body and part c) Section view showing the inner cavity. In this case, three cuts are needed to make the part removable from the mold d) Primitive parts of the mold

If the part has inner channels it is a bit more difficult. The easier case is when the inner chanel is straight, and the diameter of it is constant or cone shaped. For example, take the suction cup shown in Figure 5, it is symmetrical and has a straight channel with a connical end. I use it in a machine that I made for dropping large steel balls on rock samples. It is 28 mm tall and 30 mm wide.

<img src="/imgs/succup.png" width="850">

		Figure 5: Silicone suction cup a) ISO view b) ISO section view c) Front section view.


First, we need to obtain a piece that will produce the inner channel. For this, we will intersect the suction cup with a copy of it that does not have the channel (Figure 6). After that, we will use again the filled version of the filled cup no generate the cavity in the mold.

In this case, as the component is symmetric, we can superpose half of the part in a larger body to obtain half of the cavity (Figure 6). We will call A to this part of the mold. The other half, B, will be a copy of A with a few modifications. 

The inner channel piece will be modified with features that align it and holds it within the mold. Notice than after the injection the inner channel piece must be expulsed in the direction of the increasing section of the channel.

<img src="/imgs/fig6.png" width="850">

		Figure 6: Silicone suction cup mold a) A filled suction cup, it is intersected with the actual suction cup, which leaves the inner channel piece b) The filled section cup is cut from the larger body, and then, the inner channel piece is aligned.

The minimal features that every mold requires are:

* Injection point
* Air vents
* Opening notchs
* Closure system
* Alignment pins

Runners are not always needed. As it was said previously, the offset to considerate from the cavity must include this features. This will be the thickness of the mold. Thickness helps to strength the mold to enure more injeciton cycles.

The simplest injection point is a hole from the outside of the mold that goes into the cavity or the runners, although there are other options. The initial diameter of this hole must match the diameter of the tip of the syringe that will be used for injection, with enough clearance for the fitting. I usually use a 0.3 mm clearance with a standard fdm printer quipped with a 0.4 mm nozzle.

The hole or the runners must decrease in length approaching to the cavity, to diminish material loss and fabrication marks. I try to use 1 mm holes, and no lesser than that.

The air vents must be located from the inner top surface of the cavity until the top surface of the mold, and distributed equally.

## Manufacturing

The parts of the mold must be printed with the thinnest layer height possible, this is, 0.8-0.1 mm in an standard printer. This will increase the resolution of the molded piece and reduce sanding time. Reducing printing speeds is also helpful to achieve a better detail.

The mold must be oriented with the cavity facing upwards, with (ideally) no support material on the inside.

The sanding process of the cavity should start at grit 100-120 until 2000, for a smooth finish. Optionally, the mating faces can be sanded to improve sealing.


## Injecting

Using the CAD software it is possible to measure the volume of the injected piece, if you cannot, then you can fill the mold with water using a graduated syringe. Remember to dry it afterwards.

1. Put on the latex gloves
2. Apply demouldant to the mold
3. Assemble the mold
4. Pour the material for injection in the vase and mix it slowly, to avoid air getting trapped. It must be at least 10% more than the calculated volume, as there will be some loss in the vase. If the material is going to be degassed, then you need a vase with that at least double the volume of the mixture.
5. Degass the mixture if its possible. It could rise outside the mould, so be careful.
6. Fill a syringe with the material.
7. Push slowly the material inside the mould. Stop when it comes out from the air vent or the risers. Keep an eye for leakage.
8. Wait until the material cures, as indicated in the datasheet. You could also speed up the process using the heated chamber.
9. Open the mould and extract your piece.
10. Cut the leftovers.
11. Clean the mould.





