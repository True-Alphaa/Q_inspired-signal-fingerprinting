
# Q_inspired-signal-fingerprinting

## NOTE
The result image uploaded for Quantum inspired algorithm counted the time taken for QFT to rub excluding the time needed to convert data from array to MPS and back. That needs to be optimised. 

> **Napkin Pitch** (ISIT 2025 Quantum Hackathon)  
>
> - **The Problem:** Seeking a transform even faster than FFT for fingerprinting  
> - **Your Solution:** We will simulate QFT classically to gain a speed advantage over FFT, thereby accelerating the entire algorithm  
> - **Hack Ingredients:** Tensor Networks • Julia • PennyLane  
> - **Unique Value Proposition:** QFT has low entanglement, making it tractable to simulate efficiently. This approach not only speeds up chirp-spectrogram STFTs but can accelerate a wide class of FFT-based algorithms.  

An explorative project comparing **classical FFT–based** and **quantum-inspired QFT–MPO** implementations of the Short-Time Fourier Transform (STFT) for chirp signal spectrograms.


---

## 🔍 Overview

- **Classical FFT Version**  
  - Uses `FFTW.jl`, `Plots.jl`, and `LinearAlgebra`.  
  - Computes an FFT-based STFT on a linear chirp signal (50→250 Hz over 2 s at 1 kHz).  
  - Benchmarks spectrogram computation time and renders a heatmap.

- **Quantum-Inspired QFT-MPO Version**  
  - Uses `ITensors.jl`, `ITensorMPS.jl`, `HDF5.jl`, `LinearAlgebra`, and `Plots.jl`.  
  - Loads an 8-qubit QFT MPO and a library of basis MPS from HDF5.  
  - Encodes each STFT frame as an MPS, applies the QFT MPO, computes inner products, and benchmarks performance.  
  - Produces a QFT-based spectrogram for direct comparison.

---

## ⚙️ Prerequisites

- Julia ≥ 1.7  
- Required packages:
  ```julia
  using Pkg
  Pkg.add(["FFTW", "Plots", "LinearAlgebra", "ITensors", "ITensorMPS", "HDF5"])

---


