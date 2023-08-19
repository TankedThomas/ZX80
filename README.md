![Sinclair ZX80 Logo](https://raw.githubusercontent.com/TankedThomas/ZX80/master/Logo/sinclair_zx80_logo.svg)  
<small>Inaccurate logo recreation by me.</small>

# Sinclair ZX80 Replica

This repository contains my work-in-progress effort to recreate the Sinclair ZX80.

[Project Goals](#project-goals)  
[Future Goals](#future-goals)  
[Software](#software)  
[Project Status](#project-status)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Case](#case)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[RF Modulator](#rf-modulator)  
[Current Mysteries](#current-mysteries)  
[Contributing](#contributing)  
[Licensing](#licensing)  

## Project Goals

My goal is to recreate the original ZX80 schematic and PCB as accurately as possible in modern software so that replicas can be made via PCB manufacturers such as [JLCPCB](https://jlcpcb.com) and [PCBWay](https://www.pcbway.com).

This is both to preserve this piece of computing history and also make it accessible to those of us who don't have $1k+ to spend on an original machine of infamously dubious Sinclair quality.

Obviously this has been done before, but I have yet to find an open-source replica - most other versions, especially the open-source ones, take liberties with the original design (usually to improve it or to make use of modern, easier-to-obtain components).

I also plan to document the differences for the 60Hz (USA) variant, as the changes are primarily the addition or substitution of a small number of components, but this is very poorly documented as of now.

## Future Goals

Upon completion of this project, I would like to add a modified version that uses composite video with a built-in backporch, as well as other possibilities such as a 50Hz/60Hz switch.  
I would also like to add in the ZX81 modifications as an option for those who wanted an upgraded ZX80 i.e. a ZX81 in a ZX80 case and form factor.  
Finally, a future version should be able to be built exclusively with modern components. However, it is important to me that a 1:1 open-source replica is achieved first.

Hopefully, the schematics can be submitted to the awesome [Bit Preserve](https://github.com/baldengineer/bit-preserve/) project in the future - a project I recently found that has similar albeit less ambitious goals than my own (primarily that it isn't worried about also replicating the PCBs, just the schematics).

Finally, this is to be the first of (hopefully) many vintage computer replica projects from me, assuming everything goes smoothly.

## Software

All my work has been undertaken using [KiCad](https://www.kicad.org/).

The original schematic is &copy;Sinclair Research.  
[Grant Searle's redrawn schematic](http://searle.x10host.com/zx80/zx80.html) is the basis for this project, and mostly corrects the issues with the original schematic.  
However, Grant accidentally wrote `MALT` instead of `HALT` for the edge connector.  
Also, he did not fix the original schematic's error (or, at least, what I believe to be an error) where both `REFSH` and `RFSH` are used for the `REFRESH` pin, which creates an error in KiCad.

Grant's PCB foils are unfortunately under password protection within an encrypted PDF, so I could not directly import those images.  
Instead, I used [Martin's modified PCB foils](https://www.8bity.cz/zx80-replika/navod-na-stavbu-repliky-zx80/) as a template for placing and aligning parts on the PCB.  
Martin mentioned two corrections he made but does not elaborate, so I will have to look into this at a future date.

Therefore, both sets of PCB foils are included in this repository as reference material and the copyright belongs to their respective aforementioned owners.

I have also included realitively high quality scans of the original [assembly](https://github.com/TankedThomas/ZX80/blob/master/Docs/ZX80_Assembly_Part1.jpg) [guide](https://github.com/TankedThomas/ZX80/blob/master/Docs/ZX80_Assembly_Part2.jpg) (will add the source when I find it again), which has some contradictions to the oft-seen "original" schematic (including the one Grant provides), such as `C12` being `100nF` instead of `47nF`, and the ROM being a `2332` instead of an `8332`, and I have chosen to use the differences from this version instead as it appears to make more sense to me.

Finding high-resolution photos of the original PCB is quite difficult, but I have [included one that Grant supplied](https://github.com/TankedThomas/ZX80/blob/master/Docs/ZX80Iss2.jpg) as it has been invaluable (albeit imperfect) to me so far.

The replica keypad was made by using a screenshot from Grant's foils and then tracing it in Adobe Illustrator, so I have included the original Illustrator file in this repository.

## Project Status

Currently, [the schematic](https://github.com/TankedThomas/ZX80/blob/master/Docs/zx80_schematic_kicad.pdf) is more or less complete though not visually identical to the original.

The PCB is at a very early stage, and cannot be completed as the wiring of the schematic does not work in modern PCB CAD software, so tweaks will have to be made.  
As I am a novice with KiCad, I welcome any and all help to make this a workable board.  
The traces will be rounded to match the hand-drawn originals on the final version, but any existing traces are simply there for testing purposes and are not final.

Martin's PCB foils are included as a separate PCB file which could in theory be used to print a working replica board (but should not be used, as they are incomplete - the alignment of the two layers isn't perfect, drill holes are not marked, and planes have not been added).

I have created custom footprint and symbol libraries for this project so that any standard parts which needed modification (such as the ICs) to match the original schematic are provided, and to provide parts that wouldn't otherwise exist (such as the Astec UM1233 RF Modulator - more on this later).  
Some work still needs to be done, especially for component spacing (and especially the ceramic capacitors), and a lot of rejigging of the silkscreen is still required.

![Recreated ZX80 Keypad](https://raw.githubusercontent.com/TankedThomas/ZX80/master/Components/ZX80_Key.png)  

A [parts list is available as a CSV](https://raw.githubusercontent.com/TankedThomas/ZX80/master/Docs/zx80_parts_list.csv), though it is not completed yet (primarily the capacitors and the RAM/ROM ICs).  
Grant's parts list has some mistakes which I have corrected (to be detailed at a later date), and I am working on adding information about all the 60Hz-only components to the list as well.  

#### Case

A 3D-printable case is available, with [Spinetti's version](https://www.printables.com/model/490727-sinclair-zx80-replica-case) appearing to be the best so far.

The (supposedly) correct rivets can be had from AliExpress.  
There are meant to be two sizes of rivets used in the ZX80, with one size having both black and white rivets, whereas the other size only has white rivets.  
I will add information in the future once I can test these for myself.

#### RF Modulator

Astec's somewhat ubiquitous UM1233 UHF RF Modulator is an interesting footnote in this project. I have not managed to find any third-party KiCad libraries for this part and so I have recreated it myself to match the original ZX80 schematic.  

However, KiCad doesn't handle the logic of this part particularly well, so I've had to implement some work-arounds. If you have a better solution, please feel free to correct it yourself or let me know what can be done.  

Also, I cannot 3D model whatsoever, so I picked a similarly-shaped component's 3D model and stretched it into an approximately appropriate shape.  
If anyone would like to make a proper 3D model of the modulator, please let me know.  
I have original UHF and VHF modulators from Astec which I can measure if need be.  

In the interim, I am working on (and almost finished) recreating the UM1233 itself with KiCad so that at least there is a solid point of reference.  
These things are getting harder to come by, and in some cases, weren't used outside of European countries (e.g. the New Zealand and possibly Australian ZX81 used the USA VHF modulator from Astec instead, which has the RF jack on the opposite side of the modulator).  
Expect a repo for the UM1233 in the near future.

## Current Mysteries

- What was the original ROM chip used?  
&nbsp;&nbsp;One version of the Issue 2 schematic calls it an 8332 (of which I cannot find concrete evidence this even existed), and the other calls it a 2332.  
I have seen various other names thrown around, such as the TMS4732 (Texas Instruments 32k) and D2364C (64k, made by NEC I believe - seems likely this was used for the upgrade ROM i.e. the ZX81 ROM, not the original, as it's twice the required size).

- Why do many components seem to be of a non-standard size?  
&nbsp;&nbsp;Assuming the foil sizing in KiCad is correct (which it seems to be, but I'm not certain), many KiCad footprints don't line up with the vias on the foils.  
This may be due to how the original PCB was designed, where they weren't worried about making it an exact match for any one size (e.g. because the legs of components such as diodes and resistors are much longer than necessary anyway, so sizing leeway between each component is fine... until you try to replicate it with modern software).

- Can the power and ground pins for all the ICs that are not marked on the original schematic be hidden (instead of sitting off the bottom of the page) in the KiCad schematic without upsetting KiCad's Electrical Rules Checker?

- How can the address lines be connected like the original schematic without causing problems in KiCad?  
&nbsp;&nbsp;Kind of a major issue - this ties most of the address lines together, which isn't really correct (look at the rear PCB foil for a good example of how they're meant to linked). This throws all sorts of errors in KiCad, including making the PCB layout an inaccurate mess.

- Is ~{SYNC} used anywhere outside of IC19 pin 6?  

- Why the discrepancy between schematics (especially since both are for Issue 2)?

- What is the correct value for TR1?  
&nbsp;&nbsp;Supposedly, it should be a ZTX329.

- Why is a net label required for `A8'` to connect properly on IC2 (ROM) pin 23 when no other address lines appear to have this issue?

- What are the missing values for the 60Hz parts?  
&nbsp;&nbsp;There are photos floating around of 60Hz versions so this could be reverse-engineered from those, as I have done for some of the known values (check the parts list CSV).

If I think of more unknowns (at least to me), I'll add them later.  
Feel free to open an issue to contribute your own if you think it's crucial.

## Contributing

The further I get with this project, the more daunting it seems, as there is a ton of work left to do, and replicating something not designed in modern software with the limitations of modern software is surprisingly difficult.  
Therefore, if you would like to help, please feel free to open an issue if you find an obvious correction needs to be made (please don't do this for WIP parts unless you see a fatal error - they're obviously a work-in-progress for a reason), or make a pull request with any edits.

## Licensing

I will have to add this properly when I get more time in the future.  
In short:
- All work not done by me is copyright its respective owners, where the original licenses apply.  
- All work done by me is copyright Gare Ltd. but completely free for non-commercial use of any kind with attribution (but it'd be really cool if you contributed to this project instead of just making your own version).
- My ZX80 logo recreation was made using Wikipedia's SVG Sinclair logo as a base.