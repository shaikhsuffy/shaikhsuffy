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
