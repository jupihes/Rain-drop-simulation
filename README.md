
# "How many 1 centimeter raindrops does it take to cover 90% of a 1 meter line?"

In a exam to check knowledge of candidates for "RAN performance manager" vacancy, I asked them to try to answer below Google interview question:

### "How many 1 centimeter raindrops does it take to cover 90% of a 1 meter line?"

You can find analytical answer at following [web link](https://lnkd.in/gVQPkMR).

I tired to simulate and solve it with [Monte_Carlo_method](https://en.wikipedia.org/wiki/Monte_Carlo_method). Here is result:

![plot](https://github.com/jupihes/Rain-drop-simulation/blob/master/Rain%20drop.png)


### َnalytical solution
You can find analytical answer at following [web link](https://lnkd.in/gVQPkMR).

Here is extract
> The probability that a single drop doesn't hit it is (1-0.01) = 0.99. The probability that none of  d  drops hit it is $0.99^{d}$ . The probability that it is wet after  d  drops is  $(1−0.99)^{d}$.
> By linearity of expectation, the expected wet length after  d  drops is simply the "sum" (i.e., integral) of all those probabilities that the tiny pieces of the line are wet. And as all those probabilities are the same, the expected wet length is  $1−0.99^{d}$ .

Here is plot of needed rain drops per each `wet_length`:

```python
x = np.linspace(.1, 1, 10000)
y = [np.log10(1-wet_length)/np.log10(0.99) for i in x]
plt.plot(x,y)
```
