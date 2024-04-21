# Cointegration in Financial Markets

Cointegration, a concept introduced by Clive W.J. Granger, Nobel laureate in Economics, in 1981, is fundamental to pairs and multi-asset trading strategies. Despite its significance, the term "cointegration" might not be familiar to everyone, as it's not commonly found in dictionaries or spell checkers.

This article aims to demystify cointegration by answering key questions:

1. **Integration in Cointegration**: What does "integration" in "cointegration" mean?
2. **Intuitive Interpretations**: How can we intuitively understand cointegrated time series?
3. **Constructing a Stationary Spread**: How can we create a stationary spread from two non-stationary price series?
4. **Simulation of Cointegrated Series**: How can we simulate a cointegrated asset pair from scratch?

## What is Cointegration?

The term "integration" in cointegration refers to an integrated time series of order $ d $, denoted as $ I(d) $. Price, rate, and yield data are typically assumed to be $ I(1) $ series, while returns (obtained by differencing the price) are $ I(0) $ series. A key property of $ I(0) $ series is that they are weak-sense stationary, meaning their mean and variance are finite and do not change with time.

Cointegration comes into play when dealing with non-stationary price series. It allows us to construct a stationary time series, known as the spread, from two asset price series. Formally, two price series $ x_t $ and $ y_t $ are cointegrated if there exists a linear combination, $ z_t = x_t - \beta y_t $, which is an $ I(0) $ series.

$$
x_t \text{ and } y_t \text{ are cointegrated} \iff x_t \text{ and } y_t \text{ are } I(1) \text{ series and } \exists \beta \text{ such that } z_t = x_t - \beta y_t \text{ is an } I(0) \text{ series}
$$

Of course, here's the revised version:

---

**Intuitive Interpretation of Cointegration**

Understanding cointegration involves grasping its intuitive interpretation. Let's delve into the details provided:

**Decomposition of Series**: Suppose we have two I(1) series, $ x_t $ and $ y_t $, that are cointegrated. We can decompose each series into a nonstationary component ($ \nu $) and a stationary component ($ \varepsilon $). This decomposition is expressed as:

$$ x_t = \nu x_t + \varepsilon x_t $$
$$ y_t = \nu y_t + \varepsilon y_t $$

**Construction of Cointegrated Series**: Next, we form the cointegrated series, denoted as $ z_t $, which represents the spread between $ x_t $ and $ y_t $. The cointegration coefficient $ \beta $ is employed in constructing $ z_t $, given by:

$$ z_t = x_t - \beta y_t = (\nu x_t - \beta \nu y_t) + (\varepsilon x_t - \varepsilon y_t) $$

Certainly, here's an expansion on the intuitive understanding of cointegration:

**Decomposition of Series**: Suppose we have two I(1) series, $ x_t $ and $ y_t $, that are cointegrated. We can decompose each series into a nonstationary component ($ \nu $) and a stationary component ($ \varepsilon $). This decomposition is expressed as:

$$ x_t = \nu x_t + \varepsilon x_t $$
$$ y_t = \nu y_t + \varepsilon y_t $$

**Construction of Cointegrated Series**: Next, we form the cointegrated series, denoted as $ z_t $, which represents the spread between $ x_t $ and $ y_t $. The cointegration coefficient $ \beta $ is employed in constructing $ z_t $, given by:

$$ z_t = x_t - \beta y_t = (\nu x_t - \beta \nu y_t) + (\varepsilon x_t - \varepsilon y_t) $$

**Stationarity of the Spread**: It's crucial to note that $ z_t $ emerges as an I(0) process, signifying that it's stationary. This condition arises from the relationship $ \nu_{x_t} = \beta \nu_{y_t} $, implying that the nonstationary component of $ x_t $ is linearly related to the nonstationary component of $ y_t $. Since a stationary time series cannot contain a nonstationary component, $ z_t $ being stationary underscores the presence of a stable, long-term relationship between $ x_t $ and $ y_t $.

This comprehensive understanding illuminates the essence of cointegration, elucidating how it enables the creation of a stationary spread from nonstationary series, thereby facilitating the identification of enduring relationships between financial assets.

--- 

Feel free to let me know if you need further modifications!
## A Brief Digression: Correlation vs Cointegration
Since the topic of this article is cointegration, I would give away the conclusion first.

* Correlation has no well-defined relationship with cointegration. Cointegrated series might have low correlation, and highly correlated series might not be cointegrated at all.
* Correlation describes a short-term relationship between the returns.
* Cointegration describes a long-term relationship between the prices.

When we say two assets are correlated, the fact that the correlation is between the returns was implied. As we have discussed previously, asset prices are I(1) series and returns are I(0) series. When calculating the correlation coefficient of two assets, we are effectively performing a linear regression between the returns of asset A and asset B because the returns are stationary. Spurious correlation will occur if non-stationary price series are used in the regression.
## Simulation of Cointegrated Series

Simulation is a valuable tool for understanding cointegration. Simulating cointegrated series involves generating stationary returns for one asset, deriving the price series, and then constructing the spread using a stationary process. This simulation process helps illustrate the long-term relationship between asset prices.

## Derivation of the Cointegration Coefficient

The cointegration coefficient, often denoted as $ \beta $, represents the relationship between cointegrated assets. It can be obtained using methods such as the Engle-Granger test or the Johansen test. These tests analyze the linear relationship between asset prices to determine if they are cointegrated.

## Conclusion and Key Takeaways

Understanding cointegration is crucial for developing pairs and multi-asset trading strategies. Key takeaways include:
- Cointegration describes a long-term relationship between asset prices.
- It measures similarity in risk exposure between assets.
- Cointegrated assets are tethered due to the stationarity of the spread.
- Correlation and cointegration are distinct concepts.
- Engle-Granger and Johansen tests are used to find the cointegration coefficient.
- Simulation tools like ArbitrageLab can aid in understanding and analyzing cointegrated series.

This article provides a foundation for designing trading strategies based on cointegration. In Part 2 of this series, we'll explore mean reversion pair/multi-asset trading strategies. Stay tuned for more insights!


# RESULTS
Based on the premise that cointegration thrives with assets sharing similar risk exposure, I selected GAIL as Asset 1 and ONGC as Asset 2, both belonging to the Oil and Gas Industry, for backtesting over the past 3 years. This specific pair consistently outperformed the market, yielding a remarkable return of over 60% within a 2-year period. This performance significantly surpasses the industry average return on pairs trading.

Moreover, backtests were conducted on various other pairs, yielding an average return of 38%, which still stands significantly higher than the industry average.