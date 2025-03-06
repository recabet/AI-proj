# Indicators List

_A lot of these variables are extracted thanks to: _[_scikit-image regionprops_](https://scikit-image.org/docs/0.24.x/auto_examples/segmentation/plot_regionprops.html)

## Variables and Calculation

### Number

- Index of the school among all the images

### Label

- Index of the school among one image (1 if only 1 school in the image)

### File Name

- Name of the resized matrix used for the school extraction

### Size

- Number of pixels of the school

### Bbox

- Box around the school

### Center

- Centroid

### Depth

- Depth of the average coordinate of the school in meters

### Sea Depth

- Sea floor depth in meters

### School-Seabed Distance

- `Depth - Sea_Depth` (in meters)

### GPS Longitude and Latitude

- Longitude and latitude (WGS84)

### Time

- Time UTC

### Width Bbox

- Width of the bounding box

### Length Bbox

- Length of the bounding box

### Is Very Wide

- `(bbox[3]-bbox[1]) > width_image/2`

### Is Very Tall

- `(bbox[2]-bbox[0]) > height_image/2`

### Distance to Surface

- `Bbox[0]` in pixels

### Distance Level

- `0, 1, or 2`
  - `0` if `Dis_to_surface < 10` pixels
  - `1` if between `10 and 50`
  - `2` if `> 50`

### Axis Major Length

- _AREA_

### Axis Minor Length

- _AREA_

### Perimeter School

- Perimeter

### Intensity School

- Mean intensity of the school

### Intensity Image

- Mean intensity of the image

### Difference in Intensity (School vs Image)

- `Intensity_school - Intensity_img`

### Center Square Intensity

- Center square: A square of nine pixels with the central pixel as the centroid of the school
- Mean intensity among this square

### Edges School Intensity

- Edges: List of tuples containing coordinates of the four connected neighbors
- Mean intensity among these coordinates

### Difference in Intensity (Center vs Edges)

- `Center_square_intensity - Edges_school_intensity`

### Standard Deviation of Intensity (School)

- Intensity standard deviation of the school

### Gradient School

```python
gradient_y, gradient_x = np.gradient(coords)  # coords of the school
gradient_magnitude = np.sqrt(gradient_x**2 + gradient_y**2)
gradient_school = np.mean(gradient_magnitude)
```

### Gradient School Center

- Same as `Gradient School`, but for the coordinates of the central square

### Gradient School Edges

- Same as `Gradient School`, but for the coordinates of the edges

### Difference in Gradient (Center vs Edges)

- `Gradient_school_center - Gradient_school_edges`

### Width-Length Ratio

- `(region.bbox[3] - region.bbox[1]) / (region.bbox[2] - region.bbox[0])`

### Axis Ellipse Ratio

- `region.axis_minor_length / region.axis_major_length`

### Solidity

- Ratio of pixels in the region to pixels of the convex hull image

### Compactness

- `4 * math.pi * (region.area) / (region.perimeter**2)`

### Inertia Tensor Eigenvalues Ratio

- `region.inertia_tensor_eigvals[1] / region.inertia_tensor_eigvals[0]`

### Perimeter-Area Ratio

- `region.perimeter / region.area`

### Threshold Min

- `Thresh_min` from double thresholding

### Threshold Max

- `Thresh_max` from double thresholding

### Distance to Bottom

- Same as `School-Seabed Distance` (original calculation contained an error; this replaces it)
