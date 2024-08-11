For example, an expression like `A + B * C` is represented by template classes that encode the addition and multiplication operations without performing them immediately.

```cpp
// Basic matrix class with expression templates
template<typename T>
class Matrix {
public:
    // Constructor, destructor, and other methods...
    // Expression template for addition
    template<typename OtherMatrix>
    auto operator+(const OtherMatrix& other) const {
        return AddExpression<T, Matrix, OtherMatrix>(*this, other);
    }
private:
    T* data_;
};

template<typename T, typename LHS, typename RHS>
class AddExpression {
public:
    AddExpression(const LHS& lhs, const RHS& rhs) : lhs_(lhs), rhs_(rhs) {}

    T eval(size_t i) const {
        return lhs_.data_[i] + rhs_.data_[i];
    }
private:
    const LHS& lhs_;
    const RHS& rhs_;
};

```