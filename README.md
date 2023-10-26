# tableau

2 datasets: This is a sample data set for a fictitious soft drink company. 

1. Beverage sales
2. Custom shape for US states

Tableau to combine these two datasets.
build all of the charts we need, create a parameter, and apply the filters.
make the dashboard dynamic and interactive using different filter types and a parameter and make sure everything updates automatically.

1. Summary key figures (KPIs)
2. A custom map of the US
3. A monthly breakdown as a line chart
4. Two bar charts for products and customers

5.

6. <!-- Article: https://www.vizwiz.com/2023/10/interactive-dashboard.html
7. Data: https://data.world/vizwiz/sample-soda-sales 
2. US Albers Map Projection : https://data.world/vizwiz/us-albers-equal-area-map-projection
3. Workbook: https://public.tableau.com/app/profile/andy.kriebel/viz/MasteringContainers-InteractiveKPIDashboard/KPIs

----------------------------------------------------------------
import pandas as pd
import random
from faker import Faker

# Function to generate random data for the data set
def generate_data(num_rows):
    fake = Faker('en_US')
    data = []

    for _ in range(num_rows):
        product = random.choice(['Cola', 'Lemonade', 'Energy Drink', 'Beer', 'Wine', 'Vodka', 'Coffee', 'Green Tea', 'Black Tea', 'Herbal Tea'])
        company = random.choice(['Coca-Cola', 'Pepsi', 'Dr. Pepper'])
        category = 'Soft Drink' if product in ['Cola', 'Lemonade', 'Energy Drink'] else 'Alcoholic' if product in ['Beer', 'Wine', 'Vodka'] else 'Coffee' if product == 'Coffee' else 'Tea'
        units_sold = random.randint(100, 1000)
        revenue = random.randint(1000, 10000)
        cost_of_goods_sold = random.randint(500, 8000)
        profit = revenue - cost_of_goods_sold
        purchase_date = fake.date_this_decade()
        customer_name = fake.name()
        customer_state = fake.state()
        customer_city = fake.city()
        customer_zipcode = fake.zipcode_in_state()
        order_id = fake.isbn10()

        data.append([product, company, category, units_sold, revenue, cost_of_goods_sold, profit, purchase_date, customer_name, customer_state, customer_city, customer_zipcode, order_id])

    return data

# Generate the data set with 10,000 rows
num_rows = 10000
data_set = generate_data(num_rows)

# Create a DataFrame using Pandas
columns = ['Product', 'Company', 'Category', 'Units Sold', 'Revenue', 'Cost of Goods Sold', 'Profit', 'Purchase Date', 'Customer Name', 'Customer State', 'Customer City', 'Customer Zip Code', 'Order ID']
df = pd.DataFrame(data_set, columns=columns)

# Save the data as a CSV file
df.to_csv('soft_drink_sales.csv', index=False)

5. -->

6. 
7. 
