.. include:: <isonum.txt>

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
   :scale: 25%

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
   :scale: 25%

.. image:: images/3d-printing/assembled-multipart.jpg
   :alt: An assembled version of what was printing in the previous image
   :scale: 25%

This assembly is a good example of considering part orientation, draft angles, and stress vectors in each part of the design. Complex parts can be made strong and without any support by simply splitting it up in the right way.

Material Selection
------------------

For the purposes of FTC, PLA and PETG are all you need about 90% of the time. Everything else in here is for reference if you need very specific properties or are looking into other projects. Though we do recommend swapping your PETG with PCTG.

- On 3D prints, orientation matters. This is because as the printer stacks layers, they do not adhere perfectly, and there are gaps between extrusion lines. This makes it so that vertically printed objects are far weaker than objects printed flat on the print bed.

.. warning:: All filaments decompose at high temperatures and release potentially harmful fumes. Some byproducts are more harmful than others. Additionally, CF and GF filaments release microscopic fibers that can collect in your lungs. While filaments like Delrin and ABS are the worst and require special HEPA filters and sealed enclosures, you should still print all filaments in a well-ventilated area!!

- Filaments can be annealed. This is when they are heated for long periods of time over their glass transition temperature (Tg) and then allowed to cool slowly. This alters the crystallinity of the filament and reduces internal stresses, ultimately making it slightly stiffer and far more temperature resistant. For example, PLA’s softening temperature increases from 55ºC to nearly 140ºC. Additionally, with other materials like nylon, annealing can dramatically reduce its creep under load. Note that annealed parts may shrink significantly (several percent for PLA).
- All filaments absorb moisture and should be kept dry. Moisture can lead to reduction in print quality due to bubbles forming where water is boiling, and the water reacting and breaking down the polymer. Some filaments do not absorb water, such as: PCTG, PP, PPS, or SEBS.

.. admonition:: Fun fact

    specifically in nylons, especially moisture-conditioned PA6 and PA6,6, water acts as a plasticizer and can make it upwards of ten times tougher but will nearly halve its tensile strength.

Fiber-filled filaments
^^^^^^^^^^^^^^^^^^^^^^

.. |nbhp| unicode:: U+2011

Materials ending in |nbhp|\ CF and |nbhp|\ GF are common composite materials in 3d printing. |nbhp|\ CF denotes the addition of carbon fibers to add stiffness, strength, and temperature resistance to a filament. Similarly |nbhp|\ GF filaments add glass fibers for the same reason. Such modifiers also help reduce warping.

.. warning:: Keep in mind that CF and GF filaments will claim to be tougher and have better layer adhesion. Know that **this is usually a lie** unless you print at least 10\ |deg| C above the recommended printing temperature, and even then, they’ll still be much more brittle.

Key differences

- CF has little effect on the density of a filament, while GF can significantly increase it.
- CF adds more stiffness, strength, and temperature resistance to the filament, but GF is typically less brittle than CF.
- GF filaments can be colored with normal colors, while CF is stuck with the black CF in it, thus colored CF filaments appear darker and non-uniform in color (little specs of black are visible).

A few rules of thumb and pinky, and miscellaneous tips
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Stiffer = more brittle.
2. Do research before printing a new filament. ESPECIALLY FLEXIBLES.
3. CF is stronger, GF is tougher (in relation to each other).
4. If there’s little to no documentation for a filament, don’t use it. There’s a reason it’s not documented. Example: HDPE. I needn’t say more.

.. tip:: Expensive filament isn’t (usually) worth it. Avoid spending more than $40/kilo. Some cheap but high-performance filaments are:

    * Elegoo PAHT-CF – $39.99 for 1 kg
    * SUNLU PC-ABS – $39.99 for 1 kg
    * Polymaker PLA blends (HT, Polymax) – $30-40 for 1 kg
    * Pretty much any ASA – $20-35 for 1 kg

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

