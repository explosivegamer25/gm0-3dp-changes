.. include:: <isonum.txt>

.. |nbhp| unicode:: U+2011
.. nbhp stands for non-breaking hyphen: 'PLA\ |nbhp|\ CF' prevents PLA-CF from wrapping

.. |ndash| unicode:: U+2013

.. |kjm2| replace:: kJ/m\ :sup:`2`

.. |gcm3| replace:: g/cm\ :sup:`3`

3D Printing
===========


Kinds of 3D Printing
--------------------

There are a few different kinds of 3D printing. FDM (Fused Deposition Modeling) (also known as Fused Filament Fabrication) extrudes a melted filament to create a part and is the most common type and the one we'll focus on in this guide. SLA (stereolithography) and SLS (Selective Laser Sintering) are both options for 3D printing plastics, but they are generally more complex, expensive, or hold other disadvantages in FTC\ |reg| applications. For those reasons, they are not recommended.

Metal 3D printing (SLS and others) is also becoming more and more available, but is not in the scope of this guide.

.. tip:: Consider checking out `the FTC docs 3D printing section <https://ftc-docs.firstinspires.org/en/latest/manufacturing/3d_printing/index.html>`_, a guide for FDM 3D printing within the scope of FTC. It covers topics such as: bed adhesion, tolerances, designing for 3D printing, tuning, and hardware choices.

Advantages of 3D Printing
-------------------------

- 3D printing allows for customizable sizing and perfect optimization; for example, teams can print a spool of the exact diameter needed for optimal speed, or a belt pulley with a certain number of teeth.
- 3D printing allows teams to adapt between kits and individual parts easily, as not all kits have adaptable mounts or brackets. A good example of this are the Nexus :term:`mecanum <Mecanum Wheel>` bore adapters that teams 3D print.
- 3D printing allows teams to fabricate parts that would otherwise be impossible with materials such as aluminum due to machining restrictions.
- 3D printing allows teams to have customizable strain relief on wires and connections. This is a great project and well worth your time.

Disadvantages of 3D Printing
----------------------------

- **If you are out of 3D printed spares at a competition, you're probably out of luck. Teams are advised to print at least one set of every single 3D printed part as spares for competition**.
- 3D printed components are generally weaker than other materials such as aluminum. However, printing in the proper orientation can be very strong - teams have 3D printed hooks and other parts to support their FRC\ |reg| robot (120 pounds) and FTC robots (40 pounds).
- 3D printed parts should only be loaded in one orientation. That is, if the robot is hanging from a hook, the only load should be on the bottom face of the curved part of the hook. Try to eliminate side loads as much as possible to avoid part failure.
- The size of 3D printed parts is limited by the size of your print bed.
- Large and thick prints can take a long time (overnight) to print and can run the risk of failure.
- 3D printing can end up quite expensive, though filament can be found for a reasonable price on online vendors such as Amazon.

3D Printing Design Guide
------------------------

Here is a quick guide on designing 3D printed parts that we hope is helpful for teams who may be unfamiliar with 3D parts.

The first consideration when designing 3D printed parts is print orientation. This refers to the side that contacts the print bed. Preferably, the part should have a flat bottom to maximize contact with the print bed.

.. tip:: Maximizing contact with the print bed will make sure the part doesn't delaminate or warp from the bed and increase print quality.

If it is impossible for the part to have a flat side to print on, a simple solution is to split the part into multiple parts along a plane. For instance, the gearbox plate below didn't have a flat side to print on, so it was split in half. The part was later sandwiched with numerous screws and plastic glue. If this plate was printed as one part instead of split in half, support would have to be used to create all of the necessary holes. Parts that use no support material make sure that the least amount of plastic is wasted.

.. image:: images/3d-printing/2-piece-gearbox.jpg
   :alt: A 3D printed gearbox, printed in 2 parts, cut along a plane

.. tip:: Don't chamfer or round anything on the perimeter of the first layer on the bottom face of the part. Chamfering or rounding will increase the chances of the part warping, especially on unheated print plates.

Draft Angle
^^^^^^^^^^^

