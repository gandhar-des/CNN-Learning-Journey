# Stride in CNN

## 1. What is stride?

**Stride** is the number of pixels by which a convolution filter moves at each step across the input.

- Stride 1: the filter moves one pixel at a time.
- Stride 2: the filter moves two pixels at a time.

The filter moves across the image horizontally and vertically.

## 2. Effect of stride

A larger stride generally:
- Produces a smaller output feature map.
- Reduces the number of filter positions and computation.
- Downsamples the spatial information.
- May skip fine details when the stride is too large.

A smaller stride evaluates more overlapping regions and produces a larger feature map.

## 3. Output-size formula

For one spatial dimension, assuming dilation = 1:

\[
O = \left\lfloor\frac{N-F+2P}{S}\right\rfloor+1
\]

Where:
- \(N\) = input size
- \(F\) = filter size
- \(P\) = padding on each side
- \(S\) = stride
- \(O\) = output size

## 4. Example

Input: 7 × 7  
Filter: 3 × 3  
Padding: 0

**Stride = 1**

\[
O=\left\lfloor\frac{7-3}{1}\right\rfloor+1=5
\]

Output = **5 × 5**.

**Stride = 2**

\[
O=\left\lfloor\frac{7-3}{2}\right\rfloor+1=3
\]

Output = **3 × 3**.

## 5. Stride and padding work together

Output size depends on input size, filter size, padding, and stride. Changing more than one of these changes the output dimensions.

## Quick revision

- Stride controls how far the filter moves at each step.
- Stride 1 moves one pixel; stride 2 moves two pixels.
- Increasing stride generally reduces feature-map size and computation.
- A very large stride can lose useful spatial details.

## Practice questions

1. Define stride in convolution.
2. What happens to output size when stride increases?
3. For N = 5, F = 3, P = 0, calculate output size for stride 1 and stride 2.
4. Why might a very large stride be undesirable?
