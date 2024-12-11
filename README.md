# Python_Day17

#Data Visualization with Matplotlib
#Example Code for Basic Plotting
import matplotlib.pyplot as plt

# Sample data
x = [0, 1, 2, 3, 4, 5]
y = [0, 1, 4, 9, 16, 25]

# Plotting the data
plt.plot(x, y, label='y = x^2')

# Customizing the plot
plt.title('Simple Line Graph')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.legend()

# Display the plot
plt.show()


#Example Code for Visualizing a Sine Wave
import numpy as np
import matplotlib.pyplot as plt

# Generate sample data for a sine wave
x = np.linspace(0, 2 * np.pi, 1000)
y = np.sin(x)

# Plotting the sine wave
plt.plot(x, y, label='Sine Wave')

# Customizing the plot
plt.title('Sine Waveform')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()

# Display the plot
plt.show()


#Example Code for Real-Time Signal Plotter
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

# Set up the figure and axis
fig, ax = plt.subplots()
xdata, ydata = [], []
ln, = plt.plot([], [], 'r-', animated=True)

# Initialize plot limits and labels
def init():
    ax.set_xlim(0, 2 * np.pi)
    ax.set_ylim(-1, 1)
    return ln,

# Update the data for the plot
def update(frame):
    xdata.append(frame)
    ydata.append(np.sin(frame))
    ln.set_data(xdata, ydata)
    return ln,

# Create the animation
ani = FuncAnimation(fig, update, frames=np.linspace(0, 2 * np.pi, 128), init_func=init, blit=True)

# Display the plot
plt.title('Real-Time Sine Wave Plotter')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.show()
