#algorithm #classical

# to write better! Talk about Pivots

https://en.wikipedia.org/wiki/Gaussian_elimination

**Gaussian elimination**, also known as **row reduction**, is an [algorithm](https://en.wikipedia.org/wiki/Algorithm "Algorithm") for solving [systems of linear equations](https://en.wikipedia.org/wiki/System_of_linear_equations "System of linear equations"). It consists of a sequence of operations performed on the corresponding [matrix](https://en.wikipedia.org/wiki/Matrix_(mathematics) "Matrix (mathematics)") of coefficients. This method can also be used to compute the [rank](https://en.wikipedia.org/wiki/Rank_(linear_algebra) "Rank (linear algebra)") of a matrix, the [determinant](https://en.wikipedia.org/wiki/Determinant "Determinant") of a [square matrix](https://en.wikipedia.org/wiki/Square_matrix "Square matrix"), and the inverse of an [invertible matrix](https://en.wikipedia.org/wiki/Invertible_matrix "Invertible matrix").

To perform row reduction on a matrix, one uses a sequence of [elementary row operations](https://en.wikipedia.org/wiki/Elementary_row_operations "Elementary row operations") to modify the matrix until the lower left-hand corner of the matrix is filled with zeros, as much as possible. There are three types of elementary row operations:

- Swapping two rows,
- Multiplying a row by a nonzero number,
- Adding a multiple of one row to another row.

Using these operations, a matrix can always be transformed into an [upper triangular matrix](https://en.wikipedia.org/wiki/Triangular_matrix "Triangular matrix"), and in fact one that is in [row echelon form](https://en.wikipedia.org/wiki/Row_echelon_form "Row echelon form").

Once all of the leading coefficients (the leftmost nonzero entry in each row) are 1, and every column containing a leading coefficient has zeros elsewhere, the matrix is said to be in [reduced row echelon form](https://en.wikipedia.org/wiki/Reduced_row_echelon_form "Reduced row echelon form"). This final form is unique; in other words, it is independent of the sequence of row operations used.