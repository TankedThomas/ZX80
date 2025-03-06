# Sinclair ZX80 Replica

## Changelog

07/03/2025
- Updated [README](https://raw.githubusercontent.com/TankedThomas/ZX80/master/README.md) with a grammatical fix and some extra info on the EPROM
- Reformatted changelog dates so they aren't ambiguous
- Added some info about two other (unrelated) ZX80 replicas, plus a bit about the status of this project (it WILL get finished once I have time, I promise!)

21/08/2023  
- Added a changelog  
- Updated [README](https://raw.githubusercontent.com/TankedThomas/ZX80/master/README.md) to answer some questions previously asked and add more info where applicable  
- Replaced schematic's address line wires with proper bus connections (apparently no way to make 90&deg; connection lines to match the original schematic though)  
- Changed all pins using ' to ~{} as bus name ranges in KiCad can't use proceeding special characters (both are "bar" or "inverted", apparently)  
- Added new and changed some existing tracks on PCB layout  
- Some PCB components moved/rotated into the correct place (there are likely many still in need of repositioning)  
- Footprints for resistors and capacitors modified to closer match the sizing on the original PCB
- The RF modulator symbol and footprint have been modified to try to get the wiring logic correct though it's still not right (VIDEO and 5V, and ~{SYNC} and 0V/GND are supposedly sharing pins but this isn't so straightforward to replicate in software)  
- Modified some other parts such as swapping input/output on voltage regulator and phono jacks to try to fix more of the aforementioned problems where wiring is apparently tied to two pins (someone who better understands how exactly this should be wired up would be invaluable)  
- Added [ERC.rpt](https://raw.githubusercontent.com/TankedThomas/ZX80/master/Docs/ERC.rpt) containing current schematic wiring issues as reported by the Electrical Rule Checker in KiCad  

20/08/2023  
- Initial Commit  
