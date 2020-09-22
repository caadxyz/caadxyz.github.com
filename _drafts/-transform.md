---

layout: post
title: "World, View and Projection Transformation Matrices"
permalink: "blog/transform"
categories:
  - zh
comments_id: 15

---

![generic transform](/assets/images/15-transform/genericTransform.png)

> The engines don’t move the ship at all. The ship stays where it is and the engines move the universe around it.
-- <cite>Futurama</cite>

An introduction to matrices

Simply put, a matrix is an array of numbers with a predefined number of rows and colums. For instance, a 2x3 matrix can look like this :

In 3D graphics we will mostly use 4x4 matrices. They will allow us to transform our (x,y,z,w) vertices. This is done by multiplying the vertex with the matrix :

Matrix x Vertex (in this order !!) = TransformedVertex

This isn’t as scary as it looks. Put your left finger on the a, and your right finger on the x. This is ax. Move your left finger to the next number (b), and your right finger to the next number (y). You’ve got by. Once again : cz. Once again : dw. ax + by + cz + dw. You’ve got your new x ! Do the same for each line, and you’ll get your new (x,y,z,w) vector.


**reference**  

* http://www.opengl-tutorial.org  
* http://www.codinglabs.net/article_world_view_projection_matrix.aspx  
* http://ogldev.org/index.html  
* https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/projection-matrix-introduction  
