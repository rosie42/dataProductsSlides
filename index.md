---
title       : Diamond Price Calculator Pitch Deck
subtitle    : for Developing Data Products
author      : Michael Rose
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## How much is a diamond worth?

Using the Diamond Price Calculator one can use the prices of over 50,000 diamonds to estimate the value of 
a new diamond.

Enter the parameters of the diamond and the calculator will produce an estimate of the value of the diamond.


--- 

## Multivariate Linear Regression!


- weight!
- cut!
- colour!
- clarity!
- dimensions!


```r
diamond_model <- lm(price ~ carat + cut + color + clarity + depth + table, data = diamonds)
```

---

## Let's predict!


```r
trial_diamond <- data.frame(carat = 1.2,
							cut = factor("Very Good", levels = levels(diamonds$cut)),
							color = factor("G", levels = levels(diamonds$color)),
							clarity = factor("VS2", levels = levels(diamonds$clarity)),
							depth = 60,
							table = 50)
paste("Estimated Diamond Price: $",round(predict(diamond_model, newdata = trial_diamond)))
```

```
## [1] "Estimated Diamond Price: $ 8099"
```

---

## Try it now!

<a href="https://rosie42.shinyapps.io/dataProductsProject">https://rosie42.shinyapps.io/dataProductsProject</a>
