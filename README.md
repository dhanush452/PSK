#  PSK

#  Aim

To simulate and analyze the waveform of Binary Phase Shift Keying (BPSK) modulation using Python.

#  Tools Required

Python 3.x

Libraries:

numpy

matplotlib (for plotting waveforms)

#  Python Program

import numpy as np

import matplotlib.pyplot as plt

bit_rate = 1

T = 1 / bit_rate

fc = 2

sample_rate = 1000

data = [1, 0, 1, 1, 0, 0, 1, 0]

n = len(data)

total_samples = int(n * T * sample_rate)

t = np.linspace(0, n * T, total_samples, endpoint=False)

bpsk_signal = np.array([])

for bit in data:

phase = 0 if bit == 1 else np.pi
t_bit = np.linspace(0, T, int(T * sample_rate), endpoint=False)
wave = np.cos(2 * np.pi * fc * t_bit + phase)
bpsk_signal = np.concatenate((bpsk_signal, wave))
plt.figure(figsize=(10, 4))

plt.title("PSK Modulated Signal")

plt.plot(t, bpsk_signal, label='PSK')

plt.xlabel("Time (s)")

plt.ylabel("Amplitude")

plt.grid(True)

plt.tight_layout()

plt.show()

#  Output

![PSK OUTPUT 3](https://github.com/user-attachments/assets/90331170-b6f4-44ac-a885-f4ef86595bc5)

#  Results

Successfully simulated BPSK modulation

Phase inversion observed for binary 0

Output waveform matches theoretical expectations for BPSK

Useful for digital communication systems like wireless or satellite links
