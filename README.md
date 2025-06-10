# Jigsaw Puzzle Solver

A computer vision-based implementation of an automatic jigsaw puzzle solver.

**Alihan Esen**  
Istanbul Technical University  
📧 esenal22@itu.edu.tr

**Ulus Emir Aslan**  
Istanbul Technical University  
📧 aslanu21@itu.edu.tr

**Gaffar Dulkadir**  
Istanbul Technical University  
📧 dulkadir21@itu.edu.tr

## Overview

This Jupyter notebook implements a comprehensive jigsaw puzzle solver that can automatically reconstruct square jigsaw puzzles from individual piece images. The solver uses advanced computer vision techniques including LAB color space analysis, asymmetric dissimilarity measures, and greedy placement algorithms.

## Recommended Environment

**⭐ We strongly recommend running this notebook on Google Colab** for the best experience. The notebook includes Google Colab-specific features and the environment comes pre-configured with most required dependencies.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhnesn/YZV416E_Project/jigsaw_puzzle_solver.ipynb)

## Features

### Core Functionality
- **Piece Representation**: Efficient piece class with rotation support and boundary color caching
- **Image Splitting**: Automatic splitting of source images into square puzzle pieces
- **Rotation Handling**: Support for pieces with unknown orientations (0°, 90°, 180°, 270°)
- **Color Space Conversion**: LAB color space for improved color perception accuracy

### Algorithm Components
- **Dissimilarity Calculation**: An asymmetric dissimilarity formula
- **Compatibility Measures**: Edge compatibility analysis between adjacent pieces
- **Best Buddy Detection**: Mutual compatibility relationships
- **Greedy Placement**: Intelligent piece placement using compatibility scores

### Evaluation System
- **Ground Truth Comparison**: Accuracy metrics against original puzzle layout
- **Visual Assessment**: Direct image comparison with rotation handling
- **Performance Metrics**: Placement accuracy, neigbor accuracy, perfect reconstruction

## Technical Details

### Dependencies

For local installation, install the required packages:
```bash
pip install -r requirements.txt
```

Key dependencies:
- OpenCV (cv2) - Image processing and color space conversion
- NumPy - Numerical computations
- matplotlib - Visualization
- PIL/Pillow - Image handling
- scikit-image - Additional color space utilities
- tqdm - Progress bars
- IPython - Jupyter notebook support

### Key Classes and Functions

#### `Piece` Class
- Stores piece data with rotation and boundary color caching
- Supports LAB and BGR color spaces
- Precomputes average boundary colors for performance

#### Core Algorithms
- `calculate_dissimilarity_value()` - Implements Paikin's asymmetric dissimilarity
- `PuzzleSolver` class - Main greedy placement algorithm
- `precompute_solver_metrics()` - Efficiency optimization through precomputation

#### Evaluation Functions
- `evaluate_puzzle_solution()` - Comprehensive accuracy assessment
- `evaluate_puzzle_by_image_comparison()` - Visual comparison metrics

## Usage

### Basic Workflow
1. **Setup**: Mount Google Drive (optional) and import dependencies
2. **Image Preparation**: Load source image or create test puzzle
3. **Piece Generation**: Split image into square pieces with optional rotation
4. **Solver Execution**: Run the greedy placement algorithm
5. **Evaluation**: Assess solution quality and visualize results

### Input Formats
- Source images (any PIL-supported format)
- Pre-cut puzzle piece folders
- Custom piece size configuration

### Output
- Solved puzzle visualization

## Algorithm Background

This implementation uses:
- **LAB Color Space**: More perceptually uniform color representation
- **Asymmetric Dissimilarity**: Accounts for piece orientation and adjacency
- **Mutual Compatibility**: Bidirectional piece relationship analysis
- **Best Buddy Relationships**: High-confidence piece pairings

## Performance

The solver includes optimization features:
- Boundary color precomputation for faster dissimilarity calculation
- Compatibility metric caching
- Efficient data structures for large puzzle handling
- Progress tracking for long-running operations

## Limitations

- Designed for square puzzle pieces
- Performance scales with puzzle size and piece count
- Requires sufficient color variation for effective matching
 