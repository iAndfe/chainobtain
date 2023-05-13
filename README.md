# Chainage and Offset Calculator

This program is a utility for calculating the chainage (distance along a polyline) and offset (distance perpendicular to the polyline) of a set of points relative to a polyline. The polyline can be read from a CSV file, a shapefile, or a CAD file (.dxf or .dwg).

## Installation

To run this program, you need to install the following Python libraries:

- pandas
- rtree
- shapely
- geopandas
- ezdxf

You can install these libraries using pip:

```bash
pip install pandas rtree shapely geopandas ezdxf
```

## Usage

The `chain_obtain(polyline, input_file)` function is used to calculate the chainage and offset values for a set of points relative to a polyline. The function takes two arguments:

- `polyline` is the polyline object relative to which the chainage and offset values are to be calculated. The polyline can be created using one of the following functions:

  - `csv_to_polyline(file_path)`: Reads a polyline from a CSV file.
  - `read_shapefile(file_path)`: Reads a polyline from a shapefile.
  - `read_cad_file(file_path)`: Reads a polyline from a CAD file (.dxf or .dwg).

- `input_file` is the path to a CSV file containing the points for which the chainage and offset values are to be calculated.

The function returns a pandas DataFrame with the same structure as the input points CSV file, but with two additional columns:

- `chainage`: The distance along the polyline to the point.
- `offset`: The perpendicular distance from the polyline to the point.

Example usage:

```python
# Define the polyline as a list of Point objects
polyline = csv_to_polyline('test_poly.csv')

# Calculate chainage and offset for a set of points
points_df = chain_obtain(polyline, 'test_points.csv')

# Print the DataFrame
print(points_df)
```
