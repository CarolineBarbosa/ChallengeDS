# Key insights: 

## Model selection

### Generalization
The RMSE on the test set, 0.32, is lower than the RMSE on the validation set, 0.48 considering Random Forest model. The Linear and Ridge Regression models performed poorly on the validation set, which indicates that linear relationships may not be sufficient to capture the underlying complexity of the data. thereforem the RF model and Gradient boosting models achieved a higher R2-score on validation indicating the models handle generalization with non-linear relationship in the data. 

The Random Forest model  is the best choice. It has the lowest error (MAE and RMSE) among the models and a relatively high R² on the validation set. 
      
### Error analysis
The overall RMSE for the test set is 0.323, showing that the model generalizes reasonably well on unseen data.  The testing results reveal interesting insights into model performance by product type:

| Produto   | MAE      | RMSE     | num |
|-----------|----------|----------|-------------------|
| Diesel    | 0.112927 | 0.160831 | 1450             |
| Gasolina  | 0.309998 | 0.342530 | 1801             |
| Etanol    | 0.357568 | 0.397083 | 1708             |

Indicating that the model performs quite differently across different produto categories. 
- Diesel: With an MAE of 0.113 and RMSE of 0.161, the model performs best on Diesel. This suggests that the model captures Diesel price patterns more accurately.
- Gasolina: MAE of 0.310, and RMSE of 0.343, which indicates higher error than Diesel but still acceptable. Gasoline prices might have more variability.
- Etanol: MAE of 0.358 and RMSE of 0.397 indicate the highest error among products, suggesting the model struggles most with Etanol. This could result from more volatile pricing or unique patterns not fully captured by the features.

Despite having a close number of observations per product (imbalance is unlikely), the pricing dynamic is visually different across products. 
Some indights: 
- Higher errors for Gasoline and Etanol could indicate that their prices fluctuate more than Diesel;
- Gasoline and Etanol may have other factors that the model does not fully capture;
    
### Areas for Improvement
Next Steps:
* Hyperparameter Tuning: To further improve Random Forest models, fine-tune hyperparameters.
* Additional Features: Consider adding interaction terms, regional demand factors, or other market indicators that might uniquely impact Gasolina and Etanol prices.
* Segmented Modeling: Creating separate models for each product could improve accuracy, as it would allow each model to capture product-specific price dynamics. For instance, a dedicated model for Gasolina might focus on additional seasonal or competitive factors that impact Gasolina more than Diesel.

## Model explainability and business insights
### Yearly Trend:
There is a positive trend captured by the model and indentified on the analysis which likely is a reflection of the inflation or market changes impacting demand increase or limited resources year after year.
- Review long term pricing strategies, planning for annual price increases aligned with inflation. This yearly trend can drive in budgeting and forecasting for future periods.

### Purchase Price driving the sellling price
Coefficient of avg_preco_compra was the second most importante feature, which is a logical link with selling price.  This indicates that cost is a critical driver for setting selling prices.
- Creating a monitoring system for the oil purchase price seems crucial, as price fluctuations are essential to defining the best selling precification.
- Negotiating better purchase terms or securing currency advantages on contracts can reduce exposure to fluctuations in purchase costs, helping to maintain stable prices for customers and protect the business margin.

### Product-Level Pricing Differences

produto Coefficients:


Etanol: has consederable importance  factor on predicting the selling price. indicating it has a behavior different from the Gasoline and diesel. 

- As each product has an unique price dynamic, implementing differentiated pricing strategies whan purchasing and selling for each product can improve profitability, as each product has its' specific market demand.