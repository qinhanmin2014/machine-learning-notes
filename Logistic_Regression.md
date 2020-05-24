## scikit-learn multiclass='ovr'

reference: http://fa.bianp.net/blog/2013/numerical-optimizers-for-logistic-regression/

$$L = -\sum_{i=1}^{n}{ln(sigmoid(y_i(w^Tx_i + b)))} + \frac{\lambda}{2}\left\|w\right\|_2^2$$

$$sigmoid(x) = \frac{1}{1 + exp(-x)}$$

$$sigmoid^{\prime}(x) = sigmoid(x)(1 - sigmoid(x))$$

$$\frac{\partial L}{\partial w} = -\sum_{i = 1}^{n}{\frac{1}{sigmoid(y_i(w^Tx_i + b))}sigmoid(y_i(w^Tx_i + b)) (1 - sigmoid(y_i(w^Tx_i + b))) y_ix_i} + \lambda w$$

$$= \sum_{i = 1}^{n}{y_ix_i (sigmoid(y_i(w^Tx_i + b)) - 1)} + \lambda w$$

$$\frac{\partial L}{\partial b} = -\sum_{i = 1}^{n}{\frac{1}{sigmoid(y_i(w^Tx_i + b))}sigmoid(y_i(w^Tx_i + b)) (1 - sigmoid(y_i(w^Tx_i + b))) y_i} + \lambda w$$

$$= \sum_{i = 1}^{n}{y_i (sigmoid(y_i(w^Tx_i + b)) - 1)} + \lambda w$$

## scikit-learn multiclass='multinomial'

reference: Pattern Recongnition and Machine Learning Section 4.3.4

$$p_i^k = \frac{exp(w_k^Tx_i + b_k)}{\sum_{j=1}^{K}{exp(w_j^Tx_i + b_j)}}$$

$$L = -\sum_{i=1}^{n}\sum_{k=1}^{K}{y_i^klogp_i^k} + \frac{\lambda}{2}\left\|w\right\|_2^2$$

$$= -\sum_{i=1}^{n}\sum_{k=1}^{K}{(y_i^k((w_k^Tx_i + b_k) - ln(\sum_{j=1}^{K}{exp(w_j^Tx_i + b_j)})))} + \frac{\lambda}{2}\left\|w\right\|_2^2$$

$$= -\sum_{i=1}^{n}\sum_{k=1}^{K}{y_i^k(w_k^Tx_i + b_k)} + \sum_{i=1}^{n}{ln(\sum_{j=1}^{K}{exp(w_j^Tx_i + b_j)})} + \frac{\lambda}{2}\left\|w\right\|_2^2$$

$$\frac{\partial L}{\partial w_k} = -\frac{1}{n}\sum_{i=1}^{n}{y_i^kx_i} + \frac{1}{n}\sum_{i=1}^{n}{\frac{1}{\sum_{j=1}^{K}{exp(w_j^Tx_i + b_j)}}exp(w_k^Tx_i + b_k)x_i} + \lambda w_k$$

$$ = \frac{1}{n}\sum_{i=1}^{n}{(p_i^k-y_i^k)x_i} + \lambda w_k$$

$$\frac{\partial L}{\partial b_k} = -\frac{1}{n}\sum_{i=1}^{n}{y_i^kx_i} + \frac{1}{n}\sum_{i=1}^{n}{\frac{1}{\sum_{j=1}^{K}{exp(w_j^Tx_i + b_j)}}exp(w_k^Tx_i + b_k)}$$

$$ = \frac{1}{n}\sum_{i=1}^{n}{(p_i^k-y_i^k)}$$
