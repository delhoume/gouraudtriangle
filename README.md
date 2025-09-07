# gouraudtriangle
My first opensource code

Dated 1995 and posted to one of the usenet newsgroups, this little Postscript function allowed
printed OpenGL triangle output to reach a high visual quality.

OpenGL provides a feedback mecanism that allows to retrieve screen projected triangles.
Once sorted with a painter's algorithm they can be used as input to any graphics system function.
Each triangle vertex has its own color, and OpenGL can render it using the Gouraud shading model, where colors
are interpolated  after lighting (while Phong shading interpolates normals first).

In 1995 there was no graphics system that allowed native rendering of shaded triangles, PostScript output consisted of uniform color
triangles.

So I created this little PostScript function to achive smooth rendering of triangles, mostly for OpenGL or 3d usage.

Postcript is a complete programming language, derived from Forth, relatively hard to read and write for humans.
My code is recursive (not the best way to get good performance), but it should be if not easy to follow, at least possible.
Manipulate arbitrary structures o aa styack is tedious...
It comes with zero documentation except sample usage.

Each starting triangle is subdivided in 4 sub-triangles (3 would make very long and thin ones very quickly), until vertices have the same color
(given a configurable threshold), in this case recursion ends and a single color triangle is drawn.
Since then some people de-recursified it.


This code has the  explicit header 
```
% this code is free
% Frederic Delhoume (delhoume@ilog.fr)
```

that was not common in 1995...

It has been used by a number of 3d libraries (Coin3d, VRender), software or articles.
Mark Kilgard of OpenGL and GLUT fame used it in one GLUT's samples.

After 30 years I still find sometimes references to this code and a github search returns 26 hits
https://github.com/search?q=gouraudtriangle+delhoume


Here an illustration of the principle from a 2001 CodeProject article by Pierre Alliez.

<img width="600" height="599" alt="image" src="https://github.com/user-attachments/assets/eb31a223-d61d-407e-a0c9-00e158137213" />

And the ouput of the code, in Gimp on Windows.
<img width="1021" height="975" alt="image" src="https://github.com/user-attachments/assets/ac53758a-a2c8-427d-85cc-01b929d79c35" />