+-------+------------------+-----------+-----------------------------+----------+------------+----------------------------+
|       | Tensile Strength | Impact    | HDT (MPa)                   | Flex.    | Density    | Print Temp (\ |deg|\ C)    |
|       +--------+---------+           +--------------+--------------+ Mod.     |            +-----------+----------------+
|       | XY     | Z       |           | 0.45         | 1.8          |          |            | Bed       | Nozzle         |
+=======+========+=========+===========+==============+==============+==========+============+===========+================+
| PLA   | 55 MPa | 45 MPa  | 5 kJ/m²   | 57\ |deg|\ C | 52\ |deg|\ C | 2400 MPa | 1.24 g/cm³ | XX-XX     | XXX-XXX        |
+-------+--------+---------+-----------+--------------+--------------+----------+------------+-----------+----------------+
| PETG  | 41 MPa | 36 MPa  | 3.9 kJ/m² | 68\ |deg|\ C | 65\ |deg|\ C | 1700 MPa | 1.25 g/cm³ | XX-XX     | XXX-XXX        |
+-------+--------+---------+-----------+--------------+--------------+----------+------------+-----------+----------------+
| ABS   | 39 MPa | 35 MPa  | 30 kJ/m²  | 87\ |deg|\ C | 75\ |deg|\ C | 1700 MPa | 1.05 g/cm³ | XX-XX     | XXX-XXX        |
+-------+--------+---------+-----------+--------------+--------------+----------+------------+-----------+----------------+
| TPU   | 41 MPa | 24 MPa  | n/a       | 70\ |deg|\ C | 50\ |deg|\ C | n/a      | 1.25 g/cm³ | XX-XX     | XXX-XXX        |
+-------+--------+---------+-----------+--------------+--------------+----------+------------+-----------+----------------+

.. csv-table::
    :header: "Material", "Tensile XY", "Tensile Z", "Impact", "Heat Deflection (0.45 MPa)", "Heat Deflection (1.8 MPa)", "Flexural Modulus", "Density"
    :widths: 10, 14, 12, 14, 15, 15, 14, 15

    "ASA", "41 MPa", "35 MPa", "40 kJ/m^2", "90\ |deg|\ C", "85\ |deg|\ C", "2060 MPa", "1.05 g/cm^3"
    "PA6", "82 MPa", "18 MPa", "18 kJ/m^2", "180\ |deg|\ C", "165\ |deg|\ C", "7000 MPa", "1.16 g/cm^3"
    "PA12", "78 MPa", "30 MPa", "16 kJ/m^2", "170\ |deg|\ C", "160\ |deg|\ C", "4000 MPa", "1.06 g/cm^3"
    "PA11", "64 MPa", "no data", "17 kJ/m^2", "190\ |deg|\ C", "150\ |deg|\ C", "6000 MPa", "1.11 g/cm^3"
    "PAHT", "80 MPa", "50 MPa", "9 kJ/m^2", "210\ |deg|\ C", "200\ |deg|\ C", "9520 MPa", "1.08 g/cm^3"
    "PPA", "101 MPa", "22 MPa", "8 kJ/m^2", "227\ |deg|\ C", "N/A\ |deg|\ C", "9860 MPa", "1.25 g/cm^3"
    "PC_Stiff", "70 MPa", "53 MPa", "4 kJ/m^2", "110\ |deg|\ C", "105\ |deg|\ C", "2650 MPa", "1.2 g/cm^3"
    "PC_ABS", "58 MPa", "30 MPa", "120 kJ/m^2", "110\ |deg|\ C", "105\ |deg|\ C", "2000 MPa", "1.24 g/cm^3"
    "PC_CF", "70 MPa", "no data", "17 kJ/m^2", "115\ |deg|\ C", "105\ |deg|\ C", "4200 MPa", "1.22 g/cm^3"
    "PET_CF", "70 MPa", "35 MPa", "8 kJ/m^2", "205\ |deg|\ C", "180\ |deg|\ C", "5000 MPa", "1.24 g/cm^3"


