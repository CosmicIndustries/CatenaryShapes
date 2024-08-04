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
def plot_rotated_hexagon(ax, x_offset, y_offset, rotation_angle, a=1,num_points=10):#<10=tooLow
    x_range = np.linspace(-1.5, 1.5, num_points)
    y_catenary = catenary_2d(x_range, a)
    angles = np.linspace(0, 2 * np.pi, 7)
    for angle in angles[:-1]:
        x_shifted = (x_range * np.cos(angle + rotation_angle) - y_catenary * np.sin(angle + rotation_angle)) + x_offset
        y_shifted = (x_range * np.sin(angle + rotation_angle) + y_catenary * np.cos(angle + rotation_angle)) + y_offset
        ax.plot(x_shifted, y_shifted, 'b')

# Function to plot a grid of rotated hexagons
def plot_grid_of_rotated_hexagons(rotation_angle=0, spacing=np.pi, grid_size=2):
    fig, ax = plt.subplots(figsize=(8, 8))
    for i in range(-grid_size, grid_size+1):
        for j in range(-grid_size, grid_size+1):
            x_offset = i * spacing * 1 #horizontal Spacing
            y_offset = j * spacing * np.sin(np.pi / 3)  # Vertical spacing adjusted for hexagon tiling
            if j % 2 != 0:
                x_offset += spacing * 0.75  # Offset every other row for proper hexagonal tiling
            plot_rotated_hexagon(ax, x_offset, y_offset, rotation_angle)
    ax.set_title(f"Rotation Angle: {np.degrees(rotation_angle):.0f} degrees, Spacing: {spacing:.2f}")
    ax.set_aspect('equal')
    ax.axis('off')
    plt.show()


# Interactive plot
interact(
        plot_grid_of_rotated_hexagons,
         rotation_angle=FloatSlider(min=0, max=2*np.pi, step=0.1, value=0, description='Rotation Angle'),
         spacing=FloatSlider(min=0.5, max=5, step=0.1, value=np.pi, description='Spacing'),
         grid_size=IntSlider(min=1, max=5, step=1, value=2, description='Grid Size'));

![Catenary Shapes?](https://github.com/CosmicIndustries/CatenaryShapes/blob/main/image.png?raw=true)
<!-- The image is a diagram of a hexagonal structure with catenary arches. The structure is made up of multiple interconnected lines that form a star-like shape. The lines are blue in color and are arranged in a way that they form a symmetrical pattern. The background is white, and there is text at the top of the image that reads "Hexagonal Structure with Catenary Arches". -->
