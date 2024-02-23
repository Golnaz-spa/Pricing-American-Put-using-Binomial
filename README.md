# American Put Option - Binomial Lattice Model

This Jupyter Notebook provides an implementation for calculating the value of an American Put Option using the Binomial Lattice model. It also demonstrates the relationship between various strike prices and the option value through a plotted graph. The model allows for adjustments in parameters like the initial stock price (S0), strike price (K), time to maturity (T), risk-free rate (r), number of steps (N), up (u) and down (d) factors, and the option type.

## Features

- **American Put Option Pricing**: Uses the Binomial Lattice method to compute the value of an American Put Option. This method is suitable for options that can be exercised before their expiration date.
- **Visualization**: Plots the relationship between different strike prices and the option value, providing a visual representation of how the option value changes with the strike price.
- **Customizable Parameters**: Allows the user to input various parameters such as the strike price, time to maturity, risk-free rate, and more to observe their impact on the option's value.

## Usage

1. **Define the Binomial Tree Function**: This function calculates the option value using the Binomial Lattice approach, considering the option to exercise early.
2. **Set Parameters**: Define the parameters for your option, including the strike price, time to maturity, initial stock price, risk-free rate, volatility, up and down factors, and option type.
3. **Iterate Over Strike Prices**: Run the binomial tree function for a range of strike prices to observe how the option value changes.
4. **Plot Results**: Visualize the relationship between strike prices and option values using `matplotlib`.

## Example

```python
S0 = 25  # Initial stock price
K = 25  # Strike price
T = 1  # Time to maturity
r = 0.21  # Risk-free rate
N = 3  # Number of steps
sigma = 0.4  # Volatility
u = 1.1  # Up factor
d = 0.9  # Down factor
opttype = "P"  # Option type (P for put)

# Various strike prices in the range 20-30
k = range(20, 30, 1)
strikeprice_american = []
for i in k:
    option_value = AmericanPut_binomial_tree(i, T, S0, r, N, u, d, opttype)
    strikeprice_american.append(option_value)

print(strikeprice_american)
plt.plot(k, strikeprice_american)
plt.show()
```
