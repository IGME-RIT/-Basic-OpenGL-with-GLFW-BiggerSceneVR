Documentation Author: Niko Procopi 2020

This tutorial was designed for Visual Studio 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

Nothing hard, just added a bunch of objects to the scene

In terms of level design for VR, it is clear in this tutorial that 3D effects
are most visible when the player is looking at an object that has other
objects behind it, and while the camera is in motion. 

3D is visible when moving towards a car with a torus behind it.
However, if you look at a torus in front of a black void, with no motion,
the 3D effects are not visible, even while wearing the headset

In terms of optimization and performance
You can see in the timers that each eye now takes significantly longer to render 
than before. With this new scene, we can optimize our geometry over the next 
few tutorials, in three different ways.

Benchmark on GTX 1050:

With blur, in center of world 
Performance of Vertex shader and Fragment shader
	1st Eye: 0.427ms
	2nd Eye: 0.429ms
	Blur eyes: 1.66ms
	Full Frame: 2.54ms

No blur, camera way off in the void
Performance of Vertex shader
	1st Eye: 0.243ms
	2nd Eye: 0.248ms
	Full Frame: 0.502ms

In the next few tutorials, we try to lower these numbers.
If you are on a laptop like me, elapsed time can vary due
to heating, and power usage. When comparing optimizations,
heating and power usage must be the same with each test

After finding which algorithm is fastest, the winning
algorithm gets ported to Vulkan