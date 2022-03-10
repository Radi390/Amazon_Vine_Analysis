# Amazon_Vine_Analysis

## Overview
This project analyzes Amazon reviews written by the paid Amazon Vine program members. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who must publish a review.
This project aims to determine if there is any bias toward favorable reviews from Vine members compared with organic reviews.

## Procedure
A dataset of Amazon reviews from S3 Amazon S3 storage was picked for this analysis. A database was created in Amazon RDS and pgAdmin, and they connected. In the "Amazon_Reviews_ETL.ipynb" file, the dataset is extracted to a data frame utilizing Spark and Google Colab. Then duplicated rows were removed and transformed into four data frames include: "customers_df," "product_df," "review_df," and "vine_df." Finally, all those data frames are loaded into respective tables in pgAdmin.
In "Vine_review_Analysis.ipynb", data frames made in the previous section loaded, and then reviews were filtered to ones with more than 20total votes and more than 0.5 helpful votes to total votes ratio. In the next step, reviews were split into two separate data frames based on whether they were part of the vine program or not.
Finally, the number of five to one-star reviews counted for each paid and organic review to determine any bias in Amazon Vine program reviews.

## Results

- 107 Vine reviews follow our criteria for valuable reviews.
- Fifty-six reviews are 5-stars, 32 are four-star, 16 are three-star, two are two-star, and one is one star.
- In vine reviews, 52.33 % of reviews are five-star.
- ![This is an image](/PaidNumbers.jpg)

- Thirty-nine thousand eight hundred sixty-nine organic reviews follow our criteria for valuable reviews. 
- Twenty-one thousand five are five-stars, 7384 are four-stars, 3744 are three-stars, 2412 are two-star, and 5324 are one-star.
- In organic reviews, 52.68 % of reviews are five-star.
![This is an image](/OrganicNumbers.jpg)
## Summary

### Results

![This is an image](/Organic_vs_Paid.jpg)

### Conclusion
In determination, Opistie of our expectations, there was no meaningful difference in the percentage of five-star reviews between Vine vs. organic reviews. However, The bias we have expected is located in Low-rated reviews. For the Vine program, only 2.8% of reviews are one or two stars. However, this number for organic reviews is 18.52%. Furthermore, 29.9% of the Vine reviews are four-star. On the other hand, organic reviews are only 18.52%.

In this analysis, we could address bias in Vine program. However, it is still unknown whether the Vine reviews are as valuable as organic ones. To find out the answer to this question,  Recommendation is analyzing the percentage of valuable reviews (The ones with more than 20 vote and percentage of helpful to total vote is more than 0.5.) to total reviews for both Paid and Organic reviews.
