## EXPLAIN FORLULA 3-39 AND 3-40
### Example: Three 3×3 Kernels

Let’s assume we have three kernels \(w_1\), \(w_2\), and \(w_3\), all of size \(3 \times 3\). These kernels are used for convolution sequentially on an image or another matrix.

1.  **First kernel (\(w_1\)):**

\[
w_1 = \begin{bmatrix} 
1 & 0 & 1 \\ 
0 & 1 & 0 \\ 
1 & 0 & 1 
\end{bmatrix}
\]

2.  **Second kernel (\(w_2\)):**

\[
w_2 = \begin{bmatrix} 
0 & 1 & 0 \\ 
1 & 1 & 1 \\ 
0 & 1 & 0 
\end{bmatrix}
\]

3.  **Third kernel (\(w_3\)):**

\[
w_3 = \begin{bmatrix} 
1 & 1 & 1 \\ 
1 & 1 & 1 \\ 
1 & 1 & 1 
\end{bmatrix}
\]

### Step-by-Step Process of Convolution and Growth in Kernel Size

#### First Convolution with \(w_1\):

Convolve an image \(f\) with kernel \(w_1\).

-   The kernel size is \(3 \times 3\).
-   After convolving \(f\) with \(w_1\), the result will have grown by 2 pixels in both the vertical and horizontal dimensions (due to the \(m-1\) padding in both directions).

So, if the original image \(f\) was of size \(M \times N\), the new output will have size:

\[
(M + 3 - 1) \times (N + 3 - 1) = (M + 2) \times (N + 2)
\]

#### Second Convolution with \(w_2\):

Next, take the result from the first convolution and convolve it with \(w_2\).

-   Again, the kernel size is \(3 \times 3\).
-   The result will grow by an additional 2 pixels in both directions (i.e., \(3 - 1 = 2\)).

So, after this second convolution, the new output will have size:

\[
(M + 4) \times (N + 4)
\]

#### Third Convolution with \(w_3\):

Finally, convolve the result from the second convolution with \(w_3\).

-   The kernel size is still \(3 \times 3\).
-   The result will grow by another 2 pixels in both directions.

So, after this third convolution, the new output will have size:

\[
(M + 6) \times (N + 6)
\]

### General Formula for the Final Kernel Size:

From this specific example, we can derive the general formula for the final kernel size when you apply multiple convolutions.

If you convolve \(Q\) kernels of size \(m \times n\), the size of the final result will be:

\[
W_v = Q \times (m - 1) + m
\]
\[
W_h = Q \times (n - 1) + n
\]

In this case, \(Q = 3\), and each kernel is \(3 \times 3\), so:

\[
W_v = 3 \times (3 - 1) + 3 = 3 \times 2 + 3 = 9
\]
\[
W_h = 3 \times (3 - 1) + 3 = 9
\]

So, the **effective kernel size** after applying all three convolutions will be \(9 \times 9\).

### Visualization of Kernel Growth:

-   **Initial kernel \(w_1\):** \(3 \times 3\)
-   **After first convolution:** Resulting size grows by 2 pixels in both directions: \((M + 2) \times (N + 2)\)
-   **After second convolution:** Resulting size grows by 2 more pixels in both directions: \((M + 4) \times (N + 4)\)
-   **After third convolution:** Resulting size grows by 2 more pixels: \((M + 6) \times (N + 6)\)

### Key Takeaway:

-   **Convolution "grows" the size** of the image because each convolution adds padding around the image or previous result.
-   This is why, after multiple stages of convolution, the final "effective" kernel size becomes \(W_v = Q \times (m - 1) + m\) and \(W_h = Q \times (n - 1) + n\), where \(Q\) is the number of convolution stages, and \(m\) and \(n\) are the dimensions of the kernels used.

In this example, after three convolutions with \(3 \times 3\) kernels, the final effective kernel is \(9 \times 9\).

___
### Example:
Let’s consider a small rank-1 kernel matrix **K** and work through the steps.

#### Kernel Matrix:
\[
K = \begin{bmatrix}
2 & 4 & 6 \\
4 & 8 & 12 \\
6 & 12 & 18
\end{bmatrix}
\]

#### Step 1: Find a non-zero element **E**:
Let’s pick \( E = 2 \), which is the element at position \( (1,1) \).

#### Step 2: Form vectors **c** and **r**:
The column **c** corresponding to **E** is:
\[
c = \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix}
\]

The row **r** corresponding to **E** is:
\[
r = \begin{bmatrix} 2 & 4 & 6 \end{bmatrix}
\]

#### Step 3: Find vectors **v** and **w^T**:
\[
v = c = \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix}
\]
\[
w^T = \frac{r}{E} = \frac{1}{2} \times \begin{bmatrix} 2 & 4 & 6 \end{bmatrix} = \begin{bmatrix} 1 & 2 & 3 \end{bmatrix}
\]

#### Step 4: Reconstruct the kernel from the outer product of **v** and **w^T**:
\[
K = v \times w^T = \begin{bmatrix} 2 \\ 4 \\ 6 \end{bmatrix} \times \begin{bmatrix} 1 & 2 & 3 \end{bmatrix}
\]
\[
K = \begin{bmatrix}
2 \times 1 & 2 \times 2 & 2 \times 3 \\
4 \times 1 & 4 \times 2 & 4 \times 3 \\
6 \times 1 & 6 \times 2 & 6 \times 3
\end{bmatrix}
= \begin{bmatrix}
2 & 4 & 6 \\
4 & 8 & 12 \\
6 & 12 & 18
\end{bmatrix}
\]

Thus, we successfully decomposed the kernel into vectors **v** and **w^T**, whose outer product gives the original kernel matrix.

### Separable Kernels in Convolution:
This decomposition is especially useful in convolution operations:

- Instead of performing a full 2D convolution using the entire kernel matrix, we can first convolve the image with the column vector **v**, and then with the row vector **w^T**.
- This reduces the complexity of the convolution operation and speeds up processing, especially with large kernels or images.
___

**Circular symmetry** refers to a property of a matrix, kernel, or any function where its values are symmetric about its center in all directions. In simpler terms, if you rotate the matrix or kernel around its center, the values remain unchanged. This type of symmetry is often encountered in image processing and filtering, where the structure or pattern of the kernel looks the same regardless of how you rotate it around the central element.

### Example of Circularly Symmetric Kernel:

Consider the following 3×3 kernel:

