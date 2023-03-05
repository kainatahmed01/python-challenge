# python-homework
# python-homework
import pandas as pd

df = pd.read_csv('budget_data.csv')

num_months = len(df)


net_profit = df['Profit/Losses'].sum()


changes = df['Profit/Losses'].diff()
avg_change = changes.mean()


max_increase = changes.max()
max_increase_date = df.loc[changes.idxmax(), 'Date']
max_decrease = changes.min()
max_decrease_date = df.loc[changes.idxmin(), 'Date']


print(f'Total Months: {num_months}')
print(f'Total: ${net_profit}')
print(f'Average Change: ${avg_change:.2f}')
print(f'Greatest Increase in Profits: {max_increase_date} (${max_increase:.0f})')
print(f'Greatest Decrease in Profits: {max_decrease_date} (${max_decrease:.0f})')

