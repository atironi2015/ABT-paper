// Write in Magma only one of the following three blocks of Magma instructions before to load all the library "Magma Functions - Skew Resultants.txt", 
// depending on which division ring you want to work


// Block 1 - A field with four elements

F<w>:=GF(4); 

R<x>:=PolynomialRing(F);

S:= map< F -> F | x :-> x^2 >;

D:= map< F -> F | x :-> w*(S(x)+x) >;


// Block 2 - The complex field

F<i>:=ComplexField();

R<x>:=PolynomialRing(F);

S:= map< F -> F | x :-> ComplexConjugate(x) >;

D:= map< F -> F | x :-> x-ComplexConjugate(x) >;


// Block 3 - Quaternion algebra

F<i,j,k> := QuaternionAlgebra< RealField() | -1, -1 >;

R<x>:=PolynomialRing(F);

S:= map< F -> F | x :-> i*x*(1/i) >;

D:= map< F -> F | x :-> 0 >;
