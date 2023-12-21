# palmerpenguins <a href='https://allisonhorst.github.io/palmerpenguins/'><img src='man/figures/logo.png' align="right" height="138.5" /></a>

The goal of palmerpenguins is to provide a great dataset for data
exploration & visualization, as an alternative to `iris`. You can download the data in csv [here](https://github.com/EAISI/discover-projects/blob/main/palmer-penguins/penguins_lter.csv).

<img src="README-flipper-bill-1.png" width="75%" style="display: block; margin: auto;" />


## About the data

Data were collected and made available by [Dr. Kristen
Gorman](https://www.uaf.edu/cfos/people/faculty/detail/kristen-gorman.php)
and the [Palmer Station, Antarctica
LTER](https://pallter.marine.rutgers.edu/), a member of the [Long Term
Ecological Research Network](https://lternet.edu/).


### Meet the Palmer penguins

<img src="lter_penguins.png" width="75%" style="display: block; margin: auto;" />

### Bill dimensions

The culmen is the upper ridge of a bird’s bill. In the simplified
`penguins` data, culmen length and depth are renamed as variables
`bill_length_mm` and `bill_depth_mm` to be more intuitive.

For this penguin data, the culmen (bill) length and depth are measured
as shown below (thanks Kristen Gorman for clarifying!):

<img src="culmen_depth.png" width="75%" style="display: block; margin: auto;" />

## Articles and examples

- The original website of the R package ([link](https://allisonhorst.github.io/palmerpenguins/index.html))
- Regression and classification using scikit-learn ([link](https://inria.github.io/scikit-learn-mooc/python_scripts/trees_dataset.html))
- Classification and exploratory data analysis ([Kaggle](https://www.kaggle.com/code/alabuda/classification-and-eda-palmer-penguins))
- Use a neural network for multi-class classification ([blog](https://www.neuraldesigner.com/learning/examples/palmer-penguins/))


## License

Data are available by
[CC-0](https://creativecommons.org/share-your-work/public-domain/cc0/)
license in accordance with the [Palmer Station LTER Data
Policy](https://pallter.marine.rutgers.edu/data/) and the [LTER Data
Access Policy for Type I data](https://lternet.edu/data-access-policy/).

## Citation

To cite the palmerpenguins package, please use:

``` r
citation("palmerpenguins")
#> 
#> To cite palmerpenguins in publications use:
#> 
#>   Horst AM, Hill AP, Gorman KB (2020). palmerpenguins: Palmer
#>   Archipelago (Antarctica) penguin data. R package version 0.1.0.
#>   https://allisonhorst.github.io/palmerpenguins/. doi:
#>   10.5281/zenodo.3960218.
#> 
#> A BibTeX entry for LaTeX users is
#> 
#>   @Manual{,
#>     title = {palmerpenguins: Palmer Archipelago (Antarctica) penguin data},
#>     author = {Allison Marie Horst and Alison Presmanes Hill and Kristen B Gorman},
#>     year = {2020},
#>     note = {R package version 0.1.0},
#>     doi = {10.5281/zenodo.3960218},
#>     url = {https://allisonhorst.github.io/palmerpenguins/},
#>   }
```

## Additional data use information

Anyone interested in publishing the data should contact [Dr. Kristen
Gorman](https://www.uaf.edu/cfos/people/faculty/detail/kristen-gorman.php)
about analysis and working together on any final products. From Gorman
et al. (2014): “Individuals interested in using these data are expected
to follow the US LTER Network’s Data Access Policy, Requirements and Use
Agreement: <https://lternet.edu/data-access-policy/>.”

## References

**Data originally published in:**

-   Gorman KB, Williams TD, Fraser WR (2014). Ecological sexual
    dimorphism and environmental variability within a community of
    Antarctic penguins (genus *Pygoscelis*). PLoS ONE 9(3):e90081.
    <https://doi.org/10.1371/journal.pone.0090081>

**Data citations:**

Adélie penguins:

-   Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Adélie penguins (*Pygoscelis adeliae*) nesting along the
    Palmer Archipelago near Palmer Station, 2007-2009 ver 5.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/98b16d7d563f265cb52372c8ca99e60f>
    (Accessed 2020-06-08).

Gentoo penguins:

-   Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Gentoo penguin (*Pygoscelis papua*) nesting along the
    Palmer Archipelago near Palmer Station, 2007-2009 ver 5.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/7fca67fb28d56ee2ffa3d9370ebda689>
    (Accessed 2020-06-08).

Chinstrap penguins:

-   Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Chinstrap penguin (*Pygoscelis antarcticus*) nesting
    along the Palmer Archipelago near Palmer Station, 2007-2009 ver 6.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/c14dfcfada8ea13a17536e73eb6fbe9e>
    (Accessed 2020-06-08).
