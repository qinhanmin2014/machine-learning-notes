## Gradient Descent

$$L = \frac{1}{2}\sum_{i=1}^{n}{(y_i-w^Tx_i-b)^2}$$

$$\frac{\partial L}{\partial w} = \sum_{i=1}^{n}{(w^Tx_i+b-y_i)x_i}$$

$$\frac{\partial L}{\partial b} = \sum_{i=1}^{n}{(w^Tx_i+b-y_i)}$$

## Normal Equation

$$L = (y-Xw)^T(y-Xw)$$

$$=(y^T-w^TX^T)(y-Xw)$$

$$=y^Ty-y^TXw-w^TX^Ty+w^TX^TXw$$

$$\frac{\partial(a^Tx)}{\partial x} = (\frac{\partial \sum_{i=1}^{n}{a_ix_i}}{\partial x_p})_p = (a_p)_p = a$$

$$\frac{\partial(x^TAx)}{\partial x} = (\frac{\partial \sum_{i=1}^{n}\sum_{j=1}^{n}{a_{ij}x_ix_j}}{\partial x_p})_p$$

$$= (\sum_{i=1}^{n}{(a_{ip} + a_{pi})x_i})_p = (A+A^T)x$$

$$\frac{\partial L}{\partial w} = -X^Ty - X^Ty + 2X^TXw = 0$$

$$X^TXw - X^Ty = 0$$

$$w = (X^TX)^{-1}X^Ty$$
