# 🖼️ Image Processing with Memory Allocation Comparison

A C++ project that demonstrates and compares the performance of different memory allocation strategies (Standard `new/delete` vs. Buddy System) for image processing operations including rotation and scaling.

## 🚀 Features

- **Image Processing Operations:**
  - Image rotation with arbitrary angles
  - Image scaling with custom factors
  - Color inversion
  - Support for multiple image formats (JPG, PNG, BMP, TGA)

- **Memory Management Comparison:**
  - Standard C++ `new/delete` allocation
  - Custom Buddy System allocator implementation
  - Performance benchmarking and memory usage analysis

- **Performance Analysis:**
  - Execution time comparison between allocation methods
  - Memory consumption tracking
  - Detailed performance metrics

## 📋 Prerequisites

- **C++17 compatible compiler** (GCC 7+, Clang 5+, MSVC 2017+)
- **Make** (for building on Unix-like systems)
- **CMake** (optional, for alternative build system)

## 🛠️ Installation & Build

### Option 1: Using Make (Recommended)

```bash
# Clone the repository
git clone https://github.com/Camiloesoto/ProcesamientodeImagenes.git
cd ProcesamientodeImagenes

# Build the project
make

# Clean build files
make clean
```

### Option 2: Manual Compilation

```bash
g++ -Wall -std=c++17 -o programa_buddy main.cpp imagen.cpp buddy_allocator.cpp stb_wrapper.cpp -lm
```

## 🎯 Usage

### Basic Usage

```bash
# Process image with standard new/delete allocation
./programa_buddy input.jpg output.png -angulo 45 -escalar 1.5 -no-buddy

# Process image with Buddy System allocation
./programa_buddy input.jpg output.png -angulo 45 -escalar 1.5 -buddy
```

### Command Line Arguments

- `input.jpg` - Input image file path
- `output.png` - Output image file path
- `-angulo <degrees>` - Rotation angle in degrees (optional)
- `-escalar <factor>` - Scaling factor (optional)
- `-buddy` - Use Buddy System allocator
- `-no-buddy` - Use standard new/delete allocation

### Examples

```bash
# Rotate image 90 degrees clockwise
./programa_buddy img.jpg rotated.jpg -angulo 90 -buddy

# Scale image to 2x size
./programa_buddy img.jpg scaled.jpg -escalar 2.0 -no-buddy

# Rotate and scale simultaneously
./programa_buddy img.jpg result.jpg -angulo 45 -escalar 1.5 -buddy
```

## 🏗️ Project Structure

```
├── main.cpp              # Main program entry point
├── imagen.h              # Image class header
├── imagen.cpp            # Image processing implementation
├── buddy_allocator.h     # Buddy System allocator header
├── buddy_allocator.cpp   # Buddy System allocator implementation
├── stb_wrapper.cpp       # STB image library wrapper
├── stb_image.h           # STB image loading library
├── stb_image_write.h     # STB image writing library
├── Makefile              # Build configuration
└── README.md             # This file
```

## 🔬 Technical Details

### Memory Allocation Strategies

#### Standard new/delete
- Uses C++ standard memory allocation
- Simple and straightforward implementation
- May suffer from memory fragmentation
- Good for small to medium allocations

#### Buddy System
- Power-of-2 block allocation strategy
- Reduces external fragmentation
- Faster allocation/deallocation for repeated operations
- Better memory locality
- Optimal for image processing workloads

### Image Processing Algorithms

#### Rotation
- Implements rotation around image center
- Uses bilinear interpolation for smooth results
- Handles arbitrary rotation angles
- Maintains image quality

#### Scaling
- Nearest-neighbor interpolation for fast scaling
- Supports both upscaling and downscaling
- Maintains aspect ratio
- Efficient memory usage

## 📊 Performance Analysis

The project automatically measures and compares:

- **Execution Time:** Processing time for each operation
- **Memory Usage:** Peak memory consumption during processing
- **Efficiency:** Memory allocation/deallocation overhead

### Expected Results

- **Buddy System** typically shows better performance for:
  - Large image processing
  - Multiple consecutive operations
  - Memory-intensive workloads

- **Standard new/delete** may perform better for:
  - Single, small operations
  - Simple memory patterns
  - Development and testing scenarios

## 🧪 Testing

### Sample Images
The project includes sample images for testing:
- `img.jpg` - Test image for basic operations
- `xxx.jpg` - Additional test image

### Performance Testing
```bash
# Test with Buddy System
make run_buddy

# Test with standard allocation
make run_nobuddy
```

## 🔧 Customization

### Adding New Image Operations
1. Declare the method in `imagen.h`
2. Implement in `imagen.cpp`
3. Add command line argument handling in `main.cpp`

### Modifying Memory Allocator
1. Extend `buddy_allocator.h` with new methods
2. Implement in `buddy_allocator.cpp`
3. Update memory management in `imagen.cpp`

## 📈 Future Enhancements

- [ ] **OpenMP Integration** for parallel processing
- [ ] **GPU Acceleration** using CUDA/OpenCL
- [ ] **Advanced Filters** (blur, sharpen, edge detection)
- [ ] **Batch Processing** for multiple images
- [ ] **Memory Pooling** for better performance
- [ ] **Web Interface** for easy testing

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Camilo Soto**
- GitHub: [@Camiloesoto](https://github.com/Camiloesoto)
- Project: [ProcesamientodeImagenes](https://github.com/Camiloesoto/ProcesamientodeImagenes)

## 🙏 Acknowledgments

- **STB Libraries** for image I/O operations
- **OpenMP** community for parallel processing standards
- **Operating Systems** course for project inspiration

## 📚 Related Resources

- [STB Image Libraries](https://github.com/nothings/stb)
- [OpenMP Documentation](https://www.openmp.org/)
- [Memory Allocation Strategies](https://en.wikipedia.org/wiki/Buddy_memory_allocation)
- [Image Processing Algorithms](https://en.wikipedia.org/wiki/Digital_image_processing)

---

⭐ **Star this repository if you find it helpful!**