"PCTG", "50 MPa", "40 MPa", "10 kJ/m^2", "75\ |deg|\ C", "70\ |deg|\ C", "2040 MPa", "1.21 g/cm^3"
"TPE_General", "15-30 MPa", "22 MPa", "N/A kJ/m^2", "N/A \ |deg|\ C", "N/A \ |deg|\ C", "N/A  MPa", "1.05-1.15 g/cm^3"
"PP", "35 MPa", "35 MPa", "65 kJ/m^2", "80\ |deg|\ C", "65\ |deg|\ C", "800 MPa", "0.9 g/cm^3"
"PEEK", "100 MPa", "15 MPa", "6 kJ/m^2", "140\ |deg|\ C", "n/a", "2700 MPa", "1.3 g/cm^3"
"PEKK", "105 MPa", "30 MPa", "15 kJ/m^2", "150\ |deg|\ C", "n/a", "2680 MPa", "1.27 g/cm^3"
"PEI_1010", "82 MPa", "29 MPa", "2 kJ/m^2", "208\ |deg|\ C", "n/a", "2150 MPa", "1.27 g/cm^3"
"TPI", "72 MPa", "19 MPa", "n/a", "237\ |deg|\ C", "n/a\ |deg|\ C", "2150 MPa", "1.27 g/cm^3"

PLA (Polylactic Acid)
^^^^^^^^^^^^^^^^^^^^^

PLA is the most common printing plastic due to low cost and ease of printing. Strengths: Stiff, reasonably strong, easy to print, dirt cheap, and has good layer adhesion. Weaknesses, PLA has poor heat resistance, high creep even under small loads, and brittleness.

PLA-CF/GF – extremely brittle and actually weaker than regular PLA. Do not recommend.

PETG (Polyethylene Terephthalate Glycol)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

PETG is a glycol-modified PET to allow it to print easier. Despite being in the PET family, IT IS NOT RECYCLEABLE! Strengths: higher temperature resistance than PLA, is less brittle, low creep under small loads, dirt cheap, and good layer adhesion. Weaknesses: it’s slightly harder to print and is less stiff and strong.

- Tensile strength XY = 41 MPa
- Tensile strength Z = 36 MPa
- Impact strength = 3.9 kJ/m2
- Heat deflection temperature = 68ºC
- Heat deflection temperature = 65ºC
- Flexural modulus XY = 1700 MPa
- Density = 1.25 g/cm3

PETG-CF – can help with common issues printing PETG such as blobbing, sagging, and minor warping, as well as helping layer adhesion when printed at high temperatures.

ABS (Acrylonitrile Butadiene Styrene)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The OG printer filament, commonly used in LEGOs and “cheap plastic” components. Strengths include higher temperature resistance, great toughness, and high print speed. Weaknesses include low strength/stiffness, varying layer adhesion due to warping, harder to print, and foul-smelling, toxic styrene fumes while printing.

Mechanical properties:

- Tensile strength XY = 39 MPa
- Tensile strength Z = 35 MPa
- Impact strength = 30 kJ/m2
- Heat deflection temperature (0.45MPa) = 87ºC
- Heat deflection temperature (1.8Mpa) = 75ºC
- Flexural modulus XY = 1700 MPa
- Density = 1.05 g/cm3

ABS-CF/GF – Makes ABS stiffer (ruining its toughness), though helps reduce warping and increases temperature resistance. ABS-GF is more useful due to being less brittle.

TPU (Thermoplastic Polyurethane)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A soft, flexible material that comes in many hardnesses for many applications. Most commonly in printing is the 95A durometer. Strengths include good strength, near perfect layer adhesion, flexibility, and because of the flexibility, theoretically infinitely high toughness. Weaknesses include difficulty of printing for many reasons and a disappointing lack of grippiness (it’s plastic, not rubber).

Mechanical properties:

- Tensile strength XY = 41MPa
- Tensile strength Z = 24 MPa
- Impact strength = N/A
- Heat deflection temperature (0.45MPa): 70ºC
- Heat deflection temperature (1.8MPa): 50ºC
- Flexural modulus XY = N/A
- Density = 1.25g/cm3

TPU-CF – Yes, this exists. Somehow increases both the tensile and impact strength of TPU. Good for things like timing belts.

Engineering Grade Filaments - "It Needs to be Strong"
-----------------------------------------------------

ASA (Acrylonitrile Styrene Acrylate)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Used in the industry in medical facility pipes due to chemical resistance. Like ABS, but with the added benefit of chemical and UV resistance and less toxic fumes while printing.

Mechanical properties:

- Tensile strength XY = 41MPa
- Tensile strength Z = 35MPa
- Impact strength = 40 kJ/m2
- Heat deflection temperature (0.45MPa) = 90ºC
- Heat deflection temperature (1.8Mpa) = 85ºC
- Flexural modulus XY = 2060MPa
- Density = 1.05 g/cm3

