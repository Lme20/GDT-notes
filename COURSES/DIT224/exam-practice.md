# EXAM PRACTICE

## 'real-time' Graphics pipeline

### Be able to sketch the graphics pipeline functional blocks and relation to hardware (slide 63 in LEC13)

### What parts does the real-time graphics pipeline have?

1. Application stage (mostly CPU)
-- examples: VFC, animations, collision detection, LOD
2. Geometry stage (mostly GPU)
-- examples: transformation + per vertex shading (lighting), tesselation
3. Rasterization stage (Fully GPU)
-- examples: rasterization, texturing, fragment shading, interpolation of per-vertex values, shadow mapping

## Rendering and Shading

### Real-time rendering principles in OpenGL (buffer types, shadow maps, how to do transparency)

### Fragment shader

### Phong shading - Phong's vs Blinn's model

#### Blinn's Model

### Ambient, diffuse, specular, emission

### Emission (explain it and the 3 other terms in real-time shading)

### Compute refraction and reflection vector

### Describe basic ray tracing algorithm

### Cascaded shadow maps (explain it)

### Shadow volumes (shaders p. )

### Describe adaptive supersampling scheme

### Perspective-correct interpolation (e.g., textures)

### Bandwidth (why it is a problem and how to solve it)

### Path tracing (why it is good compared to naive Monte Carlo sampling. Overall algorithm)

### Photon mapping (short summary of algorithm, why 2 maps are needed)

### Bidirectional Path Tracing, Metropolis Light Transport (just their names)

### Naive Monte Carlo sampling (exponentially growing ray tree)

### Rendering equation (know how to explain all its components)

check Acerola (youtube channel)

### Describe the Fresnel effect: Metal vs. dielectrics

- how do dielectrics behave? How does metal behave?
- draw the angle with intensity diagram for both dielectrics/metals (fresnel reflectance)

### Planar reflections

### Perspective-correct interpolation (e.g., linearly interpolate ($u_2/w_2x v_i/w_2x 1/w_i$)) (Hardware p.40)

### perpective correct texturing

### Denoising by Final Gather or AI

## Mathematics and Geometric tests

### Z-buffer algorithm

#### z-pass

#### z-fail

### Scaling matrix (transforms)

### Vertex order facing (triangle front and back)

### 4x4 matrices (projection matrix, camera-to-world, world-to-model, world-to-camera, and model-to-world matrix)

### Normal transforms

### Geometrical tests (know equations for ray, sphere, cylinder, plane, triangle)

### Ray/sphere intersection tests

### Ray/box intersection

### Ray/triangle intersection

### Separating axis theorem (know how to describe it)

### Dynamic separating axis theorem

### Sweep-and-prune (know how to explain it, what is it used for)

### Bresenham's line-drawing algorithm

### Simple DDA algorithm

## Collision detection and spacial structures

### Collision detection with BVH (know the pseudocode BVH/BV test collision between 2 objects), examples of bounding volumes (spheres, AABBs, OBBs, k-DOPs)

### Pruning of non-colliding objects

### Ray/BVH intersection test

### Top-down BVH, AABSP-tree/bottom-up construction of BVH

### Axis-aligned BSP tree (where geometries are stored: in the leaves)

### Octrees/quadtrees

### Portal culling or culling techniques (e.g., backface culling: screen-space vs. eye-space)

### Draw spatial data structures (octree/quadtree, AABSP-tree/kd-tree, polygon-aligned BSP tree, Sphere/AABB/OBB tree)

### Grid (plain/hierarchical/recursive), mailboxing

### What is sweep-and-prune used for? (broad-phase collision detection)

## Raytracing -- lighting

### 3 types of algorithms with rays (fast but not exact, why?)

### Describe how ray tracing uses constructive solid geometry

### Draw angle vs. intensity diagrams for dielectrics/metals (Fresnel reflectance)

### Why can shadow rays be faster than other rays?

### Know what jittering is

## Scene management

### Scene graphs

### LODs (describe them)

### Taxonomy: sort first, middle, last fragment, last image

### What is a skip-pointer tree?

### What is a Kd-tree?

### perpective correct texturing

know how to draw: 
axis-aligned bounding box hierarhy
axis-aligned BSP (binary space-partitioning) tree
OBB hierarchy
octree or quatree
a grid 
recursive and hierarchical grid (raytracing2 - p25)

why is bubble efficient when we have high frame-to-frame coherency (that everything stays consistent) regarding the objects to be sorted per frame?


correct plane equation: p x n - d