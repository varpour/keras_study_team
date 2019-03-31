- **设有函数**
$$
 y = Xw + \epsilon
$$

- **有m个特征时$y_i$ :** 
$$
 y_i = \sum_{j=0}^m {w_jX_{ij} + \epsilon_i}
$$

- ** 所以有损失函数 $F(X,y,w)$ :**
\begin{align}
 F(X,y,w) & = \frac{1}{2n} \sum_{i=1}^n {(y_i - w^Tx_i)}^2  \\
       & = \frac{1}{2n} ||y - Xw||_2^2  \\
       & = \frac{1}{2n} (y - Xw)^T(y - Xw)  \\
       & = \frac{1}{2n} (y^Ty - 2y^TXw + w^TX^TXw)
 \end{align}

- **因为有： **
$$
 \frac{\partial X^TA}{\partial X}  = A  \\
 \frac{\partial X^TAX}{\partial X} = (A+A^T)X  \\
 \frac{\partial X^TAy}{\partial A}  = X^Ty  \\
$$

- **所以： **
$$
 y^TXw = <X^Ty,w> = <w,X^Ty> = x^TX^Ty   \text {  (向量内积公式)}    \\
 \frac{\partial y^TXw}{\partial w}  = \frac{\partial x^TX^Ty}{\partial w} = X^Ty  \\
 \frac{\partial w^TX^TXw}{\partial w}  = (X^TX + (X^TX)^T)w = 2X^TXw  \\
$$ 

- **所以： **
\begin{align}
 \frac{\partial F}{\partial w} & = 
 \frac{\partial \frac{1}{2n}(y^Ty - 2y^TXw + w^TX^TXw)}{\partial w}  \\
  & = \frac{1}{2n}(-2X^Ty +2X^TXw)  
\end{align}
 
 _ **所以：**
 
\begin{align}
 \frac{\partial F}{\partial w}   = 0    
 & \iff \frac{1}{2n}(-2X^Ty +2X^TXw)  = 0   \\
 & \iff  -X^Ty + X^TXw  = 0   \\
 & \iff X^Tw  = X^Ty  \\
 & \iff w  = (X^TX)^{-1}X^Ty  \\
\end{align}
