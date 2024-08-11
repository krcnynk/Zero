
**Invoking SIMD**
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

```cpp
#include <iostream>

// Forward declarations
template<typename T> class Matrix;
template<typename T> class AddExpression;

// Base matrix class
template<typename T>
class Matrix {
public:
    Matrix(std::size_t rows, std::size_t cols) : rows_(rows), cols_(cols) {
        data_ = new T[rows * cols];
    }

    ~Matrix() {
        delete[] data_;
    }

    T& operator()(std::size_t row, std::size_t col) {
        return data_[row * cols_ + col];
    }

    T operator()(std::size_t row, std::size_t col) const {
        return data_[row * cols_ + col];
    }

    std::size_t rows() const { return rows_; }
    std::size_t cols() const { return cols_; }

    // Evaluate the matrix expression
    T eval(std::size_t row, std::size_t col) const {
        return expr_ ? expr_->eval(row, col) : (*this)(row, col);
    }

    void set_expression(const AddExpression<T>* expr) {
        expr_ = expr;
    }

private:
    T* data_;
    std::size_t rows_;
    std::size_t cols_;
    const AddExpression<T>* expr_ = nullptr;
};

// Expression template for addition
template<typename T>
class AddExpression {
public:
    AddExpression(const Matrix<T>& lhs, const Matrix<T>& rhs) : lhs_(lhs), rhs_(rhs) {}

    T eval(std::size_t row, std::size_t col) const {
        return lhs_(row, col) + rhs_(row, col);
    }

private:
    const Matrix<T>& lhs_;
    const Matrix<T>& rhs_;
};

// Operator to create an AddExpression
template<typename T>
AddExpression<T> operator+(const Matrix<T>& lhs, const Matrix<T>& rhs) {
    return AddExpression<T>(lhs, rhs);
}

```