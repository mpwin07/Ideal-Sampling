Aim:

To perform ideal (impulse) sampling of a continuous-time sinusoidal signal, visualize the sampled signal, and reconstruct it using Python.

Tools/Software Required:

1. Python Software

-> Numpy Library

-> Matplotlib Library

-> Scipy Library (for signal processing)

Program :

#Impulse Sampling

import numpy as np

import matplotlib.pyplot as plt

from scipy.signal import resample

fs = 100

t = np.arange(0, 1, 1/fs) 

f = 5

signal = np.sin(2 * np.pi * f * t)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal')

plt.title('Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

t_sampled = np.arange(0, 1, 1/fs)

signal_sampled = np.sin(2 * np.pi * f * t_sampled)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')

plt.title('Sampling of Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

reconstructed_signal = resample(signal_sampled, len(t))

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')

plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()



Output Waveform : 

![Screenshot 2025-03-22 155318](https://github.com/user-attachments/assets/442e4910-09f2-4f8a-92cb-1967fe470e19) 

![Screenshot 2025-03-22 155345](https://github.com/user-attachments/assets/d8783a8d-906c-46d9-8bff-72e6dbd420c8) 

![Screenshot 2025-03-22 155437](https://github.com/user-attachments/assets/21ed6514-a25d-4479-9b5d-b3e433ba5d68)

Results :

The continuous sinusoidal signal was successfully sampled using ideal (impulse) sampling.

The sampling was performed at a rate (100 Hz) higher than twice the signal frequency (5 Hz), satisfying the Nyquist criterion.

The reconstruction of the signal using resampling accurately recovered the original waveform.

The experiment demonstrates the fundamental principle of ideal sampling and signal reconstruction.
