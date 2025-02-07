# Calculate the differences in sales and visits for analysis
store_data['Sales Change During'] = store_data['Weekly Sales During Promotion'] - store_data['Weekly Sales Before Promotion']
store_data['Sales Change After'] = store_data['Weekly Sales After Promotion'] - store_data['Weekly Sales Before Promotion']
store_data['Visit Change During'] = store_data['Average Daily Visits During Promotion'] - store_data['Average Daily Visits Before Promotion']
store_data['Visit Change After'] = store_data['Average Daily Visits After Promotion'] - store_data['Average Daily Visits Before Promotion']

# Group by promotion type and store type for analysis
promotion_type_analysis = store_data.groupby('Type of Promotion').agg({
    'Sales Change During': 'mean',
    'Sales Change After': 'mean',
    'Visit Change During': 'mean',
    'Visit Change After': 'mean'
}).reset_index()

store_type_analysis = store_data.groupby('Store Type').agg({
    'Sales Change During': 'mean',
    'Sales Change After': 'mean',
    'Visit Change During': 'mean',
    'Visit Change After': 'mean'
}).reset_index()


