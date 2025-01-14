# TODO

## Bugs
- [x] very high overlap ratios throw an error
- [x] bias error in non-translating window

## Documentation
- [x] complete the Jupyter notebook tutorials
   - [x] basic
   - [x] advanced
- [ ] update the readme to reflect improved functionality

## Optimizations
- [ ] memory optimizations
  - [x] reuse same arrays as previous iterations
  - [x] write an outside class to store the common GPU data
  - [x] reconcile the definition of new arrays with how it was originally coded
  - [x] predefine arrays for u, v, x, y, mask
  - [x] don't calculate x, y for every iteration
  - [ ] use shared memory for GPU kernels
  - [ ] confirm if to_gpu() is faster than gpuarray.zeros()

- [ ] correlation class
  - [x] reduce operations outside of CUDA kernels in iw_arrange()
  - [x] move methods out of init()
  - [ ] define fewer GPU arrays
  - [ ] Use CUDA kernel in subpixel location
  - [ ] Return a GPU array for the validation list

- [x] define empty arrays on the GPU directly instead of sending Numpy arrays to the GPU by gpuarray.to_gpu
- [ ] reduce the number of temporary gpu arrays created
- [x] make consistent the strain and shift array arguments in the correlation function

## Features
- [ ] dismantle the F-structure so that others can more easily contribute
- [x] re-enable other validation methods
  - [x] mean validation
  - [x] s2n
  - [x] rms
- [ ] Add ROI feature
- [x] Implement the extended search area in the second frame
- [ ] Make the validation functions usable by other algorithms, maybe by wrapping them in a function the does I/O with the GPU
- [ ] Use CuPy or scikit-cuda to implement the cosine transform used in Smoothn
- [ ] validate next to masked points

- [ ] fix edge treatment to have fewer errors
  - [ ] validation of edges
  - [ ] validation of points next to mask
  - [ ] interpolation onto edges
  
- [x] replace vectors with median rather than median of surrounding points to not be affected by outliers

## Object-oriented features
- [x] return the mask
- [x] return s2n
- [x] return x, y