ASA-CF

PA (Nylon, Polyamide)
^^^^^^^^^^^^^^^^^^^^^

Nylon is a strong, tough, and lightweight family of plastics used in almost every major industry due to a broad range of favorable properties – examples include everything from zip-ties to toothbrush bristles to fabrics to fuel tanks, gears, engine covers and much more.
Note – PA as a filament is usually, and is most useful, in the CF (carbon fiber) form. This is when small, chopped carbon fibers are added to increase strength, stiffness, and heat resistance. More on CF later. Beware that CF filaments are highly abrasive and require a hardened steel or gemstone nozzle. The following refer to PA-CF filaments:
PA6 – the most common nylon type for all applications. It’s stiff, strong, tough, temperature resistant, lightweight, and has good layer adhesion. However, it is much more expensive, hard to print, and absorbs large amounts of moisture from the environment which can dramatically change its mechanical properties. IT MUST BE DRIED BEFORE PRINTING.

Mechanical properties (dry):

•	Tensile strength XY = 82 MPa
•	Tensile strength Z = 18 MPa
•	Impact strength = 18 kJ/m2
•	Heat deflection temperature (0.45MPa) = 180C
•	Heat deflection temperature (1.8Mpa) = 165C
•	Flexural modulus XY = 7000 MPa
•	Density = 1.16 g/cm3

PA6,6 – Similar to PA6, except even stronger and stiffer, but is rare to find as a filament. Little data is available regarding 3D printed PA6,6.

PA12 – The other most common form of nylon in 3D printing. Slightly weaker mechanical properties compared to PA6, but boasts lighter weight and much lower moisture absorption, making it better retain its properties under harsh chemical conditions.

Mechanical properties:

- Tensile strength XY = 78 MPa
- Tensile strength Z = 30 MPa
- Impact strength = 16 kJ/m2
- Heat deflection temperature (0.45MPa) = 170C
- Heat deflection temperature (1.8Mpa) = 160C
- Flexural modulus XY = 4000 MPa
- Density = 1.06 g/cm3

PA11 – A naturally derived and renewable form of nylon. Like the ASA of nylons, it is more ductile, temperature resistant, and can handle UV and chemicals better compared to PA12.

Mechanical properties:

- Tensile strength XY = 64 MPa
- Tensile strength Z = No data
- Impact strength = 17 kJ/m2
- Heat deflection temperature (0.45MPa) = 190ºC
- Heat deflection temperature (1.8Mpa) = 150ºC
- Flexural modulus XY = 6000 MPa
- Density = 1.11 g/cm3

PAHT – Usually a PA12 alloy designed for high temperatures. Its properties take the strengths of both PA6 and PA12 while eliminating the weaknesses. Excellent for all extremely demanding applications. Its weaknesses are price and printability. Due to high CF content, it has a sandpaper-like surface texture and thus has lower dimensional accuracy due to the rough surface.

Mechanical properties:

•	Tensile strength XY = 80 MPa
•	Tensile strength Z = 50 MPa
•	Impact strength = 9 kJ/m2
•	Heat deflection temperature (0.45MPa) = 210C
•	Heat deflection temperature (1.8Mpa) = 200C
•	Flexural modulus XY = 9520 MPa
•	Density = 1.08 g/cm3

PPA – Nylon copolymer polyphthalamide. Typically used in the automotive industry for parts under extreme stress, heat, and chemicals. It is the strongest and stiffest filament printable on most consumer-grade printers. Its weaknesses are extremely high price and brittleness.

Mechanical properties:

•	Tensile strength XY = 101 MPa
•	Tensile strength Z = 22 MPa
•	Impact strength = 8 kJ/m2
•	Heat deflection temperature (0.45MPa) = 227C
•	Heat deflection temperature (1.8Mpa)
•	Flexural modulus XY = 9860 MPa
•	Density = 1.25 g/cm3


PC (Polycarbonate)
^^^^^^^^^^^^^^^^^^

