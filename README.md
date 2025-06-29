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
