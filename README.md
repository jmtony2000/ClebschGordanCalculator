# ClebschGordanCalculator

This repository contains programmes to calculate the non-zero Clebsch--Gordan coefficients of a system with given J, j1, j2 value using recursion relations.

The coupled states can be expended in the following format: 
$$\ket{J,M} = \sum_{m1,m2}\mathcal{C}(j_{1},m_1,j_2,m_2|J,M)\ket{j_{1},m_1,j_2,m_2}$$
The coefficient only has a non-zero value if 
$m_1+m_2=M$
The total angular momentum raising and lowering operators is:    
$$\hat{J}_{\pm} = \hat{J}^{(1)}_{\pm} \otimes \hat{I}^{(2)} + \hat{I}^{(1)} \otimes \hat{J}^{(2)}_{\pm}$$
The operator's effect on a state is$$\hat{J}_{\pm}\ket{j,m} = \hbar C_{\pm}(j,m)\ket{j,(m+1)}$$where the ladder coefficient is given by
$$C_{\pm}(j,m) = \sqrt{j(j+1)-m(m\pm1)}$$
The get the recursion relations the total angular momentum raising and lowering operators have to be applied to left hand / right hand side. 
To get the recursion relation the indexes have to be changed to be able to extract the $\ket{j_1\,m_1}\ket{j_2,m_2}$ state from the equation. This way we get the recursion relations:
$$ C_{\pm} (J,M) C \left( j_1,m_1,j_2,m_2 | JM\pm 1 \right) = C_{\pm} (j_1, m_{1 \mp 1}) C \left( j_1, m_{1 \mp 1}, j_2, m_2 | JM \right) + C_{\pm} (j_2, m_{2 \mp 1}) C \left( j_1, m_1, j_2, m_{2 \mp 1} | JM  \right)$$
Taking the upper sign and the condition that $M = J$ we get the initial recursion relation: 
$$0 = C_+ (j_1,m_{1}-1) \mathcal{C} \left( j_1, m_{1}-1,j_2,m_2 |J,J \right) + C_+ (j_2, m_{2}-1) \mathcal{C} \left( j_1, m_1, j_2, m_{2-1} | J,J \right)$$
$$\mathcal{C} \left( j_1, m_{1}-1,j_2,m_2 |J,J \right) = -\frac{C_{+}(j_{2},m_{2}-1) }{C_{+}(j_{1},m_{1}-1)}\mathcal{C} \left( j_1, m_1, j_2, m_{2-1} | J,J \right)$$
In the Condon–Shortley phase convention, one adds the constraint that:
$$\mathcal{C}\left(j_{1},j_{1},j_{2},J-j_{1}|J,J\right)>0$$
Using this recursion relation and the constraint starting from the $\mathcal{C} \left( j_1, m_{1},j_2,m_2 |J,J \right)$ coefficient all coefficients in the state $\ket{JJ}$ can be calculated.  After this all other coefficients can be calculated using the lower sign relation.