Polycarbonate is most often used in sheet form, where it is used for greenhouse panels and things that require extreme toughness and high visual clarity such as bulletproof glass. PC filaments are excellent for structural components that need to take a beating, and applications requiring medium-high temperature resistance such as electronics housings. As a filament, it’s almost never in its pure form due to extreme difficulty of printing. As a result, we have categorized two main types of blends: “stiff” PC and “flexy” PC.
“Stiff” PC: much closer to pure polycarbonate. Strengths include remarkably high strength (the highest of the common non-fiber filled filaments), good stiffness, high temperature resistance, and low creep. Weaknesses include brittleness, warping, and high print temperatures.

Mechanical properties:

- Tensile strength XY = 70 MPa
- Tensile strength Z = 53 MPa
- Impact strength = 4 kJ/m2
- Heat deflection temperature (0.45MPa) = 110ºC
- Heat deflection temperature (1.8Mpa) = 105ºC
- Flexural modulus XY = 2650 MPa
- Density = 1.2 g/cm3

“Flexy” PC: Polycarbonate with additives such as PBT, ABS or PETG. Strengths include good strength, high temperature resistance, outstanding toughness, great layer adhesion due to increased flexibility, and less warping than pure PC. Weaknesses include high price, some warping, and lower stiffness.

Mechanical properties (PC-ABS):

- Tensile strength XY = 58 MPa
- Tensile strength Z = 30 MPa
- Impact strength = 120 kJ/m2
- Heat deflection temperature (0.45MPa) = 110ºC
- Heat deflection temperature (1.8Mpa) = 105ºC
- Flexural modulus XY = 2000 MPa
- Density = 1.24 g/cm3

PC-CF – Takes brittle PC and makes it more brittle. However, it does increase strength and stiffness to an even higher level, rivaling PAHT-CF, PET-CF, and others. Also dramatically reduces warping and some creep at high temperatures that PC can experience.

Mechanical properties:

- Tensile strength XY = 70
- Tensile strength Z = No data
- Impact strength = 17 kJ/m2
- Heat deflection temperature (0.45MPa) = 115ºC
- Heat deflection temperature (1.8Mpa) = 105ºC
- Flexural modulus XY = 4200 MPa
- Density = 1.22 g/cm3

PET-CF (Polyethylene Terephthalate)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Recyclable in its pure form, but NOT as a CF blend. PET is used in printing primarily in its CF form for incredible stiffness, temperature resistance and low moisture absorption compared to nylons. Weaknesses include brittleness, high cost, and high print temperatures at the limit of most consumer-grade printers.

Mechanical properties:
•	Tensile strength XY = 70 MPa
•	Tensile strength Z = 35 MPa
•	Impact strength = 8 kJ/m2
•	Heat deflection temperature (Annealed) (0.45MPa) = 205ºC
•	Heat deflection temperature (Annealed) (1.8Mpa) = 180ºC
•	Flexural modulus XY = 5000 MPa
•	Density = 1.24 g/cm3

Advanced/Niche Filaments - the Cool Kids' corner (or the "I hate myself" corner)
--------------------------------------------------------------------------------

PCTG (Polycyclohexylenedimethylene Terephthalate Glycol-modified)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Like PETG, only superior in literally every aspect. Only weakness: it costs more and can be difficult to obtain. That said, as it hits the consumer market more, the price will go down, *wink* Memorize the chemical name to impress your friends.

Mechanical properties:

- Tensile strength XY = 50 MPa
- Tensile strength Z = 40 MPa
- Impact strength = 10 kJ/m2
- Heat deflection temperature (0.45MPa) = 75ºC
- Heat deflection temperature (1.8Mpa) = 70ºC
- Flexural modulus XY = 2040 MPa
- Density = 1.21 g/cm3

TPEs (Thermoplastic Elastomers)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A broader category of flexible filaments (includes TPU). Other common TPEs are SBS, SEBS, and PEBA. SEBS, unlike TPU, is stretchy and grippy. PEBA is stronger than TPU and has a high coefficient of restitution, meaning that it bounces back very easily.

Mechanical properties: (General ranges)

- Tensile strength XY = 15-30MPa
- Tensile strength Z = 22MPa
- Impact strength = N/A
- Heat deflection temperature (0.45MPa) = N/A
- Heat deflection temperature (1.8Mpa) = N/A
- Flexural modulus XY = N/A
- Density = 1.05-1.15 g/cm3

PP (WHAT? It’s Polypropylene)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

