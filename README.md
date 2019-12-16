# Recommendation System Review
Heinz 95729 Course Project  
Author: Jiefei Xia

## Project Update
* Nov. 19: Project Proposal; AWS Configuration  
* Nov. 26: Basic Papers; Baseline Algorithm  
* Dec. 3: Trend Papers; All Algorithms; Pre Draft Slides (10min); Discussion
* Dec. 10: Report

## Paper List
### Basic
个性化推荐系统的研究进展.pdf  
基于深度学习的推荐系统研究综述.pdf  
推荐系统调研报告及综述.pdf  
Toward the Next Generation of Recommender System.pdf  
Matrix Factorization Techniques for Recommendation System.pdf  
Amazon-Recommendations.pdf
### Trend Topics
Collaborative Filtering with Temporal Dynamics.pdf  
Factorization Meets the Neighborhood.pdf  
Restricted Boltzmann Machines for Collaborating Filtering.pdf  
SVD Feature A Toolkit for Feature-based Collaborative Filtering.pdf  
The Wisdom of the Few.pdf  
Information Seeking Convergence of Search, Recommendations and Advertising.pdf  


## Algorithm
| Algorithm                    | Category                |
| ---------------------------- | ----------------------- |
| FP-Growth                    | Association Rule        |
| Matrix Factorization         | Collaborative Filtering |
| Restricted Boltzmann Machine | Collaborative Filtering |

## Final Deliverable
* Report
* GitHub
* Presentation

## Dataset
[Instacart grocery data](https://www.instacart.com/datasets/grocery-shopping-2017)  
The dataset is provided as-is for non-commercial use.

### Data Dictionary
`orders` (3.4m rows, 206k users):
* `order_id`: order identifier
* `user_id`: customer identifier
* `eval_set`: which evaluation set this order belongs in (see `SET` described below)
* `order_number`: the order sequence number for this user (1 = first, n = nth)
* `order_dow`: the day of the week the order was placed on
* `order_hour_of_day`: the hour of the day the order was placed on
* `days_since_prior`: days since the last order, capped at 30 (with NAs for `order_number` = 1)

`products` (50k rows):
* `product_id`: product identifier
* `product_name`: name of the product
* `aisle_id`: foreign key
* `department_id`: foreign key

`aisles` (134 rows):
* `aisle_id`: aisle identifier
* `aisle`: the name of the aisle

`deptartments` (21 rows):
* `department_id`: department identifier
* `department`: the name of the department

`order_products__SET` (30m+ rows):
* `order_id`: foreign key
* `product_id`: foreign key
* `add_to_cart_order`: order in which each product was added to cart
* `reordered`: 1 if this product has been ordered by this user in the past, 0 otherwise

where `SET` is one of the four following evaluation sets (`eval_set` in `orders`):
* `"prior"`: orders prior to that users most recent order (~3.2m orders)
* `"train"`: training data supplied to participants (~131k orders)
* `"test"`: test data reserved for machine learning competitions (~75k orders)
