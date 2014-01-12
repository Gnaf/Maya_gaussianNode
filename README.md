Maya_gaussianNode
=================

Maya gaussianNode plugin

------------------------

In Maya pluginmanager Load compiled gaussian.mll

-------------------------

To build gaussian.mll in visual studio:


Visual studio project prefs change:

-Linker general: Output File: change .dll into .mll

-Linker general additional library directories:  C:\Program Files\Autodesk\Maya2012\lib

-Linker input additional dependencies: Foundation.lib;OpenMaya.lib;OpenMayaUI.lib;OpenMayaAnim.lib; 

OpenMayaFX.lib;OpenMayaRender.lib;Image.lib;opengl32.lib;glu32.lib
								
-Linker Command Line Additional Options: /export:initializePlugin /export:uninitializePlugin

-C/C++ general Additional Include Directories: C:\Program Files\Autodesk\Maya2012\include

-C/C++ preprocessor Preprocessor Defenitions: WIN32;NDEBUG;_ WINDOWS;NT_ PLUGIN;REQUIRE_IOSTREAM

-------------------------------------------------------------------------------------

-Visual studio: start win32 project: .dll and empty

-compile: config x64

-------------------------------------------------------------------------------------

Test:
-----

Maya mel cmdline: createNode gaussian, to create gaussianNode

----------

gaussianNode inValue, Magnitude, Mean and Variance are editable.

set Magnitude on 5 and Variance on 0.9

----------

Create 2 polygon primitives in Maya

Maya hypergraph: connect output_polygonNode1_translateX to gaussian_Invalue,

gaussian_OutValue to input_polygonNode2_translateY

----------

move objectNode1 over x to objectNode2, objectnode2 responds on y. (Bell Curve)

-------------------------------------------------------------------------------------
