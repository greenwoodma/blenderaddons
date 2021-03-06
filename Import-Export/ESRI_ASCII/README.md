# Import ESRI ASCII Format (.asc)

This addon allows you to import raster data stored using the
[ESRI ASCII format](http://resources.esri.com/help/9.3/arcgisdesktop/com/gp_toolref/spatial_analyst_tools/esri_ascii_raster_format.htm)
into Blender to create a new mesh object. This data format is commonly used to
encode LIDAR or other topology data and usually has the extension `.asc`. 

In the UK the [Environment Agency makes their LIDAR data available](https://environment.data.gov.uk/dataset/2e8d0733-4f43-48b4-9e51-631c25d1b0a9) in this format. The following render shows a 2M resolution digital terrain model of grid square SK1199 imported into Blender.

![example](./examples/SK1199_DTM_2M.png)

and of course once you have a mesh you can use it anyway you like, including using the 2D map image as a texture (in this case the 1:25,000 Ordnance Survey map)

![example](./examples/SK1199_25000.png)

## Features
- correctly supports files both with and without a `NODATA_value` declaration
- can read files which specify either `XLLCENTER` or `XLLCORNER`. The associated values are, however, currently ignored and the mesh is always positioned with the lower left corner at (0, 0, 0).
- allows the mesh to be scaled on import to avoid huge meshes being produced. The default is set to 0.01 so that a 1km square LIDAR image becomes a 10x10 sized mesh
- missing values are treated as being at sea level (i.e. the vertex is set to 0)
- two versions provided to support both Blender 2.8 and earlier versions

## Credits

Thanks go to [zeffii](https://github.com/zeffii) who wrote a [similar script](https://gist.github.com/zeffii/5dc7dd44899b7ae36dab73a2c235cd4f#file-modified_original_with_skipping_whitespace-py)
which I used as inspiration for this addon.
