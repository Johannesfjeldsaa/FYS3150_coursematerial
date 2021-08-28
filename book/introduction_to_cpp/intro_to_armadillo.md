# Introduction to Armadillo

Armadillo is an efficient linear algebra library for C++ users. Its aim is to provide a library that balances speed and ease of use. We recommend this library for numerical computations as a replacement for dynamic allocation of arrays.

We'll cover the very basics here to get you started with the library. However, their webpage provide an excellent, detailed [code documentation](http://arma.sourceforge.net/docs.html) with examples of usage that you can search through.

## Building code with Armadillo

We must make sure to include the header file for Armadillo, which amounts to adding `#include <armadillo>` at the top of a header or source file.

### Compiling code with Armadillo
For macOS users specifically, you must specificy a version of C++ that is C++11 or later. This is done by adding the compiler flag `-std=c++11` during compilation.

For Linux users, nothing special is typically required.


### Linking code with Armadillo

To link to Armadillo, we must add the compiler flag `-larmadillo` during linking.

## Vectors

Armadillo provides a useful vector class `arma::vec` that can be used to replace arrays in numerical computations. Assume `n` is a positive integer.

### Declaring and filling vectors

```c++
arma::vec x = arma::vec(n); //Initialize vector but don't fill.
arma::vec y = arma::vec(n).fill(2.); //Declare and fill with 2's.
arma::vec z = arma::vec(n).randu(); //Declare and will with random uniform values.
```

### Accessing and assigning elements in a vector

We can access an element `i` from a vector `x` by

```c++
double x_i = x(i); //Extract element i of x and assign it to x_i.
```

We can assign a new value to element `i` in the vector `x` using

```c++
x(i) = some_new_value;
```

## Matrices
Assume that `n` and `m` are positive integers.


### Declaring and filling matrices

Creating matrices with Armadillo is easy. Here's a couple examples:

```c++
arma::mat A = arma::mat(n, m); //Initialize but don't fill
arma::mat B = arma::mat(n, m).fill(0.); //Declare and fill with zeros.
arma::mat C = arma::mat(n, m).randn(); //Declare and fill with random values from the normal distribution.
```

### Accessing elements in a matrix

Access of elements in an Armadillo matrix is done as follows:

```c++
double A_ij = A(i,j); //Assign element (i,j) of the matrix A to A_ij.
```

### Extracting a column of a matrix

Armadillo provides a simple way to extract entire columns of a matrix:

```c++
arma::vec col_vec = A.col(j); //Extract column j of A and assign it to col_vec.
```