PP is a semi-flexible commodity plastic, known for its low density and exceptional chemical resistance. It’s used in food containers, ropes, and more. Advantages include ultra-low density, chemical resistance, exceptional layer adhesion, and zero moisture absorption. Disadvantages include bed adhesion (it requires a specialized print surface), warping and low strength/stiffness.

Mechanical properties:

- Tensile strength XY = 35MPa
- Tensile strength Z = 35MPa
- Impact strength = 65 kJ/m2
- Heat deflection temperature (0.45MPa) = 80C
- Heat deflection temperature (1.8Mpa) = 65C
- Flexural modulus XY = 800MPa
- Density 0.9 g/cm3

POM (Acetal, Delrin, Polyoxymethylene)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A high-performance material used for low friction and high strength applications like gears. For printing, imagine ABS except low friction, higher stiffness, and formaldehyde instead of styrene. Pros: Stiff, tough, ultra-low friction. Cons: extremely difficult to print.

Mechanical properties:

- Tensile strength XY = 64MPa
- Tensile strength Z = 45MPa
- Impact strength = 80 kJ/m2
- Heat deflection temperature (0.45MPa) = 142C
- Heat deflection temperature (1.8Mpa) = 125c
- Flexural modulus XY = 2700MPa
- Density = 1.41 g/cm3

PBT (Polybutylene Terephthalate)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Pure PBT is a semi-flexible, super tough material very similar to pure PA. Used most commonly for keycaps but also in many electronics components due to good electrical insulation properties. As a filament, the only one really available is PBT-GF20, which retains most of the same properties.

Super Polymers – Just Use Metal.
--------------------------------

PEEK (Polyether ether ketone)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Strongest of the extreme materials. In its crystalline form, it’s stiff, strong, tough, resists chemicals and temperatures over 250C, and is even self-extinguishing. It’s perfect, right? Yes, until you consider: PEEK costs $600 per kilo. PEEK requires a 400C+ hotend, 140C bed and a minimum 70C chamber. PEEK warps like crazy, prints at 40mm/s max, guzzles moisture, and in general is absolutely not worth it. But if you need strength, you need strength.

Mechanical properties:

- Tensile strength XY = 100 MPa
- Tensile strength Z = 15 MPa
- Impact strength = 6 kJ/m^2
- Heat deflection temperature (0.45MPa) = 140C
- Heat deflection temperature (1.8Mpa) =
- Flexural modulus XY = 2700 MPa
- Density = 1.3 g/cm^3

PEKK (Polyether ketone ketone)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Like PEEK but prints much easier and is somehow even more expensive.

Mechanical properties:

- Tensile strength XY = 105 MPa
- Tensile strength Z = 30 MPa
- Impact strength = 15 kJ/m^2
- Heat deflection temperature (0.45MPa) = 150C
- Heat deflection temperature (1.8Mpa) =
- Flexural modulus XY = 2680 MPa
- Density = 1.27 g/cm^3

PEI (Polyetherimide)
^^^^^^^^^^^^^^^^^^^^

Designed solely for the aerospace industry but somehow ended up on your print bed as well.

PEI 9085 – use 1010 it’s better.

PEI 1010 – extremely good at everything for the low price of $200/kilo.

Mechanical properties:
- Tensile strength XY = 82 MPa
- Tensile strength Z = 29 MPa
- Impact strength = 2 kJ/m2
- Heat deflection temperature (0.45MPa) = 208C
- Heat deflection temperature (1.8Mpa)
- Flexural modulus XY = 2150 MPa
- Density = 1.27 g/cm3


TPI (Thermoplastic Polyimide)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you’re even considering this stuff, or anything past PPS for that matter, just use metal, please, for the love of goodness.

Mechanical properties:

- Tensile strength XY = 72 MPa
- Tensile strength Z = 19 MPa
- Impact strength = No data available
- Heat deflection temperature (0.45MPa) = 237C
- Heat deflection temperature (1.8Mpa)
- Flexural modulus XY = 2150 MPa
- Density = 1.27 g/cm3

WE TAKE NO RESPONSIBILITY IN ANY PERSONAL HARM THAT MAY COME DUE TO THE USE OF THIS INFORMATION AS THE HOLY TRUTH OF THE UNIVERSE.
