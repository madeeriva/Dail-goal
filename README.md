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

# This is a conceptual example, not a runnable full code without more context.
# You'd need to install Dash: pip install dash

"""
import dash
from dash import dcc
from dash import html
import plotly.express as px
import pandas as pd

# Load your data
df = pd.read_csv('your_data.csv') # Replace with your data source

app = dash.Dash(__name__)

app.layout = html.Div([
    html.H1("My Interactive Dashboard"),

    html.Div([
        html.Label("Select Category:"),
        dcc.Dropdown(
            id='category-dropdown',
            options=[{'label': i, 'value': i} for i in df['Category'].unique()],
            value=df['Category'].unique()[0]
        )
    ]),

    dcc.Graph(id='live-update-graph')
])

@app.callback(
    Output('live-update-graph', 'figure'),
    Input('category-dropdown', 'value')
)
def update_graph(selected_category):
    filtered_df = df[df['Category'] == selected_category]
    fig = px.bar(filtered_df, x='Date', y='Value', title=f'Data for {selected_category}')
    return fig

if __name__ == '__main__':
    app.run_server(debug=True)
"""

git config --global user.name "Vivek kumar dubey"
git config --global user.email "kumar9958513256@gmail.com"
