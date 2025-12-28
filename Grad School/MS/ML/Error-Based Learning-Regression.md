Chapter 7, Appendix C

## Simple Linear Regression
- Office Rental Prices Dataset
- $y = mx+b$ is the basic equation
	- rental price = 6.47 + 0.62 X size would be the linear relationship between rental price and size
	- $\mathbb{M}_\textbf{w}(d) = \textbf{w}[0] + \textbf{w}[1] \times \textbf{d}[1]$ is the same equation written with $\textbf{w}$ are the weights of the model and $\textbf{d}$ is the descriptive feature
- Measuring error
	- Also known as a residual
	- We use an error function
	- Sum of squares or $L_2$ error
		- $L_2(\mathbb{M}_{\textbf{w}} \mathcal{D}) = \frac{1}{2}\sum_{i=1}^{n}(t_i - \mathbb{M}_{\textbf{w}}(d_i))$ 
	- Error surface
		- 3d plot of the error
		- We can try to brute-force, but that quickly proves intractable
		- But error surfaces are convex, and hence have global minimum
		- Least-squares optimization
			- Partial derivative of the error surface wrt the weights are equal to 0.
			- At the global min, the lowest point on the error surface
		- Guided search
			- Gradient descent
## Multivariable Linear Regression with Gradient Descent
This model allows us to include more features in a model.
- $\mathbb{M}_\textbf{w}(d) = \textbf{w} \cdot\ \textbf{d}$ 
- gradient descent
	- iteratively adjust the weights by a small amount, based on the error present in the current model, will eventually (hopefully) converge, where changes in the weights do not affect the error
	- delta value is the change added to each weight on each iteration
	- learning rate determines the magnitude of delta

## Extensions and Variations
- Statistical significane test
	1. Compute a test statistic
	2. Probability of a test stat value as big as that is computed, called a $p$-value
	3. $p$-value is compared to a threshold

- We use the $t$-test for multivariable linear regression
- Calculate the standard error
- Learning rate decay
	- Start large, get smaller, allows us to traverse the error surface faster without overshooting the global min

## Handling Categorical Descriptive Features
- One-hot Encoding is one strategy
- Logistic Regression
	- Feeds the output of a linear regression through the logistic function
- Modeling Non-linear relationships
	- Use a basis function
	- Useful in cases where the data is not linearly-separable
- Multinomial Logistic Regression
	- We build $r$ one-vs-all models