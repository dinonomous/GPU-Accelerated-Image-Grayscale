# GPU-Accelerated Image Grayscale Conversion

This repository demonstrates color-to-grayscale image conversion using four methods:

* **Pure Python loops**
* **NumPy vectorization**
* **OpenCV’s built-in function**
* **CUDA via Numba JIT**

The goal is to compare performance across these approaches and highlight the benefits of GPU acceleration for per-pixel image processing.

---

## 📋 Requirements

* Python 3.7+
* NumPy
* OpenCV (cv2)
* Numba (with CUDA support)
* NVIDIA GPU with CUDA toolkit installed

Install dependencies via:

```bash
pip install numpy opencv-python numba
```

Ensure you have the CUDA toolkit and drivers installed for your GPU.

---

## ⚙️ File Overview

* `cuda_grayscale_colab.py`
  Implementation of four grayscale conversion functions and benchmarking script.

---

## 🚀 Usage

1. Clone this repository:

```bash
git clone https://github.com/dinonomous/GPU-Accelerated-Image-Grayscale.git
cd gpu-grayscale-conversion
```


2. Run the script on a sample image:
```bash
python cuda_grayscale_colab.py --input image.jpg
```

3. Observe printed benchmark results for different image sizes.

You can adjust image paths or add your own tests.

---

## 📈 Benchmark Results (Example)

```
Benchmarking 512×512 image:
  Python Loops:  950.2 ms   (1.00×)
  NumPy:          12.5 ms   (76.0×)
  OpenCV:          4.3 ms  (220.5×)
  CUDA:            2.1 ms  (452.5×)

Benchmarking 2048×2048 image:
  NumPy:         210.3 ms   (1.00×)
  OpenCV:         35.7 ms   (5.89×)
  CUDA:            8.4 ms   (25.0×)
```

Runtime numbers will vary based on hardware. The CUDA approach consistently offers the greatest speedup on large images.

---

## 🔧 How It Works

1. **Python loops**: iterates pixel-by-pixel in pure Python—simple but slow.
2. **NumPy**: uses vectorized operations over arrays—significantly faster.
3. **OpenCV**: leverages highly-optimized C++ routines.
4. **CUDA via Numba**: compiles a GPU kernel mapping each pixel to a CUDA thread for maximum parallelism.

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## ✨ Contributing

Contributions, issues, and feature requests are welcome! Please open an issue or submit a pull request.
