README

*** This project has been discontinued and is no longer supported. Thank you for all the stars and contributions! Please see my Blender-to-OpenGL ES tutorial series for a similar project <http://www.raywenderlich.com/48293/how-to-export-blender-models-to-opengl-es-part-1> ***

mtl2opengl Version 1.3 (28 September 2013)
Copyright © 2013 Ricardo Rendon Cepeda
<http://www.rendoncepeda.com/>


ABOUT
mtl2opengl is a perl script for converting .obj and .mtl data files into arrays compatible with OpenGL ES on iOS devices.


INSTRUCTIONS
To run the script with its default settings, type the following into the command line terminal:

./mtl2opengl.pl model.obj model.mtl

where model.obj and model.mtl are the .obj and corresponding .mtl files of your 3D model.


ACCOMPANYING FILES
The full project includes:
-Resources: Example 3D models for a cube and pyramid shape, with .obj, .mtl, .png (texture) files and the resulting .h header files produced by the script.
-Xcode: A full Xcode project showing how to implement the resulting .h files on an iPhone application using GLKit and OpenGL ES with Vertex and Fragment shaders.


ACKNOWLEDGEMENTS
This script is based on the work of:
Heiko Behrens
<http://heikobehrens.net/2009/08/27/obj2opengl/>
Margaret Geroch
<http://people.sc.fsu.edu/~jburkardt/pl_src/obj2opengl/obj2opengl.html>


VERSION HISTORY

Version 1.3
-----------
- Removed whitespace as suggested by @GuntisTreulands, resulting in a smaller header file.
- The example Xcode project has been updated to include the script changes.
- The example Xcode project has been updated to iOS 7.
- The example Xcode project has better OpenGL ES performance for iPhone 4 due to decreased depth format and no multisample (now runs at 30 FPS)
- The example Xcode project now uses gesture recognizers to transform the model: translate XY (1-finger pan), rotate XY (2-finger pan), rotate Z (rotation), scale XYZ (pinch).
- Resulting file reductions
-- cubeOBJ.h: 5.5 MB -> 4.6 MB
-- cubeMTL.h: 2.0 KB -> 1.0 KB
-- Total reduction is approximately 16%

Version 1.2
-----------
- Reduced precision of outputs to 3 decimal places, resulting in a smaller header file.
- Removed the "face line" comment occuring every 3 vertices, resulting in a smaller header file.
- Vertices are written to the header file in sequential order, according to their associated material.
- Materials are grouped to their appropriate vertices by keeping track of *first* and *count* integers for use with glDrawArrays(GL_TRIANGLES, *first*, *count*).
- The new format mimics the the OBJ/MTL behavior where each face in the OBJ file points to a material in the MTL file.
- The example Xcode project has been updated to include the script changes.
- Resulting file reductions
-- cubeOBJ.h: 17.0 MB -> 5.5 MB
-- cubeMTL.h: 13.2 MB -> 2.0 KB
-- Total reduction is approximately 82%

Version 1.1
-----------
Original
