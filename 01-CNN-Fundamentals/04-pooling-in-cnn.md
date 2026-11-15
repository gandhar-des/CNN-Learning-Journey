# Pooling in CNN

## 1. What is pooling?

**Pooling** is a downsampling operation used to reduce the height and width of feature maps. It summarizes values within small local regions.

Pooling can reduce the amount of spatial data passed to later layers and can make the representation less sensitive to small shifts.

## 2. Types of pooling

### Max pooling

Selects the **maximum** value from each pooling window.

It keeps the strongest activation in each region and is widely used in many traditional CNN architectures.

### Average pooling

Calculates the **average** of all values in each pooling window.

It summarizes the overall activation in the region.

### Min pooling

Selects the **minimum** value from each pooling window.

It is less commonly used than max pooling and average pooling in typical CNN architectures.

## 3. Worked example

Consider this 4 × 4 feature map:

```text
1  3  2  4
5  6  1  2
7  2  8  3
1  4  2  9
```

Use a 2 × 2 pooling window with stride 2. The four windows are non-overlapping.

**Max pooling**

- Top-left: max(1, 3, 5, 6) = 6
- Top-right: max(2, 4, 1, 2) = 4
- Bottom-left: max(7, 2, 1, 4) = 7
- Bottom-right: max(8, 3, 2, 9) = 9

Result:

```text
6  4
7  9
```

**Average pooling**

Result:

```text
3.75  2.25
3.50  5.50
```

**Min pooling**

Result:

```text
1  1
1  2
```

## 4. Pooling output-size formula

For one spatial dimension, with no padding:

\[
O=\left\lfloor\frac{N-F}{S}\right\rfloor+1
\]

Where:
- \(N\) = input size
- \(F\) = pooling window size
- \(S\) = stride
- \(O\) = output size

For a 4 × 4 input, 2 × 2 window, and stride 2:

\[
O=\frac{4-2}{2}+1=2
\]

Output size = **2 × 2**.

## 5. Important points

- Pooling usually reduces spatial dimensions (height and width).
- It can reduce computation in subsequent layers.
- Standard max and average pooling operations have no trainable weights.
- Pooling is not the same as convolution: convolution learns filter weights, while standard pooling applies a fixed summary operation.
- Some modern CNN architectures reduce resolution using strided convolutions or other methods instead of pooling.

## Quick revision

- Pooling downsamples feature maps.
- Max pooling selects the largest value in each window.
- Average pooling calculates the mean.
- Min pooling selects the smallest value.
- A 2 × 2 window with stride 2 halves height and width when dimensions divide evenly.

## Practice questions

1. What is pooling and why is it used?
2. Explain max pooling with an example.
3. What is the difference between max pooling and average pooling?
4. Does standard max pooling have trainable weights?
5. Calculate the output size for N = 8, F = 2, S = 2, with no padding.
