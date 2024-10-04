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
