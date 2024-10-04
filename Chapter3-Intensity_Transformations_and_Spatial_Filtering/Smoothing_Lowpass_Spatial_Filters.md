You can combine multiple kernels into a composite kernel and then, if the composite kernel is separable, you can apply the computational efficiency of separable kernels to this composite kernel.
___
**Box Kernel vs. Gaussian Kernel:**

-   A **box kernel** assigns the **same weight to all pixels** in the region it covers. This means every pixel within the kernel contributes equally to the final value of the pixel being processed, leading to **uniform blurring**.
-   A **Gaussian kernel**, on the other hand, assigns **varying weights** to the pixels based on their distance from the center of the kernel. Pixels closer to the center have higher weights, while those further away have lower weights. This results in **smoother blurring** that gradually fades.
**Larger Gaussian Kernels Needed for Same Blurring:**

-   To achieve the **same degree of blurring** as a box kernel, a **Gaussian kernel must be larger** because it gives less weight to the pixels far from the center.
-   In the example, a **Gaussian kernel** of size **21 × 21** with a standard deviation σ=3.5\sigma = 3.5σ=3.5 results in **less blurring** than a similar-sized **box kernel**.
-   To achieve comparable results to the box kernel, you need to **increase the size** of the Gaussian kernel to **43 × 43** with σ=7\sigma = 7σ=7. This is because the Gaussian kernel's weights decrease with distance, so more pixels (larger kernel size) are needed to create the same overall blurring effect.


___
Why Edge Pixels Change Less:
In most cases, edge pixels have neighboring values that are distinctly different from one side of the edge to the other. The median filter is good at picking a value that aligns more with the predominant values in the neighborhood, meaning it’s less likely to "pull" the intensity toward the opposite side of the edge, unlike a mean filter that averages everything. This ensures that the sharp transition (edge) between two regions remains more intact.

So, while edge pixels do change, they change less drastically than they would with a linear filter because the median filter resists extreme outlier changes and preserves local pixel groups with similar intensities.
