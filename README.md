# ClusterDC

ClusterDC: a new clustering algorithm based on kernel-density contours tailored for large geological datasets.
![3D plot of the Kernel Density Estimation - 4](https://github.com/Maximilien42/clusterdc/assets/51908644/d84b7790-1175-4fce-be66-63b548b51c76)
![Contour plot of the Kernel Density Estimation - 4](https://github.com/Maximilien42/clusterdc/assets/51908644/49c236c1-9d18-4eba-a4c7-c09f9c76b435)
## License

This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0) license. You can find a copy of the license in the LICENSE file in the root directory of this project.

## User Manual

This user manual provides an overview of the input and output parameters of the `ClusterDC` function.

### Input Parameters

The `ClusterDC` function takes the following input parameters:

- `x_points` (array/list): The list of x-coordinates of the points.
- `y_points` (array/list): The list of y-coordinates of the points.
- `levels` (int): The number of contour levels to create.
- `num_points` (int): The number of points used for each side of the grid.
- `min_point` (int): The minimum number of points to include inside a valid polygon.
- `border_fraction` (float): The fraction to use as border size (< 1).
- `bw_method` (str/float): The method used for computing the bandwidth.
- `selection_method` (str/int): Method to select well-separated peaks. Can be 'first_gap', 'second_gap', 'third_gap', an int, or 'all'.
- `bw` (array/list): The bandwidth used at each point if the `bw_method` is 'local'.

### Output

The `ClusterDC` function returns the following outputs:

- `density_info` (list): A list containing all the information required to plot the kernel density estimation (KDE) function. It includes the density values, the KDE function, and the grid coordinates.
- `assignment` (array): An array of the assigned cluster labels for each point in `xy`.
- `list_assignment` (list): A list of arrays containing the assigned cluster labels for each point when the 'all' selection method is used.

### Example Notebook

To see an example of how to use the `ClusterDC` function, please refer to the provided Jupyter Notebook file `Example.ipynb`. The notebook demonstrates the usage of the function with sample data after a dimension reduction on an assay dataset and provides visualizations of the clustering results.

Please note that you need to have Jupyter Notebook installed to run the example notebook.

## Attribution

If you use this code in your work, please include the following attribution:

"This code is derived from https://github.com/Maximilien42/ClusterDC."

## Contact

If you have any questions or feedback, please feel free to contact maximilien.meyrieux@mail.mcgill.ca and samer.hmoud@mail.mcgill.ca.
