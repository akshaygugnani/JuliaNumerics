# Scalar Functions extended to Matrix functions of Matrices:
**Wikipedia Definition:**
http://en.wikipedia.org/wiki/Matrix_function#Extending_scalar_functions_to_matrix_functions

**Notation:** f(M)

**Ambiguities:** (other reasonable definitions of f(M)) 

1. Pointwise application of f. . 
2. Cholesky Decoposition when f(x)=sqrt(x). (another generalization
   of scalar sqrt)
3. Less well known: Scalar Functions extended to *scalar* functions of Matrix Argument (this page covers scalar functions extended to  *matrix* functions of matrix argument)

 

**Numerical Conditioning Issues:**  The Mathematical Definition, while easy to implement, 
      can be highly ill-conditioned, especially when the eigenvector matrix itself
      is ill-conditioned.  The Schur decomposition (available in Lapack) can ameliorate this.

**Branch Cuts:**  The issue of the proper handling of branch cuts for scalar functions
              is tricky enough.  It has been virtually ignored for matrix functions.
               Very likely different software packages will make different choices.

**Extra Accuracy:**  Many of the most common elementary scalar functions
such as sqrt (required by IEEE) and sine (if the right libraries are used) can be accurate to
                the last bit, even when ill-conditioned.  This may be beyond
                 reach in the matrix case, and anyway has not been carefully studied.

**References:** van Loan, Higham ....  (especially Higham's book)

**Embelishments for efficiency and accuracy:**  
 `f(M,v) = f(M)*v` (computed more efficiently).  For example, if
f(x)=1/x, `f(M,v)=M\v`.

 
**Rosetta Stone**                    
<table>
<tr>
<th> Function:    </th><th>   Julia </th><th>  MATLAB </th><th>            Mathematica     </th><th>       Maple ([LinearAlgebra] package) </th><th>R</th>
<tr><th> Powers  </th><th>M^p</th><th> M^p </th><th>   MatrixPower </th><th>     MatrixPower </tr>
<tr><th> Inverses </th><th>M^-1 or inv(M) </th><th>M^(-1) or inv(M) </th>  <th> Inverse </th><th>                MatrixInverse </th></tr>
<tr><th>Matrix Exponential </th>     <th>expm</th><th>   expm </th>            <th> MatrixExp </th><th>    MatrixExponential </th>
</tr>
<tr><th> Matrix Logarithm  </th><th>   </th><th>                logm </th>      <th>       MatrixLog </th><th>    use MatrixFunction </th>
<tr><th>Matrix Sqrt</th> <th>M^.5</th> <th>                       sqrtm,M^(.5)  </th><th>   MatrixPower[M,0,5]   </th>  <th> use MatrixPower </th>
</tr>
<tr>
<th>General Functions </th>   <th></th><th>                 funm </th> <th>     MatrixFunction </th><th>         MatrixFunction
 </th></table>

**Test Case**
`[0 1;0 0]^.5` should probably not be finite

**Intra-Language inconsistency**

1. Julia: scalar `(-1)^.5` is a NaN, matrix `(-eye(2))^.5` gives complex answers.

**Inter-Language inconsistency**


Additions that might make sense:

1.  A page for separate matrix functions
2.  Completion and Annotation of Reference List
3.  R, Python Syntax
4.  Numerical comparison of good test cases

would be good to add R and python and point out exactly the places where there are interesting numerical differencs.




Note: in many cases the general functions could readily be replaced with alternatives that are faster 
e.g. if matrices are hermitian the spectral approach 