Draft angle refers to the overhang angle between the part side and normal vector from the print plate. The maximum draft angle refers to the maximum angle the printer can print without support material and is based on the printer, print settings (notably speed, temperature and cooling) and filament type. When trying to decrease support material, consider every overhang angle and make sure it is within the maximum draft angle. Staying within the maximum draft angle will also decrease the chances of part warping.

Stress Vectors
^^^^^^^^^^^^^^

Perhaps the most important consideration is stress vectors. 3D printed parts are inherently stronger on two axes and weaker on one axis. The weaker axis comes from the layering action that defines FDM 3D printing. A common fix to this is to simply increase the print temperature up to a certain limit until it starts decreasing print quality, but the weaker axis can be resolved by again splitting up into multiple parts. The point to get across is to try to increase strength by optimizing sections of the part on the plane they are being printed on. For instance, this assembly below was responsible for hanging the entire robot, so it had to be the maximum strength possible for a 3D printed part.

.. tip:: It might seem counterintuitive to split up a part into multiple parts to increase strength, but there is a logic behind it.

The part could have been easily printed as a single part, but it would be fairly weak when stresses are exerted in the upward direction. Splitting the part and creating new flat surfaces to print on will strengthen each axis. *If one small part failed, the robot might still be able to somewhat function.* This would be preferable to the entire piece failing at once. In this example, the side pieces were printed as separate parts on a complementary axis to strengthen the assembly.

.. image:: images/3d-printing/printing-multipart.jpg
   :alt: A multipart assembly 3D printing

.. image:: images/3d-printing/assembled-multipart.jpg
   :alt: An assembled version of what was printing in the previous image

This assembly is a good example of considering part orientation, draft angles, and stress vectors in each part of the design. Complex parts can be made strong and without any support by simply splitting it up in the right way.

Material Selection
------------------

.. warning:: All filaments decompose at high temperatures and release potentially harmful fumes. Some byproducts are more harmful than others. Additionally, CF and GF filaments release microscopic fibers that can collect in your lungs. While filaments like delrin and ABS are the worst and require special HEPA filters and sealed enclosures, you should still print all filaments in a well-ventilated area!!

For the purposes of FTC, PLA and PETG are all you need about 90% of the time. Everything else in here is for reference if you need very specific properties or are looking into other projects. Though we do recommend swapping your PETG with PCTG.

A few things to be aware of before selecting a material:

- Filaments can be annealed. This is when they are heated for long periods of time over their glass transition temperature (T\ :sub:`g`\ ) and then allowed to cool slowly. This alters the crystallinity of the filament and reduces internal stresses, ultimately making it slightly stiffer and far more temperature resistant. For example, PLA's softening temperature increases from 55\ |deg|\ C to nearly 140\ |deg|\ C. Additionally, with other materials like nylon, annealing can dramatically reduce its creep under load. Note that annealed parts may shrink significantly (several percent for PLA).
- All filaments absorb moisture and should be kept dry. Moisture can lead to reduction in print quality due to bubbles forming where water is boiling, and the water reacting and breaking down the polymer. Some filaments do not absorb water, such as: PCTG, PP, PPS, or SEBS.

.. admonition:: Fun fact

    Specifically in nylons, especially moisture-conditioned PA6 and PA6,6, water acts as a plasticizer and can make it upwards of ten times tougher but will nearly halve its tensile strength.

Fiber-filled filaments
^^^^^^^^^^^^^^^^^^^^^^

Materials ending in |nbhp|\ CF and |nbhp|\ GF are common composite materials in 3d printing. |nbhp|\ CF denotes the addition of carbon fibers to add stiffness, strength, and temperature resistance to a filament. Similarly |nbhp|\ GF filaments add glass fibers for the same reason. Such modifiers also help reduce warping. These filaments are highly abrasive and require a hardened steel or gemstone nozzle to print.

.. warning:: Keep in mind that CF and GF filaments will claim to be tougher and have better layer adhesion. Know this **this is usually a lie** unless you print at least 10\ |deg|\ C above the recommended printing temperature, even then they will still be much more brittle.

Key differences

- CF has little effect on the density of a filament, while GF can significantly increase it.
- CF adds more stiffness, strength, and temperature resistance to the filament, but GF is typically less brittle than CF.
- GF filaments can be colored with normal colors, while CF is stuck with the black CF in it, thus colored CF filaments appear darker and non-uniform in color (little specs of black are visible).

A few Rules of Thumb and Pinky
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Stiffer = more brittle.
2. Do research before printing a new filament. **Especially flexibles**.
3. CF is stronger, GF is tougher (in relation to each other).
4. If there is little to no documentation for a filament, do not use it. There is a reason it is not documented; for example, HDPE, I need not say more.

.. tip:: Expensive filament is not (usually) worth it. Avoid spending more than $40/kilo. Some cheap but high-performance filaments are:

    * Elegoo PAHT-CF |ndash| $39.99 for 1 kg
    * SUNLU PC-ABS |ndash| $39.99 for 1 kg
    * Polymaker PLA blends (HT, Polymax) |ndash| $30-40 for 1 kg
    * Pretty much any ASA |ndash| $20-35 for 1 kg

In addition to the filaments mentioned in the tip above, we recommend using most filaments from the following brands:

- Bambu - Good balance of price and quality. Large color and filament catalog.
- eSun - Super cheap.
- Overture - High quality.
- Prusa - Exceptional quality, though higher price. Their PC blend is our favorite functional filament overall for great properties in all categories.
- Polymaker - High quality and large selection of engineering-grade materials, such as their "Fiberon" line of CF/GF filaments and many different PC blends.
- Sunlu - Cheap and good quality. Good for low-cost nylon or PC-ABS.
- VoxelPLA - Specializes in PLA and PETG, very good quality.
- 3DX Tech - High-quality, high-performance polymers (PEEK, etc.), made in the U.S.

Common Filaments
----------------

PLA
^^^

PLA (polylactic acid) is the most common printing plastic due to low cost and ease of printing. Contrary to popular belief, **it is not biodegradable**; however, it can be industrially composed in some facilities. Strengths: stiff, reasonably strong, easy to print, dirt cheap, and has good layer adhesion. Weaknesses: PLA has poor heat resistance, high creep even under small loads, and brittleness.

PLA-CF/GF |ndash| extremely brittle and actually weaker than regular PLA. Do not recommend.

PETG
^^^^

PETG (polyethylene terephthalate glycol) is a glycol-modified PET to allow it to print easier. Despite being in the PET family, **it is not recyclable!** Strengths: higher temperature resistance than PLA, is less brittle, low creep under small loads, dirt cheap, and good layer adhesion. Weaknesses: it is slightly harder to print and is less stiff and strong.

PETG-CF |ndash| can help with common issues printing PETG such as blobbing, sagging, and minor warping, as well as helping layer adhesion when printed at high temperatures.

ABS
^^^

ABS (acrylonitrile butadiene styrene) is the OG printer filament, commonly used in LEGOs and "cheap plastic" components. Strengths: higher temperature resistance, great toughness, and high print speed. Weaknesses: low strength/stiffness, varying layer adhesion due to warping, harder to print, and foul-smelling, toxic styrene fumes while printing.

ABS-CF/GF |ndash| CF helps reduce warping but makes ABS stiffer (ruining its toughness). ABS-GF is more useful due to being less brittle.

TPU
^^^

TPU (thermoplastic polyurethane) is a soft, flexible material that comes in many hardnesses (durometers) for many applications. Most commonly in printing is the 95A durometer. Strengths: good strength, near perfect layer adhesion, flexibility, and because of the flexibility, theoretically infinitely high toughness. Weaknesses: difficult to printing for many reasons and a disappointing lack of surface grippiness (it is plastic, not rubber).

TPU-CF |ndash| Yes, this exists. It increases both the tensile and impact strength of TPU, good for things like timing belts.

