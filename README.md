  ![GitHub Logo](https://github.githubassets.com/assets/mona-loading-default-c3c7aad1282f.gif)
# Catenary
![Catenary ShapesPi](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/file-10ObPhzAXl1KZfUE3s5sMrzd.png?raw=true)

  > Just an assortment of shape and lattic generators made from Catenary Curves.
![Catenary ShapesPi](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/pi.png?raw=true)
![Catenary Shapes3](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/3Tests.png?raw=true)

Sample code:
>
import numpy as np
import matplotlib.pyplot as plt
from ipywidgets import interact, FloatSlider, IntSlider

# Define the catenary function in 2D

def catenary_2d(x, a):
    return a * np.cosh(x / a)

# Function to plot a rotated hexagon with catenary curves
…
# Interactive plot

interact(
    plot_grid_of_rotated_hexagons,
    rotation_angle=FloatSlider(min=0, max=2*np.pi, step=0.1, value=0, description='Rotation Angle'),
    spacing=FloatSlider(min=0.5, max=5, step=0.1, value=np.pi, description='Spacing'),
    grid_size=IntSlider(min=1, max=5, step=1, value=2, description='Grid Size')
);

![Catenary Shapes?](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/image.png?raw=true)
<!-- The image is a diagram of a hexagonal structure with catenary arches. The structure is made up of multiple interconnected lines that form a star-like shape. The lines are blue in color and are arranged in a way that they form a symmetrical pattern. The background is white, and there is text at the top of the image that reads "Hexagonal Structure with Catenary Arches". -->

![Catenary Shapes?](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/image3d.png?raw=true)