K=[121242121]K = \begin{bmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \\ 1 & 2 & 1 \end{bmatrix}K=​121​242​121​​

This kernel is **circularly symmetric** because:

-   If you rotate it 90°, 180°, or 270° around the central element (the value 4), the matrix will look exactly the same.
-   Each concentric "circle" around the center (i.e., the rows and columns at increasing distances from the center) are symmetric.

### Why is this important?

-   **Circularly symmetric kernels** are useful in image processing because they treat all directions around a pixel equally. This can be important when designing filters that shouldn't favor any particular direction, such as blurring filters or Gaussian filters.
-   Circularly symmetric kernels allow for more efficient computation, particularly with separable kernels, which can be broken down into 1-D operations.

### Gaussian Kernels:

A common example of a circularly symmetric kernel is the **Gaussian kernel**, which is used in Gaussian blur operations. The values of the kernel are highest at the center and decrease symmetrically as you move away from the center. A 2D Gaussian kernel might look something like this:

G=116[121242121]G = \frac{1}{16} \begin{bmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \\ 1 & 2 & 1 \end{bmatrix}G=161​​121​242​121​​

This Gaussian kernel is circularly symmetric because rotating it around its center doesn’t change its structure.

___

### Spatial Domain vs. Frequency Domain

#### 1. **Spatial Domain:**

-   **Definition**: In image processing, the **spatial domain** refers to the 2D matrix (grid) of pixel values that represent the intensity or color information of an image.
-   **Representation**: When you think of an image as a 2D array of pixel values, you are working in the **spatial domain**. Each pixel represents a point in space (x, y), and the value of each pixel represents some property (e.g., intensity, color) at that point.
-   **Operations in Spatial Domain**:
    -   **Filtering**: Spatial domain filtering involves directly manipulating the pixel values in the matrix (e.g., convolution with a kernel). The kernel slides over the image, applying operations like blurring, sharpening, or edge detection.
    -   **Example**: Suppose you have an image that is a 5x5 matrix of pixel values. You can apply a 3x3 convolution kernel (like a blur filter) to modify the pixel values by directly operating on the image in the spatial domain.

**Example of a 3x3 image (spatial domain)**:

lua

Copy code

`Image = [[120, 125, 130],
         [122, 128, 131],
         [119, 123, 127]]` 

Here, each number represents the intensity of a pixel at a specific location in the 2D grid.

#### 2. **Frequency Domain:**

-   **Definition**: The **frequency domain** represents an image in terms of the frequencies of pixel intensity changes, rather than directly as pixel values. When an image is transformed from the spatial domain to the frequency domain, its representation shows how often the pixel values change across the image.
-   **Fourier Transform**: The conversion from the spatial domain to the frequency domain is done using a **Fourier transform**. The resulting frequency representation shows how much of each frequency component (low or high) is present in the image.
    -   **Low frequencies** correspond to slow changes in intensity (smooth areas of the image).
    -   **High frequencies** correspond to rapid changes in intensity (edges and details).
-   **Operations in Frequency Domain**:
    -   In the frequency domain, image filtering can be performed by multiplying the Fourier-transformed image by a **filter function**. This is easier in some cases because filtering in the frequency domain is simpler mathematically (multiplication vs. convolution).
    -   **Example**: A **low-pass filter** applied in the frequency domain might reduce high frequencies (sharp changes), resulting in a blurred image when transformed back to the spatial domain.

**Example of a frequency-domain function**: A low-pass filter in the frequency domain could look like this:

lua

Copy code

`Frequency Domain = [[1, 0, 0],
                    [1, 1, 0],
                    [1, 1, 1]]` 

This function allows low frequencies (smooth regions) to pass while blocking higher frequencies (edges or noise).

----------

### Key Points:

1.  **Convolution in the Spatial Domain ≡ Multiplication in the Frequency Domain**:
    
    -   When you apply **convolution** to an image in the spatial domain, it is mathematically equivalent to multiplying the image by a filter in the frequency domain. This equivalence is useful because some operations are easier or faster to perform in the frequency domain (such as filtering).
        
    -   **Example**: Blurring an image in the spatial domain using a convolution with a Gaussian kernel is equivalent to applying a low-pass filter in the frequency domain by multiplying the Fourier-transformed image with the frequency domain version of the filter.
        
2.  **Impulse in the Spatial Domain ≡ Constant in the Frequency Domain**:
    
    -   An **impulse** (a single high-value pixel in a sea of zeroes) in the spatial domain corresponds to a **constant** value in the frequency domain.
    -   Conversely, a constant in the spatial domain (e.g., all pixel values are the same) appears as an impulse in the frequency domain (all the energy is concentrated in the low-frequency component).

----------

### Example to Connect Both Domains:

#### Spatial Domain Example:

Consider a **1D signal** that represents the pixel intensities along a row of an image:

csharp

Copy code

`[10, 12, 14, 16, 18]` 

This is a smooth transition with no sharp changes, so most of the energy is concentrated in the **low-frequency** components.

#### Frequency Domain:

When you take the **Fourier transform** of this signal, you may get something like this:

csharp

Copy code

`[70, 0, 0, 0, 0]` 

Here, the large value at the first frequency represents the dominant low-frequency component, meaning the image has a smooth gradient of intensities.

#### Edge Detection (High Frequencies):

If the original signal has a sharp change (e.g., edges in an image):

csharp

Copy code

`[10, 100, 200, 255, 0]` 

The Fourier transform will have more energy in the **high-frequency** components because the signal changes rapidly.

----------

### Conclusion:

-   The **spatial domain** refers to the original pixel-based representation of an image.
-   The **frequency domain** refers to how often pixel values change across the image, showing the image’s frequency components.
-   Convolution in the spatial domain becomes multiplication in the frequency domain, and impulses (single high values) in one domain correspond to constants in the other.

In summary, the **spatial domain** is where you work directly with pixel values (e.g., an image matrix), and the **frequency domain** represents the underlying frequencies that make up those pixel changes (obtained via Fourier transforms).