+-------+------------------+------------+-----------------------------+----------+-------------+
|       | Tensile Strength | Notched    | Heat Deflection             | Flexural | Density     |
|       +--------+---------+ IZOD       +--------------+--------------+ Mod.     |             |
|       | XY     | Z       |            | 0.45 MPa     | 1.8 MPa      |          |             |
+=======+========+=========+============+==============+==============+==========+=============+
| PLA   | 55 MPa | 45 MPa  | 5 |kjm2|   | 57\ |deg|\ C | 52\ |deg|\ C | 2400 MPa | 1.24 |gcm3| |
+-------+--------+---------+------------+--------------+--------------+----------+-------------+
| PETG  | 41 MPa | 36 MPa  | 3.9 |kjm2| | 68\ |deg|\ C | 65\ |deg|\ C | 1700 MPa | 1.25 |gcm3| |
+-------+--------+---------+------------+--------------+--------------+----------+-------------+
| ABS   | 39 MPa | 35 MPa  | 30 |kjm2|  | 87\ |deg|\ C | 75\ |deg|\ C | 1700 MPa | 1.05 |gcm3| |
+-------+--------+---------+------------+--------------+--------------+----------+-------------+
| TPU   | 41 MPa | 24 MPa  | n/a        | 70\ |deg|\ C | 50\ |deg|\ C | n/a      | 1.25 |gcm3| |
+-------+--------+---------+------------+--------------+--------------+----------+-------------+

+-------+------------------+---------------------+----------------------+
|       | Bed (\ |deg|\ C) | Nozzle (\ |deg|\ C) | Chamber (\ |deg|\ C) |
+=======+==================+=====================+======================+
| PLA   | 0-70             | 190-230             | 20-30                |
+-------+------------------+---------------------+----------------------+
| PETG  | 65-85            | 240-265             | 20-40                |
+-------+------------------+---------------------+----------------------+
| ABS   | 85-105           | 245-270             | 35-50                |
+-------+------------------+---------------------+----------------------+
| TPU   | 0-60             | 220-245             | 20-30                |
+-------+------------------+---------------------+----------------------+

Engineering Grade Filaments
---------------------------

ASA
^^^

ASA (acrylonitrile styrene acrylate) is used in the industry in medical facility pipes due to chemical resistance. Like ABS, but with the added benefit of chemical and UV resistance and less toxic fumes while printing.

ASA\ |nbhp|\ CF |ndash| CF makes it too brittle, do not recommend.

PA
^^

PA (polyamide, also known as nylon) is a strong, tough, and lightweight family of plastics used in almost every major industry due to a broad range of favorable properties. Examples include everything from zip-ties to toothbrush bristles to fabrics to fuel tanks, gears, engine covers and much more.

.. Note::
    We will be mostly referring to the CF versions of PA, this is the most common form of nylon filament. It offers superior mechanical and printing properties compared to regular nylon.

PA6 |ndash| the most common nylon type for all applications. It is stiff, strong, tough, temperature resistant, lightweight, and has good layer adhesion. However, it is much more expensive, hard to print, and absorbs large amounts of moisture from the environment which can dramatically change its mechanical properties. **it must be dried before printing**.

PA6,6 |ndash| Similar to PA6, except even stronger and stiffer, but is rare to find as a filament. Little data is available regarding 3D printed PA6,6.

PA12 |ndash| The other most common form of nylon in 3D printing. Slightly weaker mechanical properties compared to PA6, but boasts lighter weight and much lower moisture absorption, making it better retain its properties under harsh chemical conditions.

PA11 |ndash| A naturally derived and renewable form of nylon. Like the ASA of nylons, it is more ductile, temperature resistant, and can handle UV and chemicals better compared to PA12.

PAHT |ndash| Usually a PA12 alloy designed for high temperatures. Its properties take the strengths of both PA6 and PA12 while eliminating the weaknesses. Excellent for all extremely demanding applications. Its weaknesses are price and printability. Due to high CF content, it has a sandpaper-like surface texture and thus has lower dimensional accuracy due to the rough surface.

PPA |ndash| Nylon copolymer polyphthalamide. Typically used in the automotive industry for parts under extreme stress, heat, and chemicals. It is the strongest and stiffest filament printable on most consumer-grade printers. Its weaknesses are extremely high price and brittleness.

PC
^^

