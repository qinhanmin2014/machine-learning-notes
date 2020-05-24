## binary

reference: Pattern Recongnition and Machine Learning Section 4.2.1

$$p(x|C_k) = \frac{1}{(2\pi)^{D/2}}\frac{1}{|\Sigma|^{1/2}}exp(-\frac{1}{2}(x-\mu_k)^T\Sigma^{-1}(x-\mu_k))$$

$$p(C_1|x) = \frac{p(x|C_1)P(C_1)}{p(x|C_1)P(C_1) + p(x|C_2)P(C_2)}$$

$$=\frac{1}{1 + exp(-a)} = sigmoid(a) = sigmoid(w^Tx + b)$$

$$a = ln\frac{p(x|C_1)p(C_1)}{p(x|C_2)p(C_2)}$$

$$ = ln\frac{exp(-1/2(x-\mu_1)^T\Sigma^{-1}(x-\mu_1))}{exp(-1/2(x-\mu_2)^T\Sigma^{-1}(x-\mu_2))} + ln\frac{p(C_1)}{p(C_2)}$$

$$=\frac{1}{2}((x-\mu_2)^T\Sigma^{-1}(x-\mu_2) - (x-\mu_1)^T\Sigma^{-1}(x-\mu_1)) + ln\frac{p(C_1)}{p(C_2)}$$

$$=\frac{1}{2}(x^T\Sigma^{-1}x - 2\mu_2^T\Sigma^{-1}x + \mu_2^T\Sigma^{-1}\mu_2 - x^T\Sigma^{-1}x + 2\mu_1^T\Sigma^{-1}x - \mu_1^T\Sigma^{-1}\mu_1) + ln\frac{p(C_1)}{p(C_2)}$$

$$=(\Sigma^{-1}(\mu_1-\mu_2))^Tx - \frac{1}{2}\mu_1^T\Sigma^{-1}\mu_1 + \frac{1}{2}\mu_2^T\Sigma^{-1}\mu_2 + ln\frac{p(C_1)}{p(C_2)}$$

$$w = \Sigma^{-1}(\mu_1-\mu_2)$$

$$b = -\frac{1}{2}\mu_1^T\Sigma^{-1}\mu_1 + \frac{1}{2}\mu_2^T\Sigma^{-1}\mu_2 + ln\frac{p(C_1)}{p(C_2)}$$

## multiclass

reference: Pattern Recongnition and Machine Learning Section 4.2.1

$$p(x|C_k) = \frac{1}{(2\pi)^{D/2}}\frac{1}{|\Sigma|^{1/2}}exp(-\frac{1}{2}(x-\mu_k)^T\Sigma^{-1}(x-\mu_k))$$

$$p(C_k|x) = \frac{p(x|C_k)p(C_k)}{\sum_{j=1}^{K}{p(x|C_j)p(C_j)}}$$

$$= \frac{exp(a_k)}{\sum_{j=1}^{K}{exp(a_j)}}$$

$$= \frac{exp(w_k^Tx+b_k)}{\sum_{j=1}^{K}{exp(w_jx+b_j)}}$$

$$= \frac{exp(w_k^Tx+b_k-constant)}{\sum_{j=1}^{K}{exp(w_jx+b_j-constant)}}$$

$$a_k = ln(p(x|C_k)p(C_k))$$

$$w_kx+b_k = ln(exp(-\frac{1}{2}(x-\mu_k)^T\Sigma^{-1}(x-\mu_k))) + lnp(C_k)\ (remove\ constant)$$

$$= -\frac{1}{2}(x-\mu_k)^T\Sigma^{-1}(x-\mu_k) + lnp(C_k)$$

$$= -\frac{1}{2}(x^T\Sigma^{-1}x - 2\mu_k^T\Sigma^{-1}x + \mu_k^T\Sigma^{-1}\mu_k) + lnp(C_k)$$

$$= (\Sigma^{-1}\mu_k)^Tx - \frac{1}{2}\mu_k^T\Sigma^{-1}\mu_k + lnp(C_k)\ (remove\ constant)$$

$$w_k = \Sigma^{-1}\mu_k$$

$$b_k = -\frac{1}{2}\mu_k^T\Sigma^{-1}\mu_k + lnp(C_k)$$
