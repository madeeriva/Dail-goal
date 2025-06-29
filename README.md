# Example using Plotly.express (simplified)
import plotly.express as px
import pandas as pd

# Sample data
data = {'Category': ['A', 'B', 'C', 'A', 'B', 'C'],
        'Value': [10, 15, 7, 12, 18, 9]}
df = pd.DataFrame(data)

# Create a bar chart
fig = px.bar(df, x="Category", y="Value", color="Category")

# Display the chart
fig.show()

Sales During Promotion = 
CALCULATE(
    SUM(Sales[SalesAmount]),
    NOT(ISBLANK(Sales[PromotionCode]))
)

Sales Without Promotion =
CALCULATE(
    SUM(Sales[SalesAmount]),
    ISBLANK(Sales[PromotionCode])
)

Uplift % = 
VAR Promo = [Sales During Promotion]
VAR NonPromo = [Sales Without Promotion]
RETURN IF(
    NonPromo > 0,
    DIVIDE(Promo - NonPromo, NonPromo) * 100,
    BLANK()
)

Number of Promotions = DISTINCTCOUNT(Sales[PromotionCode])

Orders With Promotion = 
CALCULATE(
    DISTINCTCOUNT(Sales[OrderID]),
    NOT(ISBLANK(Sales[PromotionCode]))
)

Redemption Rate (%) = 
DIVIDE([Orders With Promotion], DISTINCTCOUNT(Sales[OrderID])) * 100