PC (polycarbonate) is most often used in sheet form, where it is used for greenhouse panels and things that require extreme toughness and high visual clarity such as bulletproof glass. PC filaments are excellent for structural components that need to take a beating, and applications requiring medium-high temperature resistance such as electronics housings. As a filament, it is almost never in its pure form due to extreme difficulty of printing. As a result, we have categorized two main types of blends: "stiff" PC and "flexy" PC.
"Stiff" PC: much closer to pure polycarbonate. Strengths include remarkably high strength (the highest of the common non-fiber filled filaments), good stiffness, high temperature resistance, and low creep. Weaknesses include brittleness, warping, and high print temperatures.

"Flexy" PC: Polycarbonate with additives such as PBT, ABS or PETG. Strengths include good strength, high temperature resistance, outstanding toughness, great layer adhesion due to increased flexibility, and less warping than pure PC. Weaknesses include high price, some warping, and lower stiffness.

PC\ |nbhp|\ CF |ndash| Takes brittle PC and makes it more brittle. However, it does increase strength and stiffness to an even higher level, rivaling PAHT-CF, PET-CF, and others. Also dramatically reduces warping and some creep at high temperatures that PC can experience.

PET\ |nbhp|\ CF
^^^^^^^^^^^^^^^

PET (polyethylene terephthalate) is recyclable in its pure form, **but not as a CF blend.** PET is used in printing primarily in its CF form for incredible stiffness, temperature resistance and low moisture absorption compared to nylons. Weaknesses include brittleness, high cost, and high print temperatures at the limit of most consumer-grade printers.

+---------+------------------+------------+------------------------------+----------+-------------+
|         | Tensile Strength | Notched    | Heat Deflection              | Flexural | Density     |
|         +--------+---------+ IZOD       +---------------+--------------+ Mod.     |             |
|         | XY     | Z       |            | 0.45 MPa      | 1.8 MPa      |          |             |
+=========+========+=========+============+===============+==============+==========+=============+
| ASA     | 41 MPa | 35 MPa  | 40 |kjm2|  | 90\ |deg|\ C  | 85\ |deg|\ C | 2060 MPa | 1.05 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PA6-CF  | 82 MPa | 18 MPa  | 18 |kjm2|  | 180\ |deg|\ C | 165\ |deg|\ C| 7000 MPa | 1.16 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PA12-CF | 78 MPa | 30 MPa  | 16 |kjm2|  | 170\ |deg|\ C | 160\ |deg|\ C| 4000 MPa | 1.06 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PA11-CF | 64 MPa | no data | 17 |kjm2|  | 190\ |deg|\ C | 160\ |deg|\ C| 4000 MPa | 1.11 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PAHT-CF | 80 MPa | 50 MPa  | 9 |kjm2|   | 210\ |deg|\ C | 200\ |deg|\ C| 9520 MPa | 1.09 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PPA-CF  | 101 MPa| 22 MPa  | 8 |kjm2|   | 227\ |deg|\ C | n/a          | 9860 MPa | 1.25 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| Stiff PC| 70 MPa | 53 MPa  | 4 |kjm2|   | 110\ |deg|\ C | 105\ |deg|\ C| 2650 MPa | 1.2  |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PC-ABS  | 58 MPa | 30 MPa  | 120 |kjm2| | 110\ |deg|\ C | 105\ |deg|\ C| 2000 MPa | 1.24 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PC-CF   | 70 MPa | no data | 17 |kjm2|  | 115\ |deg|\ C | 105\ |deg|\ C| 4200 MPa | 1.22 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+
| PET-CF  | 70 MPa | 35 MPa  | 8 |kjm2|   | 205\ |deg|\ C | 180\ |deg|\ C| 5000 MPa | 1.24 |gcm3| |
+---------+--------+---------+------------+---------------+--------------+----------+-------------+

