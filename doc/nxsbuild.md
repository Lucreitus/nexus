# Nxsbuild

Nxsbuild generates a .nxs multiresolution mesh format given one or more .ply file:

	nxsbuild [OPTIONS] [PLY INPUT FILE(S)]

The process involves generating a sequence of increasingly coarse partitions of the mesh, interleaved with simplifications steps.
If you need compression or streaming capabilities a pass through nxsedit is needed.

### Options

**-o FILE**: filename of the nexus output, .nxs is added automatically. If not specified the name of the first .ply is used

**-f N**: average faces per patch, default value is 16286, must be less than 32000. Decreasing this value allow for better resolution control but reduces rendering performance and will increase size of the dataset. Small models with very large textures might require a small value

**-t N**: number of triangles in the top node, default 4096

**-d METHOD**: decimation method: quadric, edgelen. Default: quadric. Edgelen is much faster but will produce worse quality triangulation

**-s S**: scaling between level, default 0.5

**-O**: use original textures, no repacking

**-a S**: split notes adaptively [0...1] default 0.333

**-v S**: vertex quantization approximated to closest power of 2

**-q Q**: jpeg quality for texture [0-100] default 92

**-p**: generate a multiresolution point cloud

**-N**: force per vertex normals even in point clouds

**-n**: do not store per vertex normals

**-C**: save colors

**-c**: do not tore per vertex colors

**-u**: do not store per vertex texture coordinates

**-r M**: max ram used (in Megabytes, default 2000) WARNING: not a hard limit, increase at your risk :P



