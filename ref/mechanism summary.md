The ILM Dinosaur Input Device (DID) was limited to relative positioning, both in how it tracked spatial translation and in the specific hardware used within its joints. It did not operate like a modern optical motion capture volume where a subject’s absolute coordinates are tracked freely in 3D space.

Here is how the system handled positioning at both the global and joint levels:

1. Global Translation (Root Positioning)
Unlike an actor in a mo-cap volume, the DID was not a wireless, free-floating device. It was a heavily modified physical stop-motion armature that had to be physically mounted to a mechanical rig or boom stand on a desk.

The device could translate a 3D model through a digital scene, but it did so mechanically. The mounting rig itself was equipped with sensors that tracked the displacement and orientation of the entire armature (acting as the root node). Therefore, global translation was determined by the physical extension and rotation of the mechanical boom it was tethered to, rather than absolute spatial tracking.

2. Joint Mechanics (Relative Encoders)
At the hardware level, the joints relied strictly on relative optical encoders. The developers (Brian Knep, Craig Hayes, Rick Sayre, and Tom Williams) evaluated true absolute encoders—which have a unique code etched onto an internal disk to provide an instantaneous absolute readout of the joint's state. However, absolute encoders were far too bulky and expensive to pack into the compact joints of a T-Rex or Velociraptor puppet.

Instead, they used relative encoders containing an internal disk with 255 simple alternating stripes. When an animator moved a limb, two out-of-phase detectors generated equal-period pulse trains. By counting the pulses, the hardware knew how far the joint had rotated, and the relative phase of the signals indicated the direction.  

3. The Software Tally
  
Because the hardware was entirely relative, the DID had no native concept of its absolute pose when powered on. The system had to be manually calibrated into a known "zero" or default pose. From that initialization point, a custom controller maintained a running tally of the pulses, continually calculating the absolute rotations in software and feeding that data to the wireframe models running on Silicon Graphics (SGI) workstations.

This clever mechanical bridging is what allowed Phil Tippett’s stop-motion animators—who were used to armatures physically tied down to sets—to bypass the steep learning curve of 1990s 3D software. They could rely on their deep understanding of mass, weight, and kinematics by pushing and pulling the physical armature, while the software seamlessly translated those relative mechanical pulses into digital motion.

Summarized by Google Gemini 3.1 Pro, 2026.

Sources:
Rickitt, Richard. *Special Effects: The History and Technique*. 2000.

Knep, Brian, et al. “Dinosaur Input Device.” Paper presented at SIGCHI. 1995.

Failes, Ian. “The Oral History of the Dinosaur Input Device or: How to Survive the Near Death of Stop-Motion.” Vfxblog, 2018. https://vfxblog.com/dinosaurinputdevice/.

Jacobson, Alec, et al. Tangible and Modular Input Device for Character Articulation. 2014.