+---------+------------------+---------------------+----------------------+
|         | Bed (\ |deg|\ C) | Nozzle (\ |deg|\ C) | Chamber (\ |deg|\ C) |
+=========+==================+=====================+======================+
| ASA     | 90-115           | 250-275             | 40-55                |
+---------+------------------+---------------------+----------------------+
| PA6-CF  | 40-80            | 255-295             | 35-55                |
+---------+------------------+---------------------+----------------------+
| PA12-CF | 40-80            | 265-295             | 35-55                |
+---------+------------------+---------------------+----------------------+
| PA11-CF | 40-80            | 265-295             | 35-55                |
+---------+------------------+---------------------+----------------------+
| PAHT-CF | 80-120           | 285-320             | 45-65                |
+---------+------------------+---------------------+----------------------+
| PPA-CF  | 100-125          | 280-315             | 40-65                |
+---------+------------------+---------------------+----------------------+
| Stiff PC| 110-135          | 275-305             | 55-90                |
+---------+------------------+---------------------+----------------------+
| PC-ABS  | 110-125          | 270-295             | 50-80                |
+---------+------------------+---------------------+----------------------+
| PC-CF   | 100-120          | 275-305             | 40-65                |
+---------+------------------+---------------------+----------------------+
| PET-CF  | 80-100           | 260-290             | 40-55                |
+---------+------------------+---------------------+----------------------+

Advanced/Niche Filaments
------------------------

PCTG
^^^^

PCTG (polycyclohexylenedimethylene terephthalate glycol-modified) can be thought of as a superior PETG. It has better flexibility, durability, and printability. It is also more resistant to wrapping and absorbs less water than PETG. However, it costs more and is more difficult to obtain, but prices could go down as adoption increases.

TPEs
^^^^

TPEs (thermoplastic elastomers) are a broad category of flexible filaments (includes TPU). Other common TPEs are SBS, SEBS, and PEBA. SEBS, unlike TPU, is stretchy and grippy. PEBA is stronger than TPU and has a high coefficient of restitution, meaning that it bounces back very easily.

PP
^^

.. Note::
    PP is *polypropylene*, not be to confused with other definitions.

PP is a semi-flexible commodity plastic, known for its low density and exceptional chemical resistance. It is often found in    food containers and ropes. Advantages include ultra-low density, chemical resistance, exceptional layer adhesion, and zero moisture absorption. Disadvantages include bed adhesion (it requires a specialized print surface), warping and low strength/stiffness.

POM
^^^

POM (acetal, delrin, polyoxymethylene) is a high-performance material used for low friction and high strength applications like gears. For printing, imagine ABS except low friction, higher stiffness, and formaldehyde instead of styrene. Advantages: stiff, tough, ultra-low friction. Disadvantages: extremely difficult to print.

PBT
^^^

Pure PBT (polybutylene terephthalate) is a semi-flexible, super tough material very similar to pure PA. Used most commonly for keycaps but also in many electronics components due to good electrical insulation properties. As a filament, the only one really available is PBT-GF20, which retains most of the same properties.

+---------------+---------------------+-----------+------------------------------+----------+------------------+
|               | Tensile Strength    | Notched   | Heat Deflection              | Flexural | Density          |
|               +-----------+---------+ IZOD      +---------------+--------------+ Mod.     |                  |
|               | XY        | Z       |           | 0.45 MPa      | 1.8 MPa      |          |                  |
+===============+===========+=========+===========+===============+==============+==========+==================+
| PCTG          | 50 MPa    | 40 MPa  | 10 |kjm2| | 75\ |deg|\ C  | 70\ |deg|\ C | 2040 MPa | 1.21 |gcm3|      |
+---------------+-----------+---------+-----------+---------------+--------------+----------+------------------+
| General TPEs  | 15-30 MPa | 22 MPa  | n/a       | n/a           | n/a          | n/a      | 1.05-1.15 |gcm3| |
+---------------+-----------+---------+-----------+---------------+--------------+----------+------------------+
| PP            | 35 MPa    | 35 MPa  | 65 |kjm2| | 80\ |deg|\ C  | 65\ |deg|\ C | 800 MPa  | 0.9 |gcm3|       |
+---------------+-----------+---------+-----------+---------------+--------------+----------+------------------+
| POM           | 64 MPa    | 45 MPa  | 80 |kjm2| | 142\ |deg|\ C | 125\ |deg|\ C| 2700 MPa | 1.41 |gcm3|      |
+---------------+-----------+---------+-----------+---------------+--------------+----------+------------------+

