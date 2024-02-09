## The Caravan Insurance Sales Challenge

![](caravan-car.webp)

> Can you predict who would be interested in buying a caravan insurance policy and give an explanation why?

This dataset was created by Peter van der Putten and Maarten van Someren, and was first published as the CoIL Challenge 2000 data mining competition. The goal of the competition was to predict who would be interested in buying a specific insurance product and to explain why people would buy.

The training data contains 5,822 real customer records. Each record consists of 86 variables, containing sociodemographic data (variables 1-43) and product ownership (variables 44-86). The sociodemographic data is derived from zip codes. All customers living in areas with the same zip code have the same sociodemographic attributes. Variable 86 (Purchase) indicates whether the customer purchased a caravan insurance policy. Further information on the individual variables can be obtained at http://www.liacs.nl/~putten/library/cc2000/data.html.

In addition to the training dataset, a test dataset containing 4,000 records is provided in this repository, too.


To read more:
- Report with detailed solutions and explanations ([link](https://liacs.leidenuniv.nl/~puttenpwhvander/library/cc2000/report2.html))
- Lessons learned from the winner of the original competition ([pdf](elkan2000magical.pdf))
- Paper on bias-variance decomposition of error to analyze what caused the wide range of prediction performance from the challenge ([pdf](putten2004bias-variance.pdf))