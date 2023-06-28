# ClusterDC

ClusterDC: a new clustering algorithm based on kernel-density contours tailored for large geological datasets.

![3D plot of the Kernel Density Estimation - 4](https://github.com/Maximilien42/ClusterDC/blob/main/Images/3D%20plot%20of%20the%20Kernel%20Density%20Estimation%20-%204.svg)

![Contour plot of the Kernel Density Estimation - 4](https://github.com/Maximilien42/ClusterDC/blob/main/Images/Contour%20plot%20of%20the%20Kernel%20Density%20Estimation%20-%204.svg)

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
- `bw_method` (str/float): The method used for computing the bandwidth. It can be 'scott' or 'silverman' for global bandwidth, or 'local' if an array of local adaptive bandwidths around every data point is provided in 'bw'.
- `selection_method` (str/int): Method to select well-separated peaks. Can be 'first_gap', 'second_gap', 'third_gap', an int, or 'all'.
- `bw` (array/list): The bandwidth used at each point if the `bw_method` is 'local'.

### Output

The `ClusterDC` function returns the following outputs:

- `density_info` (list): A list containing all the information required to plot the Kernel Density Estimation (KDE) function. It includes the density values, the KDE function, and the grid coordinates.
- `assignment` (array): An array of the assigned cluster labels for each point.
- `list_assignment` (list): A list of arrays containing the assigned cluster labels for each point when the 'all' selection method is used.

### Example Notebook

To see an example of how to use the `ClusterDC` function, please refer to the provided Jupyter Notebook file `Example.ipynb`. The notebook demonstrates the usage of the function with sample data after a PaCMAP dimension reduction on an assay dataset and provides visualizations of the clustering results.

Please note that you need to have Jupyter Notebook installed to run the example notebook.

### Upcoming Improvements
The authors of this code have plans to further improve its functionality and usability. One of the upcoming milestones is the development of a dedicated library for utilizing ClusterDC, which will be easily installable via pip. Keep an eye out for updates as the repository progresses toward this goal!

## Contact

If you have any questions or feedback, please feel free to contact maximilien.meyrieux@mail.mcgill.ca and samer.hmoud@mail.mcgill.ca.

## Attribution

If you use this code in your work, please include the following attribution:

"This code is derived from https://github.com/Maximilien42/ClusterDC."

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We would like to acknowledge the PaCMAP team for providing the PaCMAP dimension reduction algorithm, which was instrumental in reducing the dimensionality of the data prior to applying ClusterDC. The PaCMAP algorithm, developed by Yingfan Wang, Haiyang Huang, Cynthia Rudin, and Yaron Shaposhnik, is a valuable tool for visualizing high-dimensional data. 

For more information, refer to the PaCMAP GitHub repository at https://github.com/YingfanWang/PaCMAP.

We are also grateful to the ClusterDV team for the development of the ClusterDV MATLAB code and the synthetic datasets provided with it. ClusterDV, developed by João C. Marques and Michael B. Orger, provided foundational concepts for ClusterDC. ClusterDC was developed as an extension of ClusterDV to overcome its limitations in processing large datasets, allowing for more efficient handling of geological datasets with thousands to hundreds of thousands of samples.

For more details on ClusterDV, see the ClusterDV GitHub repository at https://github.com/jcbmarques/clusterdv.

Please refer to the following references for more information:
- [Wang, Y., Huang, H., Rudin, C., & Shaposhnik, Y. (2021). Understanding How Dimension Reduction Tools Work: An Empirical Approach to Deciphering t-SNE, UMAP, TriMap, and PaCMAP for Data Visualization. Journal of Machine Learning Research, 22(201), 1-73.](http://jmlr.org/papers/v22/20-1061.html)
- [Marques, J. C., & Orger, M. B. (2019). Clusterdv: a simple density-based clustering method that is robust, general and automatic. Bioinformatics, 35(12), 2125-2132.](https://doi.org/10.1093/bioinformatics/bty907)