+---------------+------------------+---------------------+----------------------+
|               | Bed (\ |deg|\ C) | Nozzle (\ |deg|\ C) | Chamber (\ |deg|\ C) |
+===============+==================+=====================+======================+
| PCTG          | 75-85            | 250-265             | 25-45                |
+---------------+------------------+---------------------+----------------------+
| General TPEs  | 40-80            | 210-260             | 20-35                |
+---------------+------------------+---------------------+----------------------+
| PP            | 60-90            | 215-240             | 40-55                |
+---------------+------------------+---------------------+----------------------+
| POM           | 100-130          | 210-220             | 30-55                |
+---------------+------------------+---------------------+----------------------+

Super Polymers
--------------

PEEK
^^^^

PEEK (polyether ether ketone) is the strongest of the extreme materials. In its crystalline form, it is stiff, strong, tough, resists chemicals and temperatures over 250\ |deg|\ C, and is even self-extinguishing. It is perfect, right? Yes, until you consider: PEEK costs $600 per kilo. PEEK requires a 400\ |deg|\ C+ hotend, 140\ |deg|\ C bed and a minimum 70\ |deg|\ C chamber. PEEK warps like crazy, prints at 40mm/s max, guzzles moisture, and in general is absolutely not worth it. But if you need strength, you need strength.

PEKK
^^^^

PEKK (polyether ketone ketone) is like PEEK but prints much easier and is somehow even more expensive.

PEI
^^^

PEI (polyetherimide) is designed solely for the aerospace industry but somehow ended up on your print bed as well.

PEI 9085 |ndash| use 1010 it is better.

PEI 1010 |ndash| extremely good at everything for the low price of $200/kilo.

TPI
^^^

TPI (thermoplastic polyimide) is strong and has incredible high temperature performance. If you are even considering this stuff, or anything past PPS for that matter, just use metal, please, for the love of goodness.

+---------------+---------------------+-----------+------------------------------+----------+-----------------+
|               | Tensile Strength    | Notched   | Heat Deflection              | Flexural | Density         |
|               +-----------+---------+ IZOD      +---------------+--------------+ Mod.     |                 |
|               | XY        | Z       |           | 0.45 MPa      | 1.8 MPa      |          |                 |
+===============+===========+=========+===========+===============+==============+==========+=================+
| PEEK          | 100 MPa   | 15 MPa  | 6 |kjm2|  | 140\ |deg|\ C | n/a          | 2700 MPa | 1.3 |gcm3|      |
+---------------+-----------+---------+-----------+---------------+--------------+----------+-----------------+
| PEKK          | 105 MPa   | 30 MPa  | 15 |kjm2| | 150\ |deg|\ C | n/a          | 2680 MPa | 1.27 |gcm3|     |
+---------------+-----------+---------+-----------+---------------+--------------+----------+-----------------+
| PEI_1010      | 82 MPa    | 29 MPa  | 2 |kjm2|  | 208\ |deg|\ C | n/a          | 2150 MPa | 1.27 |gcm3|     |
+---------------+-----------+---------+-----------+---------------+--------------+----------+-----------------+
| TPI           | 72 MPa    | 19 MPa  | n/a       | 237\ |deg|\ C | n/a          | 2150 MPa | 1.27 |gcm3|     |
+---------------+-----------+---------+-----------+---------------+--------------+----------+-----------------+

+---------------+------------------+---------------------+----------------------+
|               | Bed (\ |deg|\ C) | Nozzle (\ |deg|\ C) | Chamber (\ |deg|\ C) |
+===============+==================+=====================+======================+
| PEEK          | 130-145          | 375-410             | 70-140               |
+---------------+------------------+---------------------+----------------------+
| PEKK          | 120-140          | 345-375             | 70-150               |
+---------------+------------------+---------------------+----------------------+
| PEI_1010      | 120-160          | 370-390             | 70-110               |
+---------------+------------------+---------------------+----------------------+
| TPI           | 180-220          | 420-445             | 80-160               |
+---------------+------------------+---------------------+----------------------+
