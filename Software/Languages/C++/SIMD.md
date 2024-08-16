Status: **Editing**

Tags: [[C++]]

# SIMD
```cpp
#include <iostream>
#include <vector>
#include <cstddef>
#include <cstdlib>
#include <new>
#include <emmintrin.h>  // For SSE2 intrinsics
void add_arrays(const float* a, const float* b, float* result, size_t size) {
    size_t i = 0;
    for (; i + 4 <= size; i += 4) {
        __m128 va = _mm_load_ps(&a[i]);  // Load 4 floats from 'a'
        __m128 vb = _mm_load_ps(&b[i]);  // Load 4 floats from 'b'
        __m128 vr = _mm_add_ps(va, vb);  // Add the vectors
        _mm_store_ps(&result[i], vr);    // Store result
    }
    for (; i < size; ++i) {  // Handle any remaining elements
        result[i] = a[i] + b[i];
    }
}
```
Eigen has SIMD support
Boost has SIMD support




# References
**Invoking SIMD**
