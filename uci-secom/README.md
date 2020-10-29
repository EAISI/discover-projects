# UCI SECOM dataset

Approaches for the class imbalance problem, feature selection and causality in semicondutor manufacturing process line data.


## Data Description
The SECOM dataset in the UCI Machine Learning Repository is semicondutor manufacturing data which has 1567 records, 590 anonymized features and 104 fails. The process yield has a simple pass/fail response (encoded -1/1).

The dataset has the following characteristics:

1.	two-class problem
2.	an imbalance with a 14:1 skew of pass to fails
2.	large number of features -- 590
3.	missing data
4.	features/columns which do not have sufficient information
5.	4% of the columns/features have more than 50% of their records missing
6.	some columns have constant values 


## Tasms
The SECOM dataset presents us with two problems, namely

1. Working with skewed data, i.e. an imbalanced classification problem (see <a href="#ref1">[1]</a>)
2. Feature selection (see <a href="#ref2">[2]</a>)

In this project, you will explore both tasks.

### Imbalanced classification
  - Try to successfully predict fails using i) cost sensitive learning approach and ii) sampling-based approach
  - Evaluate performance using the precision-recall curve
  - Discuss the pros and cons of different operating points on the PR curve 

### Feature reduction
A secondary objective will be feature reduction. A streamlined feature set can not only lead to better prediction accuracy and data understanding but also save manufacturing resources. Explore causal understanding of the manufacturing process using the 590 features.


### Further reading
<a name="ref1"></a>[1] [H. He and E. A. Garcia, “Learning from Imbalanced Data,” IEEE Trans. Knowledge and Data Engineering, vol. 21, issue 9, pp. 1263-1284, 2009.](https://github.com/dkapitan/jads-discover-projects/blob/main/uci-secom/he2009learning.pdf)

<a name="ref2"></a>[2] [McCann, Michael, et al. "Causality Challenge: Benchmarking relevant signal components for effective monitoring and process control." NIPS Causality: Objectives and Assessment, 2010.](https://github.com/dkapitan/jads-discover-projects/blob/main/uci-secom/mccann2008causality.pdf)  


## Acknowledgement
We thankfully acknowledge [Meena Mani's work](https://github.com/Meena-Mani/SECOM_class_imbalance) on this dataset.
