# Modern Portfolio Theory - Markowitz Model

![Markowitz](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRHUN97KNRu7yBzC0Z8ZXxcsQnNxRrFwiafPh93Cul3pe17t5py&usqp=CAU)

Since already this concept is unknown to a lot of non-finance grads, I'll try my best to cover the topic as quick as possible, and yet make it explainable. 
We all have some dreams about how we're gonna spend our lives. And most of these dreams may require us to be financially sufficient, if not rich. And when I say that,
I am sure everyone comes down to either start up something, or invest. Here we're going to focus on the later. Everyone knows the importance and benefits of investment, and 
types of financial options available for any investment. Sadly, while many have mentally accepted they'd want to invest when they start earning, nobody knows how to! 
**Modern Portfolio Theory**, henceforth referred to as MPT, is the starting point to understand the world of investments, mathematically.
The MPT was suggested by **Harry Markowitz** in 1952 for which he won the **Nobel Prize in Economic Sciences** later.

## Understanding the parameters of MPT

MPT is a completely risk-return based assessment of your portfolio. This means, all it looks for is how to **maximize** your **returns** for a given amount of **risk**. It assumes that different people 
have different risk taking attitude. A young person would be willing to take greater risk if it might generate greater returns. While someone who is old, would not be willing to take much risk and would remain satisfied with lower returns. Whatever the risk attitude, it tries to search for that 'combination' of assets in portfolio that would generate highest possible returns (for that risk).
I hope we are clear with the very basic idea of what MPT is. Now let's briefly understand how MPT defines risk and return for its assessment. 
According to MPT, returns are simply the profit you make on an asset over a period of time. It would be negative in case of a loss. Obviously, this is very much intuitive. 

Mathematically, R is percentage change in the value of assets. 

**`R = [(V - Vo)/(Vo)]X100`**

Risk, according to Markowitz, can be expressed using the standard deviation of returns over a period of time. Recall from your high school statistics, standard deviation is the measure of how deviated the values are from their mean. So, the logic here is, if the returns are more largely deviated from their mean values, the asset having those returns is more volatile. More volatility naturally means its more risky. Look how I emphasized on 'according to Markowitz'. This is because, there are several methods of risk assessment (eg. VaR, CVaR, Conditional Risk, etc). This is because, different people have different notions on what risk means to them. For some, it is only how huge their return could be on negative side. For some, by what probability they can suffer an X% of loss on a standard normal distribution of their returns (essentially, the Z-Score). Anyway, to understand MPT, we need the basic definition of risk as described by Markowitz. 

Mathmatically, Risk **`(σ) = std(returns over that period)`**

Now this is how we can calculate risk and return of an asset. But obviously we are not going to invest in single asset. So more important value to us is the risk and return of your entire portfolio. Consider a portfolio with N number of assets. 

The expected return Ro on each one of these N Assests is the average of per period return R calculated using the percentage change formula discussed before.

**`R0(single asset) = mean(R of the asset)`**

Now that we have net expected Return for each of N assets, the net returns of the portfolio as a combination of all the assets is simply the weighted average. Its obvious isnt is? Mean is a linear quantity
So if `W1, W2, W3,..Wn` is the weight of investment done in each of the Assets the Portfolio Return (π) is,

**`π = mean(W.R) ∀ N assets`**

Pretty easy right? Now what would be the risk of entire portfolio. Weighted averge of the individual asset risks? NO!
Remember, risk isnt a linear quantity plus, the net risk of entire portfolio will also depend on how one asset moves relative to the rest in the Portfolio. Example, it is generally observed that when markets plummet, gold prices soar (because gold is universal in its value, and people trust it more than cash). Hence if the equities in your Portfolio go down, the gold will rise . Hence we can see a co-dependance of assets with each other, which will also influence the risk of the entire portfolio.
Hence mathematically, 

**`σ(portfolio) = ΣΣ(Wi.Wj.σi.σj.ρij) ∀ i,j in N`**
where, ρ(i,j) = correlation between ith and jth asset.

the quantity `σi.σj.ρij` is also called Co-variance, `σ(i,j)`

Now that we've understood the parameters of MPT, let's get into a very easy and beautiful way to analyse portfolios - graphs.

## The Risk-Return Space

The best way to understand and portfolios is to plot the risk and return of each portfolios for variety of weights W1..Wn, and choose the perfect one for your needs. That 'perfect' portfolio would be the one providing highest return for a given amount of risk. For a 2-Asset portfolio, the risk-return space looks something like this -

![Risk-Return Space](https://raw.githubusercontent.com/high-in-entropy/resume2/gh-pages/Blog/risk-ret.png)


Look how different correlation values between the assets changes the portfolio curve. This curve is plotted by changing the weights assigned to each portfolio, `W1, W2`. where `W<1` and `W1+W2=1`
As the weights are changed, the portfolio return and risk change and hence the curve. One beautiful observation which is the heart or Modern Portfolio Theory, is that as the correlation approaches closer to negative values, the return one can get for a particular amount of risk increases. This is because less the correlation more differently the assets will move respect to each other and as it turns negative they essentially would move opposite to each other just like the gold-equity example discussed before.  
So far so good. What happens to the curve when there are more than 2 assets. Now there wouldn't be a single curve connecting 3 assets as in 2 asset case. This is because for every point on the curve between Asset A and B and Asset B and C, there would be an another portfolio X and Y. Hence the the risk-return plot in any case of N>2 will actually be a space and not a simple curve.



## The Efficient Frontier

![EfficientFrontier](https://github.com/high-in-entropy/resume2/blob/gh-pages/Blog/PFSpace.png?raw=true)



This is a algorithmically generated Portfolio Space for 4 Assets and 1000 different portfolios constructed by altering W1, W2, W3, W4 such that each is less than 1 and sum is 1.

Look at the above space plot carefully. Keeping in mind that one would always be looking to invest in portfolios with higher return for certain risk. We get a series of portfolios which would be ideal for us if above condition is considered that is more return for a particular risk. That would be achieved if we invest on any point on a unique curve such that the curve represents highest possible return for some risk. This curve will be the yellow curve plotted with the space. Hence as long as you're on this yellow curve, you're an efficient investor. This curve as described by the MPT is termed as the **Efficient Frontier**. The efficient frontier development mathmeatically, is a **convex quadratic optimization problem** here solved using python's **SciPy** library with its **convex optimizer**. We will, in later blogs, learn how to use python to generate this efficient curve along with the portfolio space.

## Conclusion

We come to the most beautiful conclusion in the world of Finance. There are unique set of portfolios which offer you more return for risk as compared to other possible portfolios. Now go back and imagine you being an independent investor having X amount of money wanting to invest in N Assets. Instead of randomly listening to news, people or read articles, you now have trusted mathematical way to construct a perfect portfolio to plan for your dreams. 

Hmm. But if this were so easy everyone would have learnt MPT and made money. But thaat's not the case. Probably there are some caveats to it too. This and a lot more in following blog. Until then keep following **CEV Blogs!**



