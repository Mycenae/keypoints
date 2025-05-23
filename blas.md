# blas

## level 1 blas: vector, O(n) operations

| name | description | equation |
| ---- | ----------- | -------- |
| axpy | update vector | y = y + alpha*x |
| scal | scale vector  | y = alpha*x     |
| copy | copy vector   | y = x           |
| swap | swap vectors  | x <-> y         |
| dot  | dot product   | x^T * y         |
| nrm2 | 2-norm        |                 |
| asum | 1-norm        |                 |
| i_amax | inf-norm    |                 |
| rot  | vector rotation |               |

## level 2 blas: matrix-vector, O(n^2) operations

| name | description | equation |
| ---- | ----------- | -------- |
| gemv | general matrix-vector multiply | y = alpha * A * x + beta * y |
| ger  | general rank-1 update          | A = A + alpha * x * y^T      |

## level 2 blas, band storage

带状矩阵（band matrix）是指仅在主对角线及其上下若干对角线有非零元素的矩阵，其余元素为零。

BLAS 采用列优先压缩方式：每列只存储上下带宽范围内的元素，其余省略。

## level 2 blas, packed storage

对称矩阵（或三角矩阵）中，矩阵的上三角或下三角部分完全冗余，可以只存其中一半。

将其列优先的方式存储为一维数组存储。

## level 3 blas: matrix-matrix, O(n^3) operations

| name | description | equation |
| ---- | ----------- | -------- |
| gemm | general matrix-matrix multiply | C=alpha* A *B   + beta * C |
| syrk | symmetric rank-k update        | C=alpha* A *A^T + beta * C |

## Prefixes

s为float，d为double，c为complex，z为double complex

ge为general，gb为general banded

sy为symmetric，sb为symmetric banded，sp为symmetric packed

he为Hermitian，hb为Hermitian banded，hp为Hermitian packed

tr为triangular，tb为triangular banded，tp为triangular packed

## Options

trans有转置，不转置，共轭转置3个选项

ldA是矩阵A的leading dimension

对于一个row-major存储的矩阵，其leading dimension是指其矩阵的列数

解释：矩阵在内存中是按照一行一行连续存储的，每两行之间的间隔，是列数个元素的存储空间

尤其是在取一个矩阵的子矩阵时，其子矩阵的leading dimension是原始矩阵的列数

如，对于原始矩阵A大小M * N，取子矩阵a大小m * n = A[1:1+m, 1:1+n]，虽然子矩阵大小为m * n，但是在内存中，每行之间的间隔还是N，而不是n，所以子矩阵a的leading dimension仍然是N，而不是n。