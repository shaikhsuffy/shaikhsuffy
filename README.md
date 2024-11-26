import numpy as np
import matplotlib.pyplot as plt
from ipywidgets import interact, FloatSlider

# Function to generate the plot
def plot_sine_wave(frequency):
    x = np.linspace(0, 2 * np.pi, 500)
    y = np.sin(frequency * x)
    
    plt.figure(figsize=(8, 4))
    plt.plot(x, y, label=f"Sine wave (Frequency: {frequency} Hz)")
    plt.title("Interactive Sine Wave Plot")
    plt.xlabel("x")
    plt.ylabel("sin(frequency * x)")
    plt.legend()
    plt.grid()
    plt.show()

# Create an interactive slider
slider = FloatSlider(value=1, min=0.5, max=10, step=0.5, description="Frequency:")
interact(plot_sine_wave, frequency=slider)
# Code Example: Buttons for Plot Actions
import numpy as np
import matplotlib.pyplot as plt
from ipywidgets import Button, VBox, HBox

# Data
x = np.linspace(0, 2 * np.pi, 500)
y1 = np.sin(x)
y2 = np.cos(x)

# Plotting function
def plot_graph(y_data, title):
    plt.figure(figsize=(8, 4))
    plt.plot(x, y_data, label=title)
    plt.title(title)
    plt.xlabel("x")
    plt.ylabel("y")
    plt.legend()
    plt.grid()
    plt.show()

# Button click event handlers
def plot_sine_wave(button):
    plot_graph(y1, "Sine Wave")

def plot_cosine_wave(button):
    plot_graph(y2, "Cosine Wave")

# Create buttons
sine_button = Button(description="Sine Wave")
cosine_button = Button(description="Cosine Wave")

# Assign event handlers
sine_button.on_click(plot_sine_wave)
cosine_button.on_click(plot_cosine_wave)


