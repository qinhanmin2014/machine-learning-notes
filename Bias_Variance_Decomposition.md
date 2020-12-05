$$expected\ generalization\ error = noise + bias^2 + variance$$

$$y_i = f(x_i) + \epsilon_i$$

$$E(\epsilon) = 0$$

estimate $f$ with $\hat{f}$

denote $f(x_0)$ as $f$, denote $\hat{f}(x_0)$ as $\hat{f}$

$$bias = E\hat{f} - f$$

$$variance = E((\hat{f} - E\hat{f})^2)$$

$$expected\ generalization\ error = E((y - \hat{f})^2)$$

$$=E((y - f + f - \hat{f})^2)$$

$$=E((y - f)^2) + E((f - \hat{f})^2) + 2E(y - f)(f - \hat{f})$$

$$E(y - f)(f - \hat{f}) = E\epsilon(f - \hat{f}) = E\epsilon E(f - \hat{f}) = 0$$

($\epsilon$ is related to test set, $\hat{f}$ is related to training set, so they are independent)

$$expected\ generalization\ error = E((y - f)^2) + E((f - \hat{f})^2)$$

$$= E(\epsilon^2) + E((f - \hat{f})^2)$$

$$= noise + E((f - \hat{f})^2)$$

$$= noise + E((f - E\hat{f} + E\hat{f} - \hat{f})^2)$$

$$= noise + E((f - E\hat{f})^2) + E((E\hat{f} - \hat{f})^2) + 2E(f - E\hat{f})(E\hat{f} - \hat{f})$$

$$E(f - E\hat{f})(E\hat{f} - \hat{f}) = E(fE\hat{f} - f\hat{f} - E\hat{f}E\hat{f} + \hat{f}E\hat{f})$$

$$=fE\hat{f} - fE\hat{f} - E\hat{f} + E\hat{f} = 0$$

$$expected\ generalization\ error = noise + E((f - E\hat{f})^2) + E((E\hat{f} - \hat{f})^2)$$

$$= noise + (E\hat{f} - f)^2 + E((\hat{f} - E\hat{f})^2)$$

$$= noise + bias^2 + variance$$
