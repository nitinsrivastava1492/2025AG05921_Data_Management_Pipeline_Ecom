# Feature Catalog
**Student Roll No**: `2025ag05921`

This catalog serves as our feature store database schema documentation mapping explicit and implicit telemetry attributes.

| Entity   | Feature Name             | Data Type    | Description                                                                             | Source Table               |
|:---------|:-------------------------|:-------------|:----------------------------------------------------------------------------------------|:---------------------------|
| User     | user_id                  | VARCHAR (PK) | Unique identifier for each customer.                                                    | users.csv                  |
| User     | age                      | INTEGER      | Age of the user.                                                                        | users.csv                  |
| User     | gender                   | VARCHAR      | Gender of the customer (Male, Female, Other).                                           | users.csv                  |
| User     | location                 | VARCHAR      | Geographical location of the customer.                                                  | users.csv                  |
| User     | user_avg_rating          | FLOAT        | The user's mean historical rating value (explicit feedback score).                      | reviews.csv (Computed)     |
| User     | user_rating_std          | FLOAT        | Standard deviation of ratings to assess rating variance.                                | reviews.csv (Computed)     |
| User     | user_review_count        | INTEGER      | Total number of reviews submitted by this user.                                         | reviews.csv (Computed)     |
| User     | user_preferred_category  | VARCHAR      | The category the user interacts with or rates most frequently.                          | reviews.csv & products.csv |
| User     | user_total_events        | INTEGER      | Sum of historical actions (clicks, add-to-carts, purchases).                            | events.csv (Computed)      |
| User     | user_purchase_events     | INTEGER      | Specific count of product purchase transactions.                                        | events.csv (Computed)      |
| Item     | product_id               | VARCHAR (PK) | Unique catalog identifier for each product item.                                        | products.csv               |
| Item     | product_name             | VARCHAR      | The consumer-facing descriptive name of the item.                                       | products.csv               |
| Item     | category                 | VARCHAR      | Broad product categorization taxonomies.                                                | products.csv               |
| Item     | price                    | FLOAT        | The standard listing price in USD.                                                      | products.csv               |
| Item     | item_avg_rating          | FLOAT        | Mean historical rating score aggregated across reviewers.                               | reviews.csv (Computed)     |
| Item     | item_review_count        | INTEGER      | Popularity metric summing total review feedback volume.                                 | reviews.csv (Computed)     |
| Item     | item_unique_reviewers    | INTEGER      | Count of distinct users who reviewed this specific item.                                | reviews.csv (Computed)     |
| Item     | item_bayesian_popularity | FLOAT        | Dampened popularity metric incorporating global priors to prevent cold-start anomalies. | Enriched (Formula)         |
