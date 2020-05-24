## Normal Equation

$$L = (y-Xw)^T(y-Xw) + \lambda \left\|w\right\|^2_2$$

$$=(y^T-w^TX^T)(y-Xw) + \lambda \left\|w\right\|^2_2$$

$$=y^Ty-y^TXw-w^TX^Ty+w^TX^TXw + \lambda w^Tw$$

$$\frac{\partial L}{\partial w} = -X^Ty - X^Ty + 2X^TXw + 2\lambda w = 0$$

$$X^TXw - X^Ty + \lambda w = 0$$

$$w = (X^TX + \lambda I)^{-1}X^Ty$$

## SVD

$$X=USV^T,UU^T=I,VV^T=I$$

$$w = (X^TX + \lambda I)^{-1}X^Ty$$

$$=(VS^2V^T+\lambda I)^{-1}VSU^Ty$$

$$=(VS^2V^T+\lambda VV^T)^{-1}VSU^Ty$$

$$=(V(S^2+\lambda I)V^T)^{-1}VSU^Ty$$

$$=V(S^2+\lambda I)^{-1}V^TVSU^Ty$$

$$=V(S^2+\lambda I)^{-1}SU^Ty$$

$$=V\sum{\frac{s_i}{s_i^2+\lambda}}U^Ty$$

## Kernel Ridge

$$w = (X^TX + \lambda I)^{-1}X^Ty$$

$$(X^TX + \lambda I)^{-1}X^T = X^T(XX^T+\lambda I)^{-1}$$

$$ \Leftrightarrow X^T(XX^T+\lambda I)=(X^TX + \lambda I)X^T$$

$$ \Leftrightarrow X^TXX^T+\lambda X^T=X^TXX^T+\lambda X^T$$

$$w = X^T(XX^T + \lambda I)^{-1}y$$

$$= X^T(K(X, X) + \lambda I)^{-1}y$$

$$y_{test} = K(X_{test}, X)(K(X, X) + \lambda I)^{-1}y$$
