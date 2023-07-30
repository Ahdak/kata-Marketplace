# Kata Marketplace

The Manager of CB-MarketPlace wants to create some financial KPI about the products being sold in the marketplace (mainly from external vendors).

2 reports are currently provided :
- Report 1 : `product-sold.csv` which provides details of each product sold
- Report 2 : `product-vendor.csv` which provides vendor's product.

The manager wants to automate the computation of the global incomes from selling products of **external vendors** which is :

- 5% of the operation amount if not discounted
- 2% of the operation amount if discounted

Let’s take an example :

Given the [product-sold.csv](product-sold.csv)


| productId | quantity | unitaryPrice | isDiscount | comment       |
| ----------- | ---------- | -------------- | ------------ | --------------- |
| 1         | 10       | 100          | FALSE      | <br/>         |
| 2         | 1        | 200          | FALSE      | <br/>         |
| 3         | 10       | 1000         | FALSE      | <br/>         |
| 3         | 2        | 700          | TRUE       | operation 123 |
| 4         | 5        | 500          | TRUE       | <br/>         |
| 5         | 1        | 100          | FALSE      | <br/>         |

and the [product-vendor.csv](product-vendor.csv)


| procuctId | vendorName |
| ----------- | ------------ |
| 1         | V1         |
| 2         | V2         |
| 3         | V3         |
| 4         | V4         |
| 5         | CB         |

The expected result should be **638**

The computation details :

| productId | quantity | unitaryPrice | isDiscounted | vendor | total operation | Income % | Unitary Result |
| ----------- | ---------- | -------------- | -------------- | -------- | ----------------- | ---------- | ---------------- |
| 1         | 10       | 100          | FALSE        | V1     | 1000            | 5%       | 50             |
| 2         | 1        | 200          | FALSE        | V2     | 200             | 5%       | 10             |
| 3         | 10       | 1000         | FALSE        | V3     | 10000           | 5%       | 500            |
| 3         | 2        | 700          | TRUE         | V3     | 1400            | 2%       | 28             |
| 4         | 5        | 500          | TRUE         | V4     | 2500            | 2%       | 50             |
| 5         | 1        | 100          | FALSE        | CB     | 100             | 0%       | 0              |
| <br/>     | <br/>    | <br/>        | <br/>        | <br/>  | <br/>           | total    | 638            |
