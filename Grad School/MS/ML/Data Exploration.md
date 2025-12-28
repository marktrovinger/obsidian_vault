### Data Quality Report
- Tabular Reports
	- Continuous and categorical data
	- Uses statistical measures like central tendency and variation
	- Cardinality
		- Measure of distinct values for each feature
	- Presents data in histograms, bar plots and box plots
### Getting to know your Data
- Categorical
	- Mode, 2nd Mode, mode %, 2nd mode %
- Continuous
	- Mean, std dev, min/max
- Probability distributions
	- Uniform, normal, unimodal (both directions), Exponential, Multimodal
### Normal Distribution
Follows the probability density function:
$N(x, \mu, \sigma)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ 

- $\mu$ is the population mean
- $\sigma$ is the population std dev

Standard normal distribution has $\mu=0$ and $\sigma=1$.

### ID Data Quality Issues
- Missing values
	- >60%, probably should remove feature
- Irregular Cardinality
	- Cardinality of 1 is a red flag
	- Investigate if it is a result of a data generation error
	- Check categorical as continuous 
	- Multiple unneeded levels
	- > 50 levels requires investigation
- Outliers
	- Invalid
		- Noise
	- Valid
		- Skewed histograms
		- Check median and 3rd quartile
- Invalid Data 
- Valid Data
- Data Quality Plan
	- Reports any issues mentioned above

### Handling Data Quality Issues
- Missing Values
	- Delete feature
	- Missing data flag
	- Complete case analysis
		- Deletes instances which have missing data
		- Nuclear option
	- Imputation
		- Plausible estimate
		- Mean and median are common
		- If too many are missing, this may not be a good strategy
		- Try simple approaches first, then complex if needed
	- Outliers
		- Clamping
			- Many different ways to set the threshold
### Advanced Data Exploration
- Investigate relationships between features
	- Visualization
		- Scatter Plot Matrix
		- Pairs of categorical features
			- Small multiples
			- Stacked bar plots
		- Categorical and Continuous
			- Density histogram
			- Collection of box plots
	- Covariance and Correlation
		- $cov(a,b) = \frac{1}{n-1} \sum_{i=1}^{n}((a_i - \bar{a}) x (b_i - \bar{b}))$   
		- $corr(a, b) = \frac{cov(a,b)}{\sigma(a)*\sigma(b)}$ 
		- range: $[-1,1]$, $-1$ is a strong negative correlation, $1$ is a strong positive correlation
		- Independent variables have no correlation

### Data Prep
Part of the Data Preparation step of CRISP-DM
- Normalization
	- Range normalization, linear scaling
	- Standardization
		- Standard scores, using a formula, the same formula I emailed Dr. Yoo about
- Binning
	- Continuous to categorical
	- Tradeoff between resolution and instances per bin
	- Equal-width
		- $\frac{range}{b}$, where $b$ is the number of bins
		- Can waste bins
	- Equal-frequency
		- $\frac{instances}{b}$, similar to above
		- Varying size of bins can be misleading
- Sampling
	- Top Sampling, $s\%$ 
	- Random Sampling
	- Stratified Sampling
		- Maintains relative frequency of levels
- Over/under sampling
	