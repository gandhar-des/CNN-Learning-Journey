# Padding in CNN

## 1. What is padding?

**Padding** means adding extra pixels around the border of an input image or feature map before applying a convolution filter. These added values are commonly zeros, which is called zero padding.

## 2. Why is padding used?

- **Preserve spatial dimensions:** without padding, convolution usually makes the feature map smaller.
- **Process border pixels:** padding lets filters cover pixels near the edges more fully.
- **Control output size:** padding is one way to choose the dimensions of the output feature map.

## 3. Types of padding

### Valid padding

- No extra pixels are added.
- The filter must fit entirely inside the input.
- The output is generally smaller than the input when the filter is larger than 1 × 1.

### Same padding

- Padding is selected to keep the output dimensions the same as the input when stride is 1.
- With stride greater than 1, output dimensions are generally the ceiling of input dimension divided by stride; they are not necessarily the same as the input.

## 4. Output-size formula

For one spatial dimension, assuming dilation = 1:

\[
O = \left\lfloor\frac{N-F+2P}{S}\right\rfloor+1
\]

Where:
- \(O\) = output size
- \(N\) = input size
- \(F\) = filter (kernel) size
- \(P\) = padding on each side
- \(S\) = stride
- \(\lfloor \cdot \rfloor\) = round down

For height and width, apply the formula separately.

## 5. Example

Input: 5 × 5  
Filter: 3 × 3  
Stride: 1

**Valid padding:** \(P=0\)

\[
O=\frac{5-3+0}{1}+1=3
\]

Output size = **3 × 3**.

**One-pixel zero padding:** \(P=1\)

\[
O=\frac{5-3+2}{1}+1=5
\]

Output size = **5 × 5**.

## 6. Python example with NumPy

```python
import numpy as np

image = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

padded_image = np.pad(
    image,
    pad_width=1,
    mode="constant",
    constant_values=0
)

print(padded_image)
```

## Quick revision

- Padding adds pixels around the input border.
- Zero padding is a common choice.
- Valid means no padding.
- Same commonly preserves dimensions when stride is 1.
- Padding helps filters process border regions and controls output size.

## Practice questions

1. What is padding in CNN?
2. What is the difference between valid and same padding?
3. Find the output size for N = 7, F = 3, P = 0, S = 1.
4. What padding value preserves a 5 × 5 input with a 3 × 3 filter and stride 1